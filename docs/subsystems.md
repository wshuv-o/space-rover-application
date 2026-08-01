# Subsystem requirements

Condensed from the full specification (Space Rover Application.pdf). Each subsystem below has its own use case, class, sequence, and activity diagram under [diagrams/](../diagrams/).

## 1. Hardware Maintenance (priority: high)

Pre-mission system checkup is mandatory. If a failure is detected mid-mission the rover reports to base and attempts a reboot; if the reboot does not clear it, the rover returns to the base station for repair, then resumes the mission once healthy. Health tracking covers sensors, wheels, and actuators, with a maintenance log kept per intervention.

## 2. Mission Status (priority: high)

Continuous situational reporting: vehicle status (tire pressure, battery health and percentage), mission progress with estimated completion time, and predicted mobility and visibility. Weather, route, and atmospheric conditions feed the same view so the operator can abort or reroute before damage happens.

## 3. Mobility (priority: high)

Two operating modes. Automatic mode navigates diverse terrain with all-terrain drive and obstacle avoidance algorithms. Manual mode gives the operator speed, direction, and stop control, backed by live camera feeds and telemetry. A safety protocol governs mode transitions so a handover can never leave the rover in a conflicted state.

## 4. Terrain Scanning and Way Pointing (priority: high)

Onboard sensors (cameras, radar) gather terrain data, which is processed into a detailed terrain map with obstacle detection. Waypoints are generated from the map according to mission objectives, and a path planning algorithm produces an efficient route between them. Safety measures include collision avoidance, safe stops, and mission aborts.

## 5. Weather Data Collection (priority: low)

Dedicated sensors measure wind speed, atmospheric pressure, temperature, and UV radiation. Real-time acquisition algorithms feed a timestamped data log, and the collected data is transmitted to mission control for analysis and forecasting.

## 6. Communication (priority: medium)

The communication module initializes whenever the rover leaves idle or starts a mission, then maintains real-time data streaming with the base station, which relays to the earth station for task exchange and scientific findings. If contact with base is lost during a mission, the rover heads toward the last known communication point and falls back to DTN (Delay-Tolerant Networking) protocols. The module also supports direct communication with accompanying drones for collaborative tasks.

## 7. Soil Sample Collection (priority: low)

Find a suitable site, scan the surface to confirm collection is feasible (relocate if not), drill to a set depth, collect and store the sample in containers for analysis, then reset to exploration mode.

## Process model

The project deliberately follows the Waterfall model rather than Agile. The reasoning: space missions have well-defined, stable requirements and hard safety and compliance obligations, which favor a plan-driven process with heavy documentation over adaptive iteration. The tradeoff discussion (Agile, iterative, and hybrid alternatives) is in the PDF, section 1.
