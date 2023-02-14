# Nick & Aaron's Robot Arm Project
  ## Descirption
  For this project we must create a working robot arm that picks up or moves objects using code from an Arduino. Specifically we wanted to create a robot that could        throw a paper airplane consitently 15ft.

## Table of Contents
* [Link To Planning Document](#Link-To-Planning-Document)
* [List of Materials](#List-of-Materials)
* [Wiring Diagram](#Wiring-Diagram)
* [Code](#Code)
* [CAD Renderings](#CAD-Renderings)
* [Finished Product](#Finished-Product)
* [Project Schedule](#Project-Schedule)
* [Problems And Issues](#Problems-And-Issues)
* ["Obituary"](#"Obituary")
---

### Link To Planning Document
  [Link To Planning Document](https://docs.google.com/document/d/17YDV7t57pZ85mQmOJNlsC8A8yKnT_Qs7Ie4sjMxX9nk/edit)
  
### List of Materials
  Acrylic Sheets, ABS Plastic, Solder, Male-Male Wires, Button, 220 Ohm Resistor, Arduino Metro, ½” Standoffs, Prototyping Shield, Custom Built Wires, 9V Battery Pack, AA Batteries, Mini Red LED, LED Holder,Toggle Switch, MG996R Metal Gear Servo, Servo Horn, #4-40 Socket Head Cap Screws, #4-40 Machine Screw Nuts, and Electrical Tape.

### Wiring Diagram 
![Nick   Aaron Robot Arm Wiring Diagram](https://user-images.githubusercontent.com/91289646/218571097-c64b1c0c-d430-4d5d-9718-90f53add36ee.PNG)

### Code
```python
import time #importing files
import board
import digitalio
import pwmio
from adafruit_motor import servo
from digitalio import DigitalInOut,Direction,Pull
import simpleio

pwm = pwmio.PWMOut(board.D10, duty_cycle=2 ** 20, frequency=40) # create a PWMOut object on Pin 9.

my_servo = servo.Servo(pwm) # Create a servo object, my_servo.

btn = DigitalInOut(board.D8) #create button 
btn.direction = Direction.INPUT #identify button  direction
btn.pull = Pull.UP #pull up button 

switch = DigitalInOut(board.D12) #create switch
switch.direction = Direction.INPUT #identify button direciton

while True:
    if switch.value: #if switch is on
        if btn.value: #if button being pressed
            for angle in range(0, 180, 5):  # 0 - 180 degrees, 5 degrees at a time forward.
                my_servo.angle = angle
                time.sleep(0.05)
``` 

### CAD Renderings


### Finished Product
<img src=![Screenshot 2023-02-14 10 20 14 AM](https://user-images.githubusercontent.com/91289646/218780479-2df16a67-2c3b-427f-a2b0-c2ed91c32739.png)
     width="400" 
     height="500" />
![Screenshot 2023-02-14 10 21 17 AM](https://user-images.githubusercontent.com/91289646/218780777-2d684f8b-5388-4154-8460-23c26740e8b0.png)

### Project Schedule
* <b>11/28 Week 1:</b> Completed all research.
* <b>12/5 Week 2:</b> Completed both a proof of concept and finalized our design.
* <b>12/19 Week 4:</b> Finish base and main pillar and finish spinning code.
* <b>12/26 Week 5:</b> Work on supporting arm and claw and work on claw code.
* <b>1/9 Week 7:</b> Work on full sequence code.
* <b>1/23 Week 9:</b> Begin assembly and testing final code.
* <b>1/30 Week 10:</b> Finish assembly and testing final code.
* <b>2/6 Week 11:</b> Begin documentation.
* <b>2/13 week 12:</b> Have claw working and running properly,Have the sequence code done 
* <b>2/14 Week 12:</b> Complete documentation, Have base and main pillar and spinning code working and ready to go.

### Problems and Issues


### "Obituary"
---
