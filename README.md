# HEARTBEAT-MONITOR**
About:
Heart rate, body temperature and blood pressure monitoring are very important parameters of human body. Doctors use various kind of medical apparatus like thermometer for checking fever or body temperature, BP monitor for blood pressure measurement and heart rate monitor for heart rate measurement. In this project, we have built an Arduino based heartbeat monitor which counts the number of heartbeats in a minute. Here we have used a heartbeat sensor module which senses the heartbeat upon putting a finger on the sensor.

Components:

Arduino
Heart Beat sensor module
16x2 LCD
Push button
Bread board
Power
Connecting wires

Working of Heartbeat Monitor Project:

Working of this project is quite easy but a little calculation for calculating heart rate is required. There are several methods for calculating heart rate, but here we have read only five pulses. Then we have calculated total heart beat in a minute by applying the below formula:

     Five_pusle_time=time2-time1;

      Single_pulse_time= Five_pusle_time /5;

      rate=60000/ Single_pulse_time;

where time1 is first pulse counter value

time2 is list pulse counter value

rate is final heart rate.

When first pulse comes, we start counter by using timer counter function in arduino that is millis();. And take first pulse counter value form millis();. Then we wait for five pulses. After getting five pulses we again take counter value in time2 and then we substarct time1 from time2 to take original time taken by five pulses. And then divide this time by 5 times for getting single pulse time. Now we have time for single pulse and we can easily find the pulse in one minute, deviding 600000 ms by single pulse time.

Rate= 600000/single pulse time.

In this project we have used Heart beat sensor module to detect Heart Beat. This sensor module contains an IR pair which actually detect heart beat from blood. Heart pumps the blood in body which is called heart beat, when it happens the blood concentration in body changes. And we use this change to make a voltage or pulse electrically.

Circuit Diagram Explanation
Circuit of heartbeat monitor is shown below, which contains arduino uno, heart beat sensor module, reset button and LCD. Arduino controls whole the process of system like reading pulses form Heart beat sensor module, calculating heart rate and sending this data to LCD. We can set the sensitivity of this sensor module by inbuilt potentiometer placed on this module. 

Arduino Based Heartbeat Counter Circuit Diagram:

Heart beat sensor module’s output pin is directly connected to pin 8 of arduino. Vcc and GND are connected to Vcc and GND. A 16x2 LCD is connected with arduino in 4-bit mode. Control pin RS, RW and En are directly connected to arduino pin 12, GND and 11. And data pin D4-D7 is connected to pins 5, 4, 3 and 2 of arduino. And one push button is added for resetting reading and another is used to start the system for reading pulses. When we need to count heart rate, we press start button then arduino start counting pulses and also start counter for five seconds. This start push button is connected to pin 7 and reset push button is connected to pin 6 of arduino with respect to ground.
