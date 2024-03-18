
This dataset is a result of running simulations for a research paper - "Risk Dynamics: Unveiling Autonomous Drone Collision Risks through simulated skies of the Future"

The dataset consists of 16 folders - each corresponding to a different test scenario:

| # |World variables |Trajectory height selection|Flight level height (meters)|
|--|--|--|--|
|01| No ground variables enabled | Random |0.1|
|02| Only higher density zones enabled | Random |0.1|
|03| Only No-fly zones enabled | Random |0.1|
|04| All zones are enabled | Random |0.1|
|05| No ground variables enabled | Random |10|
|06| Only higher density zones enabled | Random |10|
|07| Only No-fly zones enabled | Random |10|
|08| All zones are enabled | Random |10|
|09| No ground variables enabled | HeadingHeight |10|
|10| Only higher density zones enabled | HeadingHeight |10|
|11| Only No-fly zones enabled | HeadingHeight |10|
|12| All zones are enabled | HeadingHeight |10|
|13| No ground variables enabled | HeadingHeight |0.1|
|14| Only higher density zones enabled | HeadingHeight |0.1|
|15| Only No-fly zones enabled | HeadingHeight |0.1|
|16| All zones are enabled | HeadingHeight |0.1|

Each of these 16 folders contains 6 sub-folders corresponding to different drone density targets ranging from 10 to 100 flights/h/km2

In each subfolder, there are 3 files:
`summary.csv` - general test scenario variables and summary of collision counts
`collisions.csv` - in-depth variables about each spot-on collision between UAVs
`flights.csv` - in-depth variables about each UAV flight

Columns in CSVs:
- `No fly zones` - ((x1, diameter1, y1) (x2 diameter2, y2)...) representation of the no fly areas in cylinder shape (could be not enabled)
- `Higher density zones` - ((x1, diameter1, y1) (x2 diameter2, y2)...) representation of the high density areas in cylinder shape (could be not enabled)
- `Range [km2]` - The area in square kilometers where the drones could spawn (squared area with center at (0, 0), infinite height)
- `Collision range [km2]` - The area in square kilometers where the collisions between drones are measured (squared area with center at (0, 0), infinite height)
- `No fly evasion` - boolean whether there are "no fly zones" present in the simulated world
- `Angle height` - boolean whether "angle height" principle is used when determining the drone flight height. If false a random flight height is assigned.
- `Collision evasion` - boolean whether a local collision evasion is performed
- `Flight level height` - the height of a flight level in meters
- `Simulation time frame [minutes]` - the length of the simulation
- `Density target` - the target for average density of drones over the simulation time frame
- `Flight count` - total flight count over the simulation time frame (summary.csv) or total flight count before the collision (collisions.csv)
- `Far collisions` - total far distance collisions over the simulation time frame
- `Medium collisions` - total medium distance collisions over the simulation time frame
- `Close collisions` - total close distance collisions over the simulation time frame
- `Spot on collisions` - total spot on collisions over the simulation time frame
- `Time flown` - the time it took the uav to fly from the Start position to the End position
- `Start/End position x/y/z` - the first (spawn) and last (despawn) position of the drone in the flight
- `Start/End/Current/Next/Target position type` - the type of position point in the flight (Ground, Air)
- `Distance` - the distance in a straight line between start and end points
- `Start/End time` - simulation time in seconds for start and end positions
- `Flight speed` - the flight speed of the uav
- `Collision level 0/1/2/3 max` - max concurrent count of collisions in corresponding collision level (level 3 equals spot on collision; level 0 equals area of interest)
- `Current position x/y/z` - the position of uav in the exact moment
- `Next position x/y/z` - the next position in the path of the uav
- `Target position x/y/z` - the target (last) position in the path of the uav
- `Flight state` - the state of the uav at the moment (Ground, Transit)
- `Aircraft diameter` - the dimensions of the uav as a diameter of a sphere
- `Total far/medium/close/spot on collisions` -  total corresponding level collision count before the collision
- `This/Other uav id` - the ids of a uav and the uav it collided to






