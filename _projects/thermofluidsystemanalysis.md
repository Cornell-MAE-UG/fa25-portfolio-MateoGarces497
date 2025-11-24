---
layout: project
title: Heat Exchanger Portfolio Assignment
description: A thermodynamic analysis of a water–water heat exchanger operating in parallel and counterflow configurations.
technologies: Heat Exchanger
image: /assets/images/HXPhoto.png
permalink: /portfolio/MateoGarces497/thermofluidsystemanalysis/

---

This project investigates the performance of a double-pipe heat exchanger operating in both parallel flow and counterflow configurations. The device consists of two separate water flow channels, labeled 1→2 and 3→4, through which hot and cold water streams circulate without mixing. The primary goal was to measure inlet and outlet temperatures for both streams under different operating modes and evaluate heat-transfer performance using experimental data.

The apparatus included a heat exchanger, two submersible pumps, four buckets, ice, water, a Styrofoam-insulated cold reservoir, an immersion heater to generate a hot reservoir, one thermocouple, four thermometers, and food dye for flow visualization. The hot reservoir was heated using the immersion heater and circulated using a pump. The cold reservoir was prepared with ice water and insulated with Styrofoam. Each reservoir was filled completely at the start of the experiment to maximize run time. Dye was added to one reservoir to confirm proper routing of the flows. The system was run first in counterflow, then in parallel flow, with temperatures recorded at the heat-exchanger inlet and outlet on both sides as well as in the reservoirs.

Heat transfer occurs between the two fluids through the metal wall separating the flow paths. In counterflow, the hot and cold streams move in opposite directions, maintaining a high temperature gradient along the entire length of the heat exchanger. In parallel flow, both streams enter from the same side and move in the same direction, resulting in a lower average temperature gradient and generally poorer heat-transfer performance. After steady operation was reached, the inlet and outlet temperatures of both streams were recorded for multiple runs.

A consolidated table of all experimental data is shown.

<hr>

<div style="text-align: center;">
  <img src="{{ '/assets/images/HX_Table.png' | relative_url }}" 
       alt="Shaded rendering of earlier version" 
       style="width: 400px; display: block; margin: 0 auto;">
</div>

Heat-Transfer Calculations (First Two Experiments)

All heat-transfer values below are expressed per kg of water:

<hr>

<div style="text-align: center;">
  <img src="{{ '/assets/images/HX_Calcs.png' | relative_url }}" 
       alt="Shaded rendering of earlier version" 
       style="width: 400px; display: block; margin: 0 auto;">
</div>

These values show that parallel flow transferred significantly less heat than counterflow, confirming theoretical expectations.

Discussion and Interpretation

Across both sets of experiments, counterflow operation consistently produced larger temperature changes in both streams, indicating greater heat-transfer rates and higher thermal effectiveness. This occurs because counterflow maintains a larger mean temperature difference along the heat-exchanger length. Parallel flow, in contrast, experiences rapid temperature convergence, reducing the driving force for heat transfer.

In real-world systems, heat exchangers are found in power-plant condensers, car radiators, refrigeration systems, chemical processing equipment, and HVAC units. Ideally, we model heat exchangers as adiabatic, meaning all heat transfer occurs only between the two fluids. In practice, however, some heat leaks into the surroundings, especially when hardware is uninsulated, as in this experiment. This explains why the hot-side and cold-side calculated heat-transfer values do not match perfectly.

Steady-state was approached but not perfectly achieved during the experiments, as indicated by drifting reservoir temperatures. Steady state could be improved by pre-circulating water before taking measurements, fixing the pumps at constant flow rates, further insulating the reservoirs, or using larger water volumes to reduce temperature drift.

Overall, the results clearly demonstrate that counterflow heat exchangers outperform parallel-flow heat exchangers, both in theory and in practice, due to superior temperature-gradient utilization and lower entropy generation.

