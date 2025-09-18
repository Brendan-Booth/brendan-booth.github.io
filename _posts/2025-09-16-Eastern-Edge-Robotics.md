---
title: "Eastern Edge Robotics"
date: 2025-09-16
---

Eastern Edge Robotics is a student design team with ~30 members that competes in the MATE ROV competition at the university level. For the competition, teams must design and build ROVs to perform specific tasks that change every year. 2024-2025 was my first year on the team, and I worked on the vertical profiler, photosphere, and some of the endcaps for the camera tube on the main bot.

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





