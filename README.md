# Nick & Aaron's Robot Arm Project
  ## Descirption
  For this project we must create a working robot arm that picks up or moves objects using code from an Arduino. Specifically we wanted to create a robot that could        throw a paper airplane consitently 15ft.

## Table of Contents
* [Link To Planning Document](#Link-To-Planning-Document)
* [Link To Onshape Document](#Link-To-Onshape-Document)
* [Link To Repository](#Link-To-Repository)
* [List of Materials](#List-of-Materials)
* [Wiring Diagram](#Wiring-Diagram)
* [Code](#Code)
* [CAD Renderings](#CAD-Renderings)
* [Finished Product](#Finished-Product)
* [Project Schedule](#Project-Schedule)
* [Problems And Issues](#Problems-And-Issues)
* [Obituary](#Obituary)
---

### Link To Planning Document
  [Link To Planning Document](https://docs.google.com/document/d/17YDV7t57pZ85mQmOJNlsC8A8yKnT_Qs7Ie4sjMxX9nk/edit)
  
### Link To Onshape Document
  [Link To Onshape Document](https://cvilleschools.onshape.com/documents/6b8511f108c770ff195489a6/w/40bfbfc61cb8fbbabc800d69/e/9607a84db268c87d29a03a86)
  
### Link To Project Repository 
  [Link To Repository](https://github.com/nbednar2929/Nick-And-Aaron-Arm-Project)
  
### List of Materials
  Acrylic Sheets, ABS Plastic, Solder, Male-Male Wires, Button, 220 Ohm Resistor, Arduino Metro, ½” Standoffs, Prototyping Shield, Custom Built Wires, 9V Battery Pack, AA Batteries, Mini Red LED, LED Holder,Toggle Switch, MG996R Metal Gear Servo, FS90R Continuous Servo, Servo Horn, #4-40 Socket Head Cap Screws, #4-40 Machine Screw Nuts, and Electrical Tape.

### Wiring Diagram 
![Nick   Aaron Robot Arm Wiring Diagram](https://user-images.githubusercontent.com/91289646/223543930-9f5f0bc4-8fcd-4142-a8e3-4dcc5d505129.PNG)

### Code
[Link To Code Respository](https://github.com/nbednar2929/CircuitPython)

The code for this project is titled: PaperAirplaneThrowerCode.py

```python
import time #importing files
import board
import digitalio
import pwmio
from adafruit_motor import servo
from digitalio import DigitalInOut,Direction,Pull
import simpleio

# create a PWMOut object on Pin 9.
pwm = pwmio.PWMOut(board.D10, duty_cycle=2 ** 20, frequency=40)

# Create a servo object, my_servo.
my_servo = servo.Servo(pwm)

btn = DigitalInOut(board.D13) #create button 
btn.direction = Direction.INPUT #identify button  direction
btn.pull = Pull.DOWN #pull up button 



while True:
    print('Switch1')
    time.sleep(0.1)
    if btn.value: #if button being pressed
        print('Button')
        for angle in range(0, 180, 5):  # 0 - 180 degrees, 5 degrees at a time forward.
            my_servo.angle = angle
            print(angle)
        for angle in range(180, 0, -5):  # 0 - 180 degrees, 5 degrees at a time forward.
            my_servo.angle = angle
``` 

### CAD Renderings
![Nick   Aaron Box Front Rendering](https://user-images.githubusercontent.com/91289646/218838529-44cd4cfe-a749-42f7-ad30-3a955038aae8.PNG)
![Nick   Aaron Box Transparent](https://user-images.githubusercontent.com/91289646/218838518-d366655b-7db6-4df0-8b9a-95e480e584b1.PNG)


### Finished Product
![Screenshot 2023-02-14 10 20 14 AM](https://user-images.githubusercontent.com/91289646/218780479-2df16a67-2c3b-427f-a2b0-c2ed91c32739.png)
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
#### CAD Issues
The majority of our issues for this project related to CAD given that was what we spent 90% of our time on. Because we were both working on the same CAD document but in different part studios, at times we would make changed and fail to communicate that to the other resulting in possible miss measurments. We learned this soon into our project and began focussing on proper communication between one another. We put our trust in public onshape documents that had real world objects we could use the dimensions of to quicken our CAD process. At times these public models had incorrect units leading to our own CAD models having measurment issues. As of right now we still don't know of a way to test the legitimacy of Onshape documents, although I'm sure we could take rough measurements of these real world items and compare them to the dimensions of the online models.

#### Code Issues
The majority of our code issues came down to a lack of time to work on them after all the CAD problems were solved. The majority of our code problems were solved in the last week of work and the code is somewhat functioning. The main issue is that the gears fail to return to their zero degree state after spinning 180 degrees. So if you were to keep pressing the button without reseting the gears it wouldn't spin because the servo was already at its maximum spin. At times the gears spin too fast that they end up hopping out of the slots they sit in and get jammed within one another. To solve this we began making inserts for the axles so that they swould stay flush with the bottom of the box. Sadly the time we were given to work on the project ended before thsee could be properly intergrated. We chose to use a servo instead of a stepper motor because it's smaller and presumably has more power which would aid in throwing the paper airplane as far as possible. But the servo caused a lot of issues so it maybe have been wise to just stick with a stepper motor like most others doing this project.

### Obituary
If we were to pick this project back up we'd definitely create fully polished code as well as create a claw to go onto our robot. We'd integrate the claws that we made onto our arm as well. As to what we would've done differently, we would've given ourselves more time work on the code, made sure to do more research before using public Onshape models, and finally we would ensure our communcation was held to an utmost standard. Otherwise our project fit together, integrated properly, and spun with a passionate fervor capable of sending any plane into the outer atmosphere.

---
