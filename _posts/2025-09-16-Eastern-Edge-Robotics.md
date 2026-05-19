---
title: "Eastern Edge Robotics"
date: 2026-05-19
---

Eastern Edge Robotics is a student design team with ~30 members that competes in the MATE ROV competition at the university level. For the competition, teams must design and build ROVs to perform specific tasks that change every year. 

2025-2026 was my second year on the team, and because of that, I had more leadership opportunities and worked on many more projects. I worked on three main projects this year: underwater electric actuation, cameras, and the vertical profilier. Additionally, I was involved in troubleshooting and speeding up critical path components for the bot. 

The project I planned for this year was to develop a reliable, versatile system for tool actuation on the ROV. In 2024-2025, we only had static tooling, which works for many mission tasks but limits us on some of the more complex ones. To achieve this, I primarily focused on electric motor systems due to my prior experience with them and their ease of integration with the rest of our system; however, in retrospect, I should have given pneumatic and hydraulic systems more serious consideration. After a lot more research, I came up with four options to try; first, I had some experience with waterproofing brushed gear motors from my previous year on the team, and they had proven to be very reliable and versatile. Next was adding an encoder to the motor for controlled rotation, initially planned for camera actuation. Next was buying underwater servos, which I had not had much luck with in previous years, but a new member mentioned a specific servo he had used in high school that worked great for him. Finally, I also looked into waterproofing a servo ourselves.

My first step for the DC motors was choosing a motor to waterproof. I chose https://www.digikey.ca/en/products/detail/sparkfun-electronics/15277/9995750 primarily due to its low cost, and circular output shaft, with the RPM and torque being close enough to what I wanted. The circular output shaft was important because I planned to install an O-ring on it for waterproofing. The low cost was also important because I planned to break many of them through testing. To waterproof the motor, I CNC-machined an HDPE cover to fit over the motor head and hold the O-ring, then potted the back of the motor. I followed the instructions in Parker's O-Ring handbook to get all my important dimensions, starting with my 6mm shaft and relatively low RPM. I followed a design table that specified a number 10 O-ring with an outer groove diameter of 9.12mm, and constructed the hat based on that. 

![Unpotted with Hat](https://github.com/user-attachments/assets/a527d433-c6e1-4431-9ee0-05ff412e97be)
First test fit of the motor, not enough of the shaft available, so I made some small tweaks.

![V1 Potted](https://github.com/user-attachments/assets/f0c82b37-5c7e-4399-91dc-984b9b199558)
Second motor I potted, the first one I did, I forgot to fill some holes in the motor casing before potting, and the epoxy infiltrated the housing, preventing the rotor from rotating. I also filled this motor with mineral oil to further prevent water infiltration, but it greatly reduced speed and torque. Additionally, the process of filling them involved drilling a small hole in the back of the motor to fit a syringe of mineral oil; this introduced some loose debris that caused damage to the motor after ~1.5 days of rotation. I built three of these mineral-oil-filled motors, all of which failed in a similar way after ~1 day of rotation. However, on disassembly, I didn't find any water, so I decided to forgo the mineral oil and trust in the O-ring seal. 

![V5 on the robot](https://github.com/user-attachments/assets/25184a64-fdd0-4acc-9518-d895d320e0f9)

For the most recent version, I changed the hat for easier mounting, switched to a jacketed two-wire cable for better potting, and integrated strain relief into the potting frame. Tonight (May 19th) will be its first test for an actual competition run, but it has already spent ~48 hours at 4m with no RPM drop, so I am optimistic. 

The motor encoder worked well in testing, but it introduced too much electronic complexity for our short-staffed electronic team, so we pivoted. 

Buying a waterproof servo was also a short story, as they did not stand up to my 4m for a day test, with water infiltrating and damaging the board.

I took on a more leadership role in waterproofing our own servos because other projects were taking up a lot of time. The first thing we tried was disassembling a servo, epoxing the control board, filling it with mineral oil, and reassembling. This worked well, passing the 24-hour at 4m test and showing no signs of corrosion since then. It did leak some mineral oil, and we worried that, over a longer time scale, this would allow water infiltration, which could corrode the potentiometer or motor and could not be sealed with epoxy. So we decided that, after assembling in mineral oil, we would dip the motor in Plasti Dip to seal the grease in. This test also succeeded, so we ordered some more motors to seal. Sealing these was delayed because I was working on many other projects, and the people I'd assigned had limited availability. I did manage to get them done later, but by then we had started practicing competition runs, and it was decided not to install them at this time, with our priority on spending more time practicing. There are a couple of tasks that would benefit from them, so depending on how the next week of practice goes, they may yet be used.

This project was great, and I think the approach of trying a bunch of different things at once and then choosing the winning option is a powerful problem-solving strategy I will continue to use in the future. 

The next project I worked on was the robot's camera system. I worked mainly on the hardware and waterproofing aspects of the camera design, as well as handling much of the soldering and assembly, since much of the camera streaming/Pi wizardry talk goes over my head. Collaborating with members of the software and electrical teams on this project taught me a lot. Our first approach was inspired by a previous year of Pi cams connected to Pi-Zeros, which then connected to the main Pi on the bot via USB Gadget. This approach seemed very promising for a long time, as testing on laptops showed that everything worked great. However, on connecting to the Pi, the USB connection would drop and not be reestablished, which, to our best guess, is some limitation of the Pi. After a bit of troubleshooting, we couldn't resolve the problem, and it seemed unresolvable with the hardware we had at the time. Timelines were getting very tight after this failure, and we needed another option. We decided on another shotgun problem-solving strategy and split our effort into two different camera systems. First was a much simpler system that used the same camera modules as our previous strategy, with an adapter board to convert to UVC, which would be a hardware drop-in replacement for the old cameras. We also designed another system that would use an Ethernet converter on the Pi Zero, which would then plug into an Ethernet switch added to the enclosure.  

![V1 Camera CAD Partially Exploded](https://github.com/user-attachments/assets/6a4972c2-9003-4c97-aaec-19ddaaf5f946)
Version one of the camera that was potted, I went through a couple iterations before potting to make things easy, the trick I learned is to design a sort of skeleton frame to hold all of the wires and electronic parts that can be removed from the main potting box, so you can fill the box mostly with epoxy then slowly lower in the electronics assembly to reduce trapped air underneath the board I also used a vacum chamber to further reduce bubbles. Initially, we were also worried about heat dissipation from the Pi Zero. After learning some math, my calculations didn't give a clear answer, so I added a hole in the bottom that lines up with the Pi's CPU for better heat dissipation. This is tapped over during potting and removed once the epoxy sets. After assembly, we tested the Pi's equilibrium temperature, which was 33-34 Degrees C, well within the safe range. 

![Simplified Camera After Potting](https://github.com/user-attachments/assets/d45513d6-2ade-4aa3-9cd8-b0032d44a7ad)
This is the arducam after potting. This is the option we ended up going with because it got done first and worked really well for piloting. It was also much easier to pot. Another aspect of the design of these three systems is that they are fairly interchangeable, all cameras are mounted the same way, and they also all use the same CNC'd polycarbonate lens cover, which gets siliconed on after the epoxy. I did this to make construction more efficient and because all of these features worked well for the first version, so why change them.

![Camera with integrated Ethernet Board](https://github.com/user-attachments/assets/6539b97a-05d2-4f54-b805-5b0be35dbb74)
The camera was designed to be used with the Ethernet switch. This camera provided better quality; however, it was finished a week after the previous camera, and due to its increased complexity, it wasn't chosen. It is also much larger than the arducams. You can see pretty well in this picture how I approached potting the board: all wires are locked down as much as possible, and then the frame is slowly lowered into the main potting container to let the epoxy push the air out without it getting trapped. We might still need to use these cameras because we are having some difficulties with the lower-quality Arducams for computer vision. 





2024-2025 was my first year on the team, and I worked on the vertical profiler, photosphere, and some of the endcaps for the camera tube on the main bot.

![Verticle profilier](https://github.com/user-attachments/assets/4508c662-71b9-4c1f-a72f-76562dba7a78)

-Screenshot taken during livestream, in which you can see the profilier (Yellow arrow), the main robot (Blue arrow), and the photoshpere camera (red arrow)

The main project i worked on was the verticle profilier. It has been a task for a couple years and the previous year they never quite got it working, from what ive heard from the senior members the previous year it would go back down and never come back up again. It also had several major flaws that made it really inconvenient to use, such as annoying connectors that had to be unplugged and replugged every time it was disassembled, no on-off switch, which meant it needed to be disassembled extremely frequently. The additional twist on this year's mission was that it had to hover between 2-3m of depth for 45 seconds.

After a lot of testing, I found that the issue with the previous profilier was that the gearbox of the motor used to actuate the syringe would slip at high torque, which would lead to the issue where it would appear to work fine on the surface but would break during underwater trials. This was fixed by using a different motor with a more robust gearbox. To fix the connector issue, we swapped the UFL connectors with SMA connectors. To make turning it on and off simpler, I CNC'd a new endcap with an extra penetrator hole. Finally, to perform the hovering, we added a linear potentiometer to track the position of the syringe; with this, we could track the extension of the syringe in order to perform precise buoyancy changes. To do the hovering first, we found neutral buoyancy and then limited the syringe to a very small range of motion and had it change direction based on whether it was above or below the 2.5m point. This felt unsatisfying as a solution but worked well enough to get full points and since a simple solution is a good solution I left it at that and moved on to another project.

![Old profilier design](https://github.com/user-attachments/assets/37b38827-ba36-43f4-81d7-14b8e7d6fb80)

-2023 to 2024 profilier CAD

![New profilier design](https://github.com/user-attachments/assets/5e01d112-695b-4c9a-af01-c52ebc9c65e3)

-My revised version, almost everything has changed, and there is a lot more space for excess battery packs, which turned out not to be needed. Most of the parts were also 3D-printed, and only one needed support material, which I was quite happy about.

My next task was to help out with the camera tubes. They had quite a few flooding incidents, which were likely due to the custom endcaps. I spent a couple of sessions redoing the tolerances on the O-rings using Parker's O-Ring Handbook and manufacturing them on the CNC. After more troubleshooting, we discovered the issue was actually caused by the servo motor used, because the camera assembly is only supported by one endcap and twists out of the tube. My endcap did still end up being used, though.

![Endcap](https://github.com/user-attachments/assets/42149071-7de0-4fa5-b0a8-4c2985f5275f)

-Endcap

After this, school was over, and it was getting pretty close to the competition, so I was going in almost every day to help with testing. Around three weeks before we were set to go away to the world championship, I was at my cabin on the beach drying out my boat after an unsuccessful first sea trial, and I got a call about working on the photosphere, which was another non-ROV device like the vertical profiler. It was supposed to capture a 360 view of the pool to pick out targets on different props. Initially, we had discussed a system that used 180-degree cameras and could take it all in one go; however, this never ended up being done due to time constraints. However, instead, they suggested using a fishing camera and mounting it on a pan-tilt mechanism, which would complete the same task but with a couple fewer points. After getting back to town, I gave it a go and, after one and a half weeks, had a fully functioning version. It uses worm gear drives to slow down the output from two different DC gear motors that we had lying around from several years previously in order to maneuver the camera through the required 360 degrees. Its only issue was that if you over-rotated, the wires would get caught, and one of the 3d printed parts would snap and have to be replaced. I spent like half the time trying to fix this by making a clutch, which unfortunately wasn't very consistent, so in the end I just used a pink pipe cleaner to provide a visual indication of the extent of the range, and that worked great. Again ot the most satisfying engineering solutions, but if it works, it works. The Photosphere camera also ended up being very helpful as a third-person POV during competition runs.

![CAD](https://github.com/user-attachments/assets/49c748ab-2a68-4422-8a87-66192c38a400)

-Very pretty CAD image

![harsh reality](https://github.com/user-attachments/assets/d3e85d2c-0b2c-495d-bc5c-e0fd09732faa)

-Actual device, doesn't look great but does work perfectly





