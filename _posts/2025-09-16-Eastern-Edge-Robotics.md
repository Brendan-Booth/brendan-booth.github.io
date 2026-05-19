---
title: "Eastern Edge Robotics"
date: 2026-05-19
---

Eastern Edge Robotics is a student design team with ~30 members that competes in the MATE ROV competition at the university level. For the competition, teams must design and build ROVs to perform specific tasks that change every year. 

2025-2026 was my second year on the team, and because of that, I had more leadership opportunities and worked on many more projects. I worked on three main projects this year: underwater electric actuation, cameras, and the vertical profilier. Additionally, I was involved in troubleshooting and speeding up critical path components for the bot. 

The project I planned for this year was to develop a reliable, versatile system for tool actuation on the ROV. In 2024-2025, we only had static tooling, which works for many of the mission tasks, but limits us for some of the more complex tasks. To achieve this, I looked primarily at electric motor systems due to my prior experience with them and their ease of integration with the rest of our system; however, retrospectively, I should have looked seriously at pneumatic and hydraulic systems. After a lot more research, I came up with four options to try; first, I had some experiance with waterproofing brushed gear motors from my previous year on the team, and they had proven to be very reliable and versatile. Next was adding an encoder to the motor to have controlled rotation, which was initially planned for camera actuation. Next was buying underwater servos, which I have not had a lot of luck with in previous years, but a new member had mentioned a specific servo he had used in highschool which had worked great for him. Finally, I also looked into waterproofing a servo ourselves.

My first step for the DC motors was choosing a motor to waterproof. I chose https://www.digikey.ca/en/products/detail/sparkfun-electronics/15277/9995750 primarily due to its low cost, and circular output shaft, with the RPM and torque being close enough to what I wanted. The circular output shaft was important because I planned on putting an O-ring on the shaft for waterproofing. The low cost was also important because I planned on breaking a lot of them through testing. To waterproof the motor, I chose to CNC a HDPE cover to go over the motor head to hold the O-ring, and then potted the back of the motor. I followed the instructions in Parker's O-Ring handbook to get all my important dimensions, starting with my 6mm shaft and relatively low RPM. I followed a design table that specified a number 10 O-ring with an outer groove diameter of 9.12mm, and constructed the hat based on that. 

![Unpotted with Hat](https://github.com/user-attachments/assets/a527d433-c6e1-4431-9ee0-05ff412e97be)
First test fit of Motor not enough of the shaft available so made some small tweaks.

![V1 Potted](https://github.com/user-attachments/assets/f0c82b37-5c7e-4399-91dc-984b9b199558)
Second motor I potted, the first one I did, I forgot to fill some holes in the motor casing before potting, and the epoxy infiltrated the housing, preventing the rotor from rotating. This motor I also filled with mineral oil to further prevent water infiltration, which greatly reduced speed and torque. Additionally, the process of filling them involved drilling a small hole in the back of the motor to fit a syringe of mineral oil, this introduced some loose debris that caused damage to the motor after ~1.5 days of rotation. I did three of these mineral oil-filled motors which all failed in a simaler way failing after ~1 day of rotation. However on dissasembley I didn't find any water so I decided to forgo the mineral oil, and trust in the O-ring seal. 

![V5 on the robot](https://github.com/user-attachments/assets/25184a64-fdd0-4acc-9518-d895d320e0f9)
For the most recent version, I changed the hat for easier mounting, switched to a jacketed two-wire cable for better potting, and integrated strain relief into the potting frame. Tonight (May 19th) will be its first test for an actual competition run, but it has already spent ~48 hours at 4m with no RPM drop, so I am optimistic. 




2024-2025 was my first year on the team, and I worked on the vertical profiler, photosphere, and some of the endcaps for the camera tube on the main bot.

![Verticle profilier](https://github.com/user-attachments/assets/4508c662-71b9-4c1f-a72f-76562dba7a78)

-Screenshot taken during livestream, in which you can see the profilier (Yellow arrow), the main robot (Blue arrow), and the photoshpere camera (red arrow)

The main project i worked on was the verticle profilier. It has been a task for a couple years and the previous year they never quite got it working, from what ive heard from the senior members the previous year it would go back down and never come back up again. It also had several major flaws that made it really inconvenient to use, such as annoying connectors that had to be unplugged and replugged every time it was disassembled, no on-off switch, which meant it needed to be disassembled extremely frequently. The additional twist on this year's mission was that it had to hover between 2-3m of depth for 45 seconds.

After a lot of testing, I found that the issue with the previous profilier was that the gearbox of the motor used to actuate the syringe would slip at high torque, which would lead to the issue where it would appear to work fine on the surface but would break during underwater trials. This was fixed by using a different motor with a more robust gearbox. To fix the connector issue, we swapped the UFL connectors with SMA connectors. To make turning it on and off simpler, I CNC'd a new endcap with an extra penetrator hole. Finally, to perform the hovering, we added a linear potentiometer to track the position of the syringe; with this, we could track the extension of the syringe in order to perform precise buoyancy changes. To do the hovering first, we found neutral buoyancy and then limited the syringe to a very small range of motion and had it change direction based on whether it was above or below the 2.5m point. This felt unsatisfying as a solution but worked well enough to get full points and since a simple solution is a good solution I left it at that and moved on to another project.

![Old profilier design](https://github.com/user-attachments/assets/37b38827-ba36-43f4-81d7-14b8e7d6fb80)

-2023 to 2024 profilier CAD

![New profilier design](https://github.com/user-attachments/assets/5e01d112-695b-4c9a-af01-c52ebc9c65e3)

-My revised version, almost everything has changed, and there is a lot more space for excess battery packs, which turned out not to be needed. Most of the parts were also 3D printed, and only one of them needed support material, which I was quite happy about.

My next task was to help out with the camera tubes. They had quite a few flooding incidents, and we thought that this was probably due to the custom endcaps. I spent a couple of sessions redoing the tolerances on the O-rings using Parker's O-Ring Handbook and manufacturing them on the CNC. After some more troubleshooting, we discovered the issue was actually due to the servo motor used, due to the camera assembly being only supported by one endcap, and twisting it out of the tube. My endcap did still end up being used, though.

![Endcap](https://github.com/user-attachments/assets/42149071-7de0-4fa5-b0a8-4c2985f5275f)

-Endcap

After this, school was over, and it was getting pretty close to the competition, so I was going in almost every day to help with testing. Around three weeks before we were set to go away to the world championship, I was at my cabin on the beach drying out my boat after an unsuccessful first sea trial, and I got a call about working on the photosphere, which was another non-ROV device like the vertical profiler. It was supposed to capture a 360 view of the pool to pick out targets on different props. Initially, we had discussed a system that used 180-degree cameras and could take it all in one go; however, this never ended up being done due to time constraints. However, instead, they suggested using a fishing camera and mounting it on a pan-tilt mechanism, which would complete the same task but with a couple fewer points. After getting back to town, I gave it a go and, after one and a half weeks, had a fully functioning version. It uses worm gear drives to slow down the output from two different DC gear motors that we had lying around from several years previously in order to maneuver the camera through the required 360 degrees. Its only issue was that if you over-rotated, the wires would get caught, and one of the 3d printed parts would snap and have to be replaced. I spent like half the time trying to fix this by making a clutch, which unfortunately wasn't very consistent, so in the end I just used a pink pipe cleaner to provide a visual indication of the extent of the range, and that worked great. Again ot the most satisfying engineering solutions, but if it works, it works. The Photosphere camera also ended up being very helpful as a third-person POV during competition runs.

![CAD](https://github.com/user-attachments/assets/49c748ab-2a68-4422-8a87-66192c38a400)

-Very pretty CAD image

![harsh reality](https://github.com/user-attachments/assets/d3e85d2c-0b2c-495d-bc5c-e0fd09732faa)

-Actual device, doesn't look great but does work perfectly





