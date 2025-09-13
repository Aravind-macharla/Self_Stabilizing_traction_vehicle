Self-Balancing & Traction Vehicle

Microcontroller: Arduino Mega / ESP32
Motors: DC geared motors (flywheel + rear wheel)
Sensors: MPU6050 (gyro + accelerometer), motor encoders
Power: Li-Po Battery (3S 11.1V 500–1200 mAh)
Drivers: L298N (flywheel), L293D (rear wheel)
Servo: TowerPro MG995 (steering)
Buzzers: 2 × Active buzzers (2–5V)

![image](https://github.com/Aravind-macharla/Self_Stabilizing_traction_vehicle/blob/e7ab091df056c0f92c541741a25b52415a0ce913/Self_stabilizing_traction_vehicle/Picture/Final%20model.jpeg)
Features

PID-based balancing controller with MPU6050 feedback.

Flywheel for balance + rear wheel for traction.

Steering via servo motor.

Dual buzzers for alerts.

Remote control via ESP8266 Wi-Fi web interface.

Calibration of balance point stored in EEPROM.

Safety alert: buzzers trigger if tilt > 30°.

![image](https://github.com/Aravind-macharla/Self_Stabilizing_traction_vehicle/blob/e7ab091df056c0f92c541741a25b52415a0ce913/Self_stabilizing_traction_vehicle/Picture/schematic.png)
![image]()
Calibration

Power on and connect via serial/Wi-Fi.

Send c+ → Start calibration mode.

Place bike at balance point (upright, no tilt).

Send c- → Save calibration offsets to EEPROM.

Bike begins balancing.

Remote Control (Wi-Fi Web UI)

ESP8266 runs an access point (BikeControl / 12345678).

Control buttons available:

Forward / Backward / Stop

Turn Left / Turn Right / Center

Speed can be adjusted via on-screen slider (0–255).

![image](https://github.com/Aravind-macharla/Self_Stabilizing_traction_vehicle/blob/e7ab091df056c0f92c541741a25b52415a0ce913/Self_stabilizing_traction_vehicle/Picture/Web%20page%20which%20connects%20to%20controls%20of%20bike.jpg)
![image](https://github.com/Aravind-macharla/Self_Stabilizing_traction_vehicle/blob/e7ab091df056c0f92c541741a25b52415a0ce913/Self_stabilizing_traction_vehicle/Picture/Wi-fi%20connection%20to%20bike.jpg)
Notes

The 7805 regulator is not recommended → use a switching 5V regulator.

Motors should be powered from the Li-Po directly (not USB).

Balance tuning is done through PID gains (Kp, Ki, Kd) in Arduino code.

Prototype Build

Frame: PLA/metal chassis with two wheels.

Control Loop:

MPU6050 → Angle estimation

PID → Flywheel torque correction

Servo → Steering adjustments

Rear wheel → Constant drive / manual control
