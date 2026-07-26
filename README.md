# Jiang Jiawei Research Evidence Brief

Focus: embedded robotic actuation, board-level hardware implementation, and learning-based locomotion.

This page is a compact evidence index for research-oriented graduate outreach. It is not a full project report. The strongest evidence is listed first.

## 1. Actuation and Embedded Control

**FOC Motor Drive Board for Compact Robotic Actuation**

Evidence:
- [PCB layout](foc_motor_drive/foc_pcb_layout.png)
- [Physical board photo](foc_motor_drive/foc_board_photo.jpg)
- [12V / power validation photo](foc_motor_drive/power_validation_12v.jpg)
- [Motor rotation demo](foc_motor_drive/foc_motor_rotation_demo.mp4)

Technical scope:
- Three-phase motor-drive board for robotic actuation.
- Power stage, current sampling, communication/protection circuitry, and PCB layout.
- FOC control workflow involving SVPWM and Clarke-Park transforms.
- Preliminary motor-rotation and power validation.

Technical value:
- Demonstrates hands-on experience with compact actuation hardware, current sensing, embedded control loops, and actuator-level reliability.
- This is the strongest hardware evidence in the portfolio and should be viewed as the main proof of low-level robotic actuation capability.

## 2. Learning-Based Locomotion

**Isaac Sim Bipedal Locomotion Training**

Evidence:
- [Reward curves / training logs](isaac_sim_training/reward_curve.png)
- [Training scene](isaac_sim_training/isaac_training_scene.png)
- [Flat walking screenshot](isaac_sim_training/isaac_flat_walking.png)

Technical scope:
- Isaac Sim / local RL workflow setup for bipedal locomotion.
- Reward tuning around step clearance, torso posture, gait stability, and continuous-motion stability.
- Short-cycle progress from environment setup to stable walking and slope traversal.

Technical value:
- Supports the robot-learning side of the application.
- Relevant to legged locomotion, reward design, gait stabilization, and sim-to-sim / sim-to-real foundations.

Evidence note:
- The current screenshots are used as process evidence. The reward curves and training description should be treated as the main proof until short locomotion clips are added.

## 3. Field Robotics and Hardware Reliability

This section is supporting evidence. It shows practical embedded-system experience across robotic platforms, but should not lead the portfolio.

### Embedded Hardware Diagnostics and Board Bring-Up

Evidence:
- [Hardware diagnostics photo](hardware_debugging/embedded_hardware_diagnostics.jpg)
- [Linux embedded platform debugging](hardware_debugging/linux_embedded_platform_debug.jpg)
- [MCU board bring-up](hardware_debugging/mcu_board_bringup.jpg)

Technical scope:
- MCU-level boards and Linux-capable embedded platforms.
- Board bring-up, peripheral checks, serial debugging, power-path diagnosis, and abnormal-startup isolation.
- Use of multimeters, oscilloscopes, adjustable power supplies, load instruments, and serial tools.

Technical value:
- Useful as evidence of physical-system debugging, sensorized platform integration, and embedded control reliability.

### Robotics and Agricultural Automation Projects

Evidence:
- [Mountain tea garden drone system](robotics_projects/tea_garden_drone_system.jpg)
- [Sugarcane monitoring system](robotics_projects/sugarcane_monitoring_system.png)
- [Cabbage harvester CAN / motor-control evidence](robotics_projects/cabbage_harvester_can_motor_control.jpg)
- [SPIE mine robot publication evidence](robotics_projects/spie_mine_robot_publication.jpg)

Technical scope:
- UAV hardware and power-management module.
- Agricultural machinery monitoring, multi-sensor acquisition, and field-oriented deployment.
- CAN communication and motor-control exposure in agricultural robotics.
- STM32-based multi-sensor mobile robot work documented in SPIE Proceedings.

Technical value:
- Shows breadth in real robotic systems, sensing, communication, and embedded deployment.
- Use as background evidence after the FOC and Isaac Sim sections.

## Email Usage

Suggested one-line link text:

`I also organized a compact evidence brief for my FOC motor-drive board, Isaac Sim locomotion training, and embedded robotics projects: [link].`

Suggested reading order:
- Actuation and Embedded Control
- Learning-Based Locomotion
- Field Robotics and Hardware Reliability
