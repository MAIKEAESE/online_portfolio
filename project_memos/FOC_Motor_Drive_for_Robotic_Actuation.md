# FOC Motor Drive for Robotic Actuation

## One-Minute Story

I built this project around one practical question: can a compact embedded motor-drive board provide stable, measurable low-level actuation for a real robotic mechanism?

The original graduation project targeted a pressure-control mechanism, but the transferable research value is the actuator-control stack: a DRV8300-based gate-driver circuit, MOSFET three-phase power stage, magnetic encoder feedback, three-channel current sampling, synchronized complementary PWM, and FOC software pipeline. The work moved from schematic design to board bring-up and measured power-rail validation, which makes it useful evidence for robotic actuation, exoskeleton joint drives, and hardware-in-the-loop control research.

## Key Data

| Layer | Evidence | Why It Matters |
|---|---|---|
| Power integrity | 12.00V target measured at 11.97V, 0.25% error | Main supply was validated before motor-drive testing. |
| Gate-drive rail | 10.50V target measured at 10.40V, 0.96% error | DRV8300 gate-drive power stayed within sub-1% measurement error. |
| Sensor / logic rails | 5.00V measured at 4.97V; 3.30V measured at 3.31V | Sensor and MCU rails were stable enough for encoder and control logic. |
| Current feedback | three-channel 14-bit ADC | Supports phase-current acquisition for current-loop control. |
| Position feedback | SPI encoder interface, 1M baud | Provides rotor-position feedback for FOC angle alignment. |
| PWM output | three-channel synchronized complementary PWM | Enables coordinated three-phase inverter control. |

## Design Logic

The hardware was structured as a complete actuator-control chain:

1. **Power path first:** validate the 12V input and derived rails before driving the motor.
2. **Power-stage control:** use DRV8300 and MOSFET bridge circuitry for three-phase motor actuation.
3. **Feedback acquisition:** collect rotor position through magnetic encoder feedback and phase-current signals through ADC channels.
4. **FOC computation:** convert three-phase current into the d-q frame through Clarke / Park transforms.
5. **PWM synthesis:** generate inverter duty cycles through inverse Park transform and SVPWM.
6. **Calibration:** align encoder zero position with rotor magnetic phase before closed-loop operation.

This order matters because it mirrors how real robotic actuators fail in practice: unstable rails and incorrect feedback alignment can invalidate higher-level control even when the algorithm is theoretically correct.

## Validation Result

The most concrete validation result is the measured power-rail table:

| Tested Rail | Target | Measured | Relative Error |
|---|---:|---:|---:|
| Main supply | 12.00V | 11.97V | 0.25% |
| Gate driver | 10.50V | 10.40V | 0.96% |
| Sensor rail | 5.00V | 4.97V | 0.60% |
| MCU rail | 3.30V | 3.31V | 0.30% |

The conclusion is modest but solid: the board reached successful bring-up, stable multi-rail power validation, and preliminary motor-rotation validation. This is enough to support a credible actuator-hardware story without overclaiming torque-control performance.

## Debugging and Engineering Takeaway

The project strengthened three practical skills that are directly relevant to robotics research:

- **Board-level bring-up:** checking the power path, soldering quality, connector mapping, and driver-interface behavior before running control code.
- **Feedback-chain reasoning:** understanding how encoder alignment and current sampling affect FOC stability.
- **System-level risk control:** validating hardware layers in sequence instead of jumping directly to closed-loop control.

For advisor outreach, this project should be presented as evidence that I can work below the simulation layer: debugging the actuator electronics, validating measured rails, and connecting embedded control details to future robotic actuation experiments.

## Evidence Used

Representative extracted figures from the thesis:

- DRV8300 gate-driver schematic.
- Three-phase bridge / motor-drive schematic.
- Current-sampling circuit.
- PCB layout detail.
- Power architecture diagram.
- Encoder interface circuit.
- Reverse-voltage / surge-protection circuit.
- FOC software flowchart.
- Current-loop block diagram.
- Waveform / validation screenshots.
