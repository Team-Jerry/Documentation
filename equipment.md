# Team Jerry - Micro Mouse Component Overview

This document provides a comprehensive list of the components used by Team Jerry for the Micro Mouse project, outlining their purpose and specific selections.

---

## 1. Microcontroller Unit (MCU)

* **ESP32 Wroom**
  * **Description:** The central processing unit and "brain" of the Micro Mouse. The ESP32 Wroom series is chosen for its powerful dual-core processor, ample General Purpose Input/Output (GPIO) pins, and integrated Wi-Fi and Bluetooth capabilities.
  * **Purpose:** Processes sensor data, executes advanced navigation algorithms (e.g., maze mapping, pathfinding), controls motor movements, and manages overall robot behavior. Its wireless capabilities offer potential for real-time debugging and data telemetry.

## 2. Sensors

* **Time of Flight (ToF) Sensor: VL53L0Xv2**
  * **Purpose:** Utilized for precise, absolute distance measurements to detect walls and obstacles within the maze. This is crucial for accurate navigation and mapping.
* **Gyroscope: MPU9250**
  * **Purpose:** Provides angular velocity and orientation data, enabling the Micro Mouse to execute precise turns and maintain accurate heading control throughout the maze navigation.
* **Encoders:**
  * **Primary:** Built-in encoders on N20 motors.
    * **Purpose:** Essential for tracking the rotational position and speed of each motor shaft. This feedback is critical for precise odometry, allowing the mouse to calculate distance traveled and position within the maze.
  * **Alternative:** AS5600 Magnetic Rotary Encoder.
    * **Purpose:** A high-resolution alternative or supplementary encoder for precise rotary position sensing, offering potentially finer control and more accurate odometry.
* **Infrared (IR) Sensors:** (Typically multiple units, e.g., 2-4 for front and side wall detection).
  * **Purpose:** Complement the ToF sensor for short-range, highly responsive wall detection and fine-tuning the mouse's alignment within maze cells. These are vital for immediate obstacle avoidance and maintaining a straight path.

## 3. Motors & Drivers

* **Motors: N20 with built-in encoders**
  * **Description:** Compact, high-torque geared DC motors selected for their suitability in small-scale robotic applications. The integrated encoders simplify the mechanical design and provide direct feedback for closed-loop motor control.
* **Motor Driver: L293D Dual H-Bridge IC**
  * **Purpose:** Controls the direction and speed of the N20 DC motors by converting signals from the ESP32 Wroom into appropriate voltage and current for the motors.
  * *Note:* While the L293D is a functional choice, more modern motor drivers often offer higher efficiency, lower heat generation, and more precise control, which could be considered for future iterations.

## 4. Power Supply

* **Battery:** (e.g., LiPo, Li-ion, NiMH - Specific type to be determined/listed)
  * **Purpose:** Provides electrical power to all components of the Micro Mouse. High discharge rate and suitable capacity are critical to deliver consistent power, especially during demanding maneuvers. Common choices are 2S (7.4V) or 3S (11.1V) LiPo batteries.
* **Battery Connector:** (e.g., XT30, JST - Specific type to be determined/listed)
  * **Purpose:** Ensures a secure and reliable connection between the battery and the Micro Mouse's power distribution system.
* **Power Switch:**
  * **Purpose:** Allows for safe and convenient power on/off control of the entire robot.
* **Voltage Regulators:** (e.g., LDOs, Buck Converters - Specific types to be determined/listed)
  * **Purpose:** Steps down and stabilizes the battery voltage to the required operating voltages for various components (e.g., 5V for the ESP32 and motor driver logic, 3.3V for sensors). This protects sensitive electronics from overvoltage and ensures stable operation.
* **Capacitors:** (Various types and values - Specific types to be determined/listed)
  * **Purpose:** Used for decoupling power lines, filtering electrical noise (especially from motors), and smoothing voltage ripples to ensure clean power delivery to all circuits.
* **Resistors:** (Various values - Specific types to be determined/listed)
  * **Purpose:** Utilized for current limiting (e.g., for IR LEDs), pull-up/pull-down configurations on digital lines, and voltage division for sensor inputs.

## 5. Mechanical Components

* **Chassis:** (Custom-fabricated from materials like acrylic, carbon fiber, aluminum, or 3D-printed)
  * **Purpose:** The structural framework that houses and provides mounting points for all electronic and mechanical components. It is designed to be lightweight, rigid, and precisely sized for maze navigation.
* **Wheels:** (Typically rubber or silicone tires)
  * **Purpose:** Provide traction and enable the mouse's movement. The wheel diameter directly impacts odometry calculations and overall speed.
* **Ball Caster / Skid:** (3D Printed)
  * **Purpose:** Provides a stable third point of contact, typically at the front or rear, allowing the two driven wheels to handle steering and propulsion effectively. Being 3D printed allows for custom geometry and weight optimization.
* **Mounting Hardware:** (Screws, nuts, standoffs, spacers, zip ties, double-sided tape)
  * **Purpose:** Used for securely fastening all components onto the chassis and PCB, ensuring structural integrity and preventing movement during high-speed maneuvers.

## 6. Optional/Advanced Components

* **Buzzer / LEDs:**
  * **Purpose:** Provide auditory and/or visual feedback during operation, useful for status indications (e.g., maze solved, error codes, power status) and debugging.
