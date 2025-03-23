
Intruder Alert System 🚨

Description

This is a motion-detection intruder alert system built using a Raspberry Pi Pico, PIR sensor, LED, and buzzer. The system is programmed in MicroPython and simulated in Wokwi.

      Features
 Detects motion using a PIR sensor
 Activates an LED and buzzer when motion is detected
 Written in MicroPython
 Simulated using Wokwi

     Components Used
Raspberry Pi Pico
PIR Motion Sensor
LED
Buzzer
Resistors & Jumper Wires

     How It Works

The PIR sensor detects motion.
If motion is detected, the system: 
Turns on the LED
Activates the buzzer to alert users
If no motion is detected, the LED and buzzer remain off


Try it online with Wokwi:
(https://wokwi.com/projects/424954622368924673)

     Code To Project
from machine import Pin ,PWM
import time 

PIR_Sensor = Pin(26, Pin.IN)
LED     = Pin(4 , Pin.OUT)
Buzzer = PWM(Pin(12))


while True:
    if PIR_Sensor.value() == 1:
        print ("Motion Detected")
        LED.value(1)
        Buzzer.freq(1000)
        Buzzer.duty_u16(30000)
        time.sleep(2)

    else:
        LED.value(0)
        Buzzer.duty_u16(0)
        time.sleep(2)
       



