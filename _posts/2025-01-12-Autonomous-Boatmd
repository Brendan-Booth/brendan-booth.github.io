---
title: "Autonomous Boat"
date: 2025-01-12
![boot 1](https://github.com/user-attachments/assets/46c3a189-8428-4dcf-b542-23ebe217a02a)
-Thanks to the birdwatcher who took this picture for me!
This is my autonmus boat! So far its longest mission has been 34km, which was done at 1m/s. Based of the data from this run it seems that it ha a maxiumum range at this speed of ~74km. At 1m/s it consumes ~40w of power in calm conditions, however if the speed is decreased to 0.8m/s its efficency improves to 104km, though the downside of this is this mission would take ~35 hours. Building this boat took me just over a year, with the majority of the time spent in designing and constructing the hulls. The hulls were designed in fusion 360, where I spent a lot of time trying to get them to be fully parametric, which the shape of the hull is, however I had to then split this into 104 pieces in order to fit it on my Voron 0 priner which has 120mmx120mm buildplate, and my old slow Ender 3. 
![boot modle](https://github.com/user-attachments/assets/ddf60f52-4661-4a29-864c-b63d0fddd672)
-overveiw of hull model with componet colors
The parts for the hull took ~10 spools of filament and took almost 1000 print hours between the two hulls. These pices were designed to slot into each other which aligns them in order for them to be glued into place. 
![boat unglued](https://github.com/user-attachments/assets/d0117da6-6ca4-4c65-a91a-6f26f8b1418d)
-one hull partially assembled
After they were glued the hull was faired and sanded and then several coats of epoxy were poured over top to create a watertight layer. This was then painted.
![fair and just](https://github.com/user-attachments/assets/d55351f0-374a-40ef-ad2c-d64b229e895f)
-hulls after fairing
![eepoxy](https://github.com/user-attachments/assets/38eb3883-7169-421e-b9aa-8b9b4aec90b2)
-epoxy was done in two position, the more difficult one, that i didnt get a picture of was the bottoms of the hull which required 4 layers since the epoxy just wanted to slide right off the hull and would only make realy thin coats. the top being flat only required 1 layer, however it was complicated by my decision to put embed in some 10mm rubber tubeing to act as o-rings. This didn't work because of the uneaveness of the hull and I later added weather stripping which seems to work very well. 

During and after hull construction I was also working on the electronics, after some reasearch I went with ardupilot as my software, and ran it on a speedybee fixed wing controller. For radios, I have a 300m telemetry radio, a cheap radio controller and reciver. It also had a speedy-bee combined gps and compass module. For drive I have two pretty large low KV motors, which were chosen with the batteries to give simaler rpm's to the more expensive motors the props were meant for. They are driven by some pretty huge 80A speed controllers, which are potentionally needed for the higher throttle commands I cant quite achieve yet because of the vibrations.
https://github.com/user-attachments/assets/835a0619-e6fe-4864-9d44-38835135e096
-short video of initial tests, the componets were basically the cheapest possible so I was pretty nervous about it, They all worked but I cut the camera out since it was on the same frequency as my wifi and every time it was turned on the wifi in my room would cut out.

my first test was done in november, it was both cold and dissapointing. Cold since I was just wearing some dumb rubber boots that were imeaditly overtopped my the freezing lake water. And dissapointing since there were really bad vibraion problems with the motors that started melting the 3d printed prop hubs, and I thus I couldn't drive it at all, and just had to stand in the lake testing waterproofness. Also at this point the connectors for two hulls were about 20ibls heavier then they needed to be, and I redislocated my shoulder from moveing the boat around. 
![first test](https://github.com/user-attachments/assets/3c4ae99d-7ea3-4b6f-8ce4-9eeabe60b72f)
-there was also a lot of wind, and I couldn't really see anything because I forgot a hair elastic

For the second test I added some bearings which helped but didnt fix vibrations and added a automatic bilge system and weather stripping to have a drier boat.
![bilge system](https://github.com/user-attachments/assets/48c4a524-19db-41d9-aec2-356b069fba0e)
-limit switch activated by a float which turns on pump when the water reaches sufficent height. 

However these changes were enough to make it work! After a lot of fighting software and tuneing PID controller I finaly go it working well enough for long missions!
https://www.youtube.com/watch?v=VCD_91h2P_U 
-video of some tuneing
As mentioned earlier it succesfully compleated the the mission there was one hiccup where some weeds were caught on one of the props on the 5th of 10 laps and I took it in to remove the weeds. However it was able to compensate for the weeds and make it back to the its home. I think this might be able to be helped by programming in ocassional sharp turns into missions to dislodge weeds. Right now the project is on hold until summer comes back, and I will attempt ocean missions.
