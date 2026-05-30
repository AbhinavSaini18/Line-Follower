# ESP32 PID Line Follower Robot

An advanced Line Follower Robot built around the ESP32 microcontroller, designed for high-speed and accurate autonomous navigation. The robot uses an 8-channel IR sensor array for line detection, a PID control algorithm for smooth path tracking, encoders for speed feedback, and TF-Luna LiDAR for obstacle detection.

## Features

* PID-based line following control
* 8-channel RLS-08 IR sensor array
* ESP32 microcontroller
* TB6612FNG motor driver
* Dual N20 600 RPM geared motors
* AS5600 magnetic encoders
* TF-Luna LiDAR obstacle detection
* Lightweight and compact chassis
* Real-time sensor processing
* Adjustable PID tuning parameters

## Hardware Used

| Component         | Specification             |
| ----------------- | ------------------------- |
| Microcontroller   | ESP32                     |
| Motor Driver      | TB6612FNG                 |
| Motors            | 2 × N20 600 RPM DC Motors |
| Sensors           | RLS-08 IR Array           |
| Encoder           | AS5600 Magnetic Encoder   |
| LiDAR             | TF-Luna                   |
| Battery           | 11.1V 850mAh LiPo         |
| Voltage Regulator | LM2596 Buck Converter     |

## System Architecture

```text
Battery
   |
Buck Converter
   |
ESP32
├── RLS-08 IR Sensor Array
├── TF-Luna LiDAR
├── AS5600 Encoders
└── TB6612FNG Motor Driver
      ├── Left N20 Motor
      └── Right N20 Motor
```

## Control Strategy

The robot continuously reads the IR sensor array to determine its position relative to the track.

### PID Controller

The controller calculates the error between the desired line position and the current position:

* **Proportional (P):** Corrects current error.
* **Integral (I):** Eliminates accumulated offset.
* **Derivative (D):** Reduces oscillations and predicts future error.

Motor speeds are adjusted dynamically using the PID output to achieve smooth and accurate line tracking.

## Project Structure

```text
LineFollower/
│
├── src/
│   ├── main.ino
│   ├── pid_controller.cpp
│   ├── sensors.cpp
│   ├── motor_driver.cpp
│
├── include/
│
├── docs/
│   └── concept_note.pdf
│
├── images/
│
└── README.md
```

## Future Improvements

* Automatic PID tuning
* Speed profiling for different track sections
* Sensor fusion using encoder and LiDAR data
* Obstacle avoidance during competitions
* Telemetry and wireless debugging

## Applications

* Robotics competitions
* Autonomous navigation research
* Embedded systems learning
* Control systems and PID experimentation

## Team Walrus

Developed as part of a robotics project focused on designing a reliable, efficient, and competition-ready autonomous line follower robot.

## License

This project is licensed under the MIT License.
