# Test Results — TurtleBot3 Autonomous Navigation

## 1. Test Environment

| Component | Configuration |
|---|---|
| Operating System | Ubuntu 24.04 LTS |
| ROS 2 Distribution | Jazzy |
| Simulator | Gazebo Sim |
| Robot | TurtleBot3 |
| Navigation Stack | ROS 2 Navigation2 (Nav2) |
| Visualization | RViz2 |
| Navigation Parameters | Default Nav2 configuration |
| Localization | Map-based localization using AMCL |

## 2. Test Summary

The official TurtleBot3 simulation and Nav2 stack were launched using the default configuration. ROS 2 topic publication and sensor/odometry data were checked. The robot's initial pose was estimated in RViz2, and multiple navigation goals were sent through the RViz2 interface.

The robot successfully reached the selected goals during the observed test runs.

## 3. Test Cases

| Test ID | Test Description | Expected Result | Observed Result | Status |
|---|---|---|---|---|
| TC-01 | Launch the TurtleBot3 simulation with Nav2 | Gazebo, RViz2, and the navigation stack initialize successfully | Simulation and navigation stack started successfully | PASS |
| TC-02 | Verify ROS 2 topic publication and data | Relevant topics publish data that can be inspected | Topic publication and data were checked and appeared correct | PASS |
| TC-03 | Initialize the robot's pose in RViz2 | The robot's estimated pose is established on the map | Initial pose was set using the 2D Pose Estimate tool | PASS |
| TC-04 | Send a navigation goal through RViz2 | Nav2 plans a route and autonomously moves the robot toward the goal | The robot reached the selected goal successfully | PASS |
| TC-05 | Repeat navigation with multiple goals | The robot can navigate to different selected destinations | Two to three goals were sent, and the robot reached them successfully | PASS |
| TC-06 | Verify obstacle-aware navigation | The robot selects a traversable route around relevant obstacles | Record the observed result after confirming that a goal required navigating around an obstacle | NOT YET VERIFIED |

**Note:** TC-06 should be marked PASS only if the test visibly demonstrated obstacle avoidance. Successful arrival at multiple goals alone does not establish that obstacle avoidance was tested.

## 4. Test Procedure

1. Installed the required TurtleBot3 simulation and Nav2 packages.
2. Launched the simulation using the provided Nav2 simulation launch file and default parameters.
3. Checked relevant ROS 2 topics and inspected their published data.
4. Opened Gazebo and RViz2 side by side to observe the simulation and navigation state.
5. Initialized the robot's estimated pose using the 2D Pose Estimate tool in RViz2.
6. Selected navigation goals using the Nav2 Goal tool.
7. Observed the robot navigating to the selected destinations.
8. Repeated the goal-navigation procedure and recorded the successful runs.

## 5. Evidence

- **Screen recording:** Demonstrates the running simulation, pose initialization, goal selection, and autonomous navigation.
- **Screenshot:** Shows the Gazebo simulation and RViz2 visualization side by side.
- **Configuration:** The tests used the default Nav2 configuration without custom parameter modifications.

Evidence files and links are maintained in the project README.

## 6. Conclusion

The tests demonstrated successful integration of the official TurtleBot3 simulation with ROS 2 Nav2 on ROS 2 Jazzy. Topic publication and data were inspected, the robot's estimated pose was initialized in RViz2, and multiple navigation goals were reached successfully.

The implementation uses existing ROS 2 packages and default navigation parameters. The results demonstrate the basic autonomous navigation workflow. Obstacle avoidance should be considered verified only after a test explicitly demonstrates a route around an obstacle.

## 7. Scope and Limitations

- No custom navigation algorithms were implemented.
- No Nav2 parameters were modified or tuned.
- Testing was conducted in simulation rather than on a physical robot.
- Navigation performance was assessed through observed goal completion; quantitative measures such as navigation time, path length, and goal-position error were not recorded.
- Dynamic obstacle avoidance was not separately evaluated unless explicitly demonstrated in the recorded tests.
