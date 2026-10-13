# QuadCtrl - A QuadRotor Device Making Avionics and Flight-Control Education Accessible
QuadCtrl is a ~$30 educational micro-quadcopter designed to teach embedded flight control from the ground up. An ESP32-S3 flight controller fuses LSM6DSV IMU data with a complementary filter and runs a cascaded angle → rate PID loop at 500 Hz to drive four 8520 brushed motors. A custom ESP-NOW transmitter with an OLED display and potentiometers lets you tune PID gains live in flight. A VL53L0X/VL53L1X time-of-flight sensor adds altitude hold, and optical flow and UWB positioning are planned for autonomous flight without motion capture.

<br>
The base drone consists of:

* 4 8520 DC Brushless Motors w/ 75mm Propelllers
* A 1S LiPo battery - 5-7 minutes of run time.
* A 6-axis accelerometer/gyro sensor. 
* A microcontroller (ESP32s) to communicate with hardware and sensors.
* 75 grams
* 3D-Printed Motor Mount Frame

<br>
This robot was inspired by the UCSD course, CSE 176E/276E, taught by Professor Steven Swanson, with the goal being to streamline the design around the EnVision Maker Studio's ESP32S3 DevBoard.
</br>



- - -

<br>


## Drone in action:

<p align="center" >
<img   align="center"  style=" display: block;margin-left: auto;margin-right: auto;width:400px;border: 5px solid grey;border-radius:20%;
" src="./images/Assembly 2 (1).png">
<img   align="center"  style=" display: block;margin-left: auto;margin-right: auto;width:400px;border: 5px solid grey;border-radius:20%;
" src="./images/ECE193HQuadCopterLEDVersion6 1.png">
</p>

<img   align="center"  style=" display: block;margin-left: auto;margin-right: auto;width:400px;border: 5px solid grey;border-radius:20%;
" src="./images/IMG_6508.gif">


- - -

<br>

## Electronics:
<br><br>
Below is an image of the drone schematic, with an explanation of the purposes of most components:
<img   align="center"  style=" display: block;margin-left: auto;margin-right: auto;width:400px;border: 5px solid grey;border-radius:20%;
" src="./images/ECE193HQuadCopterShieldSchematicV1.pdf">

* NMOS acts like a voltage controlled switch, so that when Pin 4 writes HIGH, NMOS turns on which allows current to flow through the motor. 

* Pull down resistor is to hold the MOSFET off when the gate isn’t being driven.

* Flyback diode is there to protect the motors, since motors are a coil, like inductors, they resist sudden changes in current, think how the current of an inductor can’t change instantaneously! So the current in the motor wants to keep flowing even if the NMOS has turned off which means no current flow, with the diode, the current flows through the diode and back into the motor so it slowly dies out safely without feeding back into the NMOS and destroying it. (Because of how fast the mosfets can switch on and off, a schottky diode is recommended and used here because those are able to switch very fast)

* Bulk capacitor (220uF) is there since motors draw a large amount of current when they turn on, which might make the battery supply dip in voltage since they can’t supply that amount instantaneously, so the bulk caps here help supply that burst locally

* Bypass capacitor (1uF) is here so that any high frequency electrical noise here created from the motors is shorted to ground and gets smoothed out

<br><br>

- - -
<br>
