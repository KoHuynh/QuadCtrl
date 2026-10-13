# QuadCtrl - A QuadRotor Device Making Avionics and Flight-Control Education Accessible
QuadCtrl is a ~$30 educational micro-quadcopter designed to teach embedded flight control from the ground up. An ESP32-S3 flight controller fuses LSM6DSV IMU data with a complementary filter and runs a cascaded angle → rate PID loop at 500 Hz to drive four 8520 brushed motors. A custom ESP-NOW transmitter with an OLED display and potentiometers lets you tune PID gains live in flight. A VL53L0X/VL53L1X time-of-flight sensor adds altitude hold, and optical flow and UWB positioning are planned for autonomous flight without motion capture.

<br>
The drone consists of:

* 4 8520 DC Brushless Motors w/ 75mm Propelllers
* A 1S LiPo battery - 5-7 minutes of run time.
* A 6-axis accelerometer/gyro sensor. 
* A microcontroller (ESP32s) to communicate with hardware and sensors.
* 75 grams
* 3D-Printed Motor Mount Frame

<br>
This robot was inspired by the CSE 176E/276E, with the goal being to streamline the design around the EnVision Maker Studio's ESP32S3 DevBoard.
</br>


- - -

<br>
