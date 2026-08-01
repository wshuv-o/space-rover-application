# Test plan

Twenty scenario test cases across six modules, condensed from the full specification (pages 31 to 54 of the PDF, which carry the step-by-step procedures, preconditions, and expected postconditions).

| ID | Module | Test title | Priority |
|---|---|---|---|
| COMM_01 | Communication | Verify initialization of communication module | High |
| COMM_02 | Communication | Verify real-time data streaming mechanism | High |
| COMM_03 | Communication | Verify handling of communication failures | Medium |
| MISS_01 | Mission Status | Verify real-time mission progress update | High |
| MISS_02 | Mission Status | Verify real-time mission status update | Medium |
| MISS_03 | Mission Status | Check vehicle status | Medium |
| SOILC_01 | Soil Sample Collection | Search for a suitable location | High |
| SOILC_02 | Soil Sample Collection | Sample collection | Medium |
| SOILC_03 | Soil Sample Collection | Sample data analyzer | Medium |
| TR001 | Terrain Scanning | Terrain data collection | High |
| TR002 | Terrain Scanning | Terrain map generation for Martian exploration | High |
| TR003 | Terrain Scanning | Waypoint generation for Martian exploration | High |
| TR004 | Terrain Scanning | Path planning for Martian exploration | High |
| TR005 | Terrain Scanning | Obstacle avoidance in asteroid belt navigation | High |
| THM01 | Hardware Maintenance | Sensor calibration and data measurement | High |
| THM02 | Hardware Maintenance | Verify system checkup before mission | High |
| THM03 | Hardware Maintenance | Verify handling system failure during mission | High |
| MOB_01 | Mobility | Verify mobility of the rover | High |
| MOB_02 | Mobility | Verify turning capability of the rover | Medium |
| MOB_03 | Mobility | Verify obstacle avoidance capability of the rover | High |

The failure-path cases are the interesting ones: COMM_03 exercises the DTN fallback and return-to-last-contact behavior, THM03 exercises mid-mission failure, reboot, and return-to-base repair.
