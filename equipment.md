
# Team Jerry - Micro Mouse Components

This document outlines the key components used by Team Jerry for their Micro Mouse project, including essential additional items for a complete and functional robot.

## Sensors:

* **Time of Flight (ToF) Sensor:** VL53L0Xv2

  * *Purpose:* Used for precise distance measurement, crucial for wall detection and navigation within the maze.
* **Gyroscope:** MPU9250

  * *Purpose:* Provides angular velocity and orientation data, enabling accurate turns and heading control for the mouse.
* **Encoders:**

  * **Primary:** Built-in encoders on N20 motors.
    * *Purpose:* Essential for tracking wheel rotations, allowing for precise odometry and distance traveled calculations.
  * **Alternative:** AS5600
    * *Purpose:* A potential substitute for the built-in encoders, offering high-resolution rotary position sensing.

## Motors:

* **Motors:** N20 with built-in encoders
  * *Description:* Compact and high-torque geared DC motors, well-suited for the small scale of a micro mouse. The integrated encoders simplify wiring and provide direct feedback for motor control.
* **Motor Driver:** L293D
  * *Purpose:* A common H-bridge motor driver IC used to control the direction and speed of the DC motors based on signals from the microcontroller. (Note: More modern and efficient motor drivers like those from Pololu are often preferred for better power efficiency and less heat generation in competitive mice.)

## Core Electronics:

* **Microcontroller Unit (MCU):** ESP32 Wroom

  * *Purpose:* The "brain" of the micromouse. The ESP32 Wroom series offers integrated Wi-Fi and Bluetooth, a powerful dual-core processor, and ample GPIOs, making it suitable for complex navigation algorithms, sensor data processing, and potentially wireless debugging/communication. It processes sensor data, executes navigation algorithms (e.g., flood fill), controls the motors, and manages overall robot behavior.
* **Voltage Regulators:** (e.g., LDOs, Buck Converters)

  * *Purpose:* To provide stable and regulated power at different voltage levels (e.g., 5V for the ESP32 and other components, 3.3V for certain sensors) from the battery supply, protecting sensitive electronics.
* **Capacitors:** (various types and values)

  * *Purpose:* For decoupling power lines, filtering noise, and smoothing power delivery, especially for motors which can generate electrical noise.
* **Resistors:** (various values)

  * *Purpose:* For current limiting (e.g., for LEDs in IR emitters), pull-ups/downs, and voltage division.

## Power Supply:

* **Battery:** (e.g., LiPo, Li-ion, NiMH)
  * *Purpose:* To power all components of the micromouse. High discharge rate and appropriate capacity are important to ensure consistent power to motors, especially during high-speed maneuvers. Common choices are 2S (7.4V) or 3S (11.1V) LiPo batteries.
* **Battery Connector:** (e.g., XT30, JST)
  * *Purpose:* For safely connecting the battery to the micromouse's power distribution.
* **Power Switch:**
  * *Purpose:* For easily turning the micromouse on and off.

## Mechanical Components:

* **Chassis:** (Custom-fabricated from materials like acrylic, carbon fiber, aluminum, or 3D-printed)
  * *Purpose:* The structural frame that holds all components together. It needs to be lightweight, rigid, and provide mounting points for motors, sensors, and the electronics board.
* **Wheels:** (Rubber or silicone tires are common for good grip)
  * *Purpose:* To provide traction and allow the mouse to move smoothly within the maze. Wheel diameter affects odometry calculations.
* **Ball Caster / Skid (3D printed)):**
  * *Purpose:* To provide a third point of contact for stability, typically at the front or rear, allowing the two driven wheels to handle steering.
* **Mounting Hardware:** (Screws, nuts, standoffs, spacers, zip ties, double-sided tape)
  * *Purpose:* For securely attaching all components to the chassis.

## Connectivity and Debugging:

* **Printed Circuit Board (PCB):** (Custom-designed or protoboard/perfboard)
  * *Purpose:* To consolidate and connect all electronic components. A custom PCB can significantly reduce size, weight, and improve reliability.
* **Wires/Cables:** (Various gauges and lengths)
  * *Purpose:* For electrical connections between components.
* **Connectors/Headers:** (e.g., JST, Dupont headers)
  * *Purpose:* For modularity and easy connection/disconnection of sensors, motors, and other peripherals.
* **Debugging Tools:** (e.g., USB-to-serial converter, oscilloscope, multimeter)
  * *Purpose:* Essential for testing individual components, diagnosing issues, and monitoring signals during development.
* **Programming Cable:** (e.g., USB cable for ESP32 Wroom development board)
  * *Purpose:* To upload firmware and code to the microcontroller.

## Optional/Advanced Components:

* **Buzzer/LEDs:**
  * *Purpose:* For auditory or visual feedback during operation, debugging, or indicating status (e.g., maze solved, error).
