---
title: "Solar panel data"
date: 2025-09-14
---

___________CURRENTLY DOWN FOR MAINTENCE___________________
<iframe width="450" height="250" style="border: 1px solid #cccccc;"
src="https://thingspeak.mathworks.com/channels/2937156/charts/2?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=100&title=Power&type=column&yaxis=Power+%28w%29">
</iframe>
-Normal values between -0.3w - 5w in theory could be up to 10

<iframe width="450" height="250" style="border: 1px solid #cccccc;"
src="https://thingspeak.mathworks.com/channels/2937156/charts/1?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=1000&title=Solar+Voltage&type=line&yaxismax=14&yaxismin=6&yaxis=Voltage+%28V%29">
</iframe>
-Voltage on solar panel end of charge controller

This project is the first step of my big goal of making an autonomous boat that can travel from Newfoundland to Ireland. The goal of this project is to collect solar data for weather conditions that will be similar to the weather of the voyage. This data will let me make informed decisions about solar panel, hull, and motor size, and thus is necessary before I start designing the boat. 

![Solar Collector](https://github.com/user-attachments/assets/1e498280-6fe4-4448-99d6-fa8bba60896f)

The Solar Collector is made from two parts. The first is a small 10-w solar panel on the end of a 2x4x10 that can be attached to a railing or fence. The other is a bucket I got from Kent, which serves as a durable splash-resistant enclosure for the electronics. The electronics themselves are made from an MPPT charge controller, which charges a 12V 18Ah AGM battery. This battery powers the Arduino, to which is attached a current and voltage sensor to measure the power input, as well as an SD card module and an ESP8266. The SD card module connects through SPI to the Arduino and stores the current time as well as the current and voltage output by the solar panel, once every ~5s. It stores each day's data into a separate file. The ESP8266 is connected to the Arduino through a software serial communication library. It is used for getting the real-time data from the SD cards for data logging as well as communicating the data to ThinkSpeak. The portfolio then takes the data from thinkSpeak to show here. This project is still under development. I want to move the location of the collector to my friend's house since right now it's in the shade of a tree for most of the day. Additionally, I need a way to burn excess power since right now it very slowly accumulates power. In my original plan this would be done by a relay that would start a motor whenever the battery voltage got above 12.5v, however since the arduino is directly powered from the 12v battery the LDO used for regulating the power is already running very hot and I after testing it the extra load the relay puts on the arduino seems like it might overly stress the LDO. My plan is to either hook a large resistor up in series with the supply to reduce the energy the supply itself has to dissipate, which seems like a very jank solution, or to use a buck converter to also reduce the voltage.

