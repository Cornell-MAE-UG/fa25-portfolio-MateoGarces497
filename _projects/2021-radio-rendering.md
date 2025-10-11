---
layout: project
title: Mechanical System Optimization Lifting the Maximum Weight to Maximum Height
description: Optimized Lifting Mechanism Design
technologies: Pencil and Paper
image: /assets/images/Diagram.png
---


For ENGRD2020: Statics and Mechanics of Solids, we were asked to design a frame/mechanism to lift the maximum possible weight to the highest possible height, given a 2D design space of 150cm long and 50cm tall, a rigid bar of a fixed length, 3 pin supports of which two need to be mounted on the ground, and a linear actuator picked from a manufacturer catalog. This project involved sketching, CAD modeling, and mechanical analysis to create an optimized lifting system. 

The final mechanism design included a rigid 1.5 m lever pinned to the ground at x = 0m, supporting a load 1.5 m away ath the end of the lever. The actuator was pinned to the ground at x = 0.05m and to the lever 0.013 m away from the base. Both the actuator and lever were free to rotate about their bases, creating a system in which the upward moment force from the actuator strictly opposed the moment created by the applied load.

![Shaded rendering of earlier version]({{ "/assets/images/Tolomatic.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}

For this design, a Tolomatic IMA55 integrated actuator with a roller-nut screw and a 3-stack motor was selected for maximum peak thrust (~2300N). I factored in the dimensions of the actuator to ensure it fit within our design constraints of 150 cm x 50 cm. 

Next, a moment balance about the lever ground pin was performed to maximize lift height and applied load magnitude. This allowed me to calculate the actuator force required for different applied loads and lever angles. Because the actuator is pinned and only exerts force along its axis, the actual lifting force is determined by the component of the load that acts in that same direction. Importantly, the failure point of this mechanism occurs when the projection of the weight component onto the actuator's line of action is smallest, or in other words fully contracted. To calculate the maximum applied load, I calculated the moment balance about the ground pin in this specific scenario.

This project taught me how to approach a design problem by balancing theoretical analysis with practical engineering constraints. I learned to use statics and geometry to optimize a mechanism’s performance, interpret actuator specifications from a manufacturer catalog, and evaluate tradeoffs between mechanical advantage, stroke length, and structural limits. The process reinforced the importance of precision in modeling assumptions and highlighted how small geometric changes can drastically affect force transmission and load capacity.


