# 🚀 SLAM-Based IoT Rover

An **autonomous IoT rover** designed to perform **Simultaneous Localization and Mapping (SLAM)** using 2D LiDAR and ROS 2. The project integrates real-time mapping, autonomous navigation, path planning, obstacle avoidance, and motor control to develop a self-navigating robotic platform.

## 🌟 Features

- 🗺️ **Real-Time 2D Mapping:** Generate maps of the surrounding environment using LD24 LiDAR and SLAM.
- 🧭 **Autonomous Navigation:** Perform path planning and navigation using ROS 2 Nav2.
- 🚧 **Obstacle Detection and Avoidance:** Detect obstacles and navigate around them using sensor data.
- ⚙️ **Motor Control:** Control N20 encoder motors using the SmartElex L298N motor driver.
- 📡 **IoT Integration:** Use ESP32 for data logging and remote communication.
- 📊 **Visualization:** Visualize maps, robot position, LiDAR scans, and navigation data using RViz.
- 🤖 **Hardware Implementation:** Integrate software and physical components to develop and test an autonomous rover.

---

## 🔧 Tools and Technologies

### 🛠️ Hardware

| Component | Purpose |
|---|---|
| Raspberry Pi 4 | Main controller running ROS 2 |
| LD24 LiDAR | 2D environmental scanning and mapping |
| N20 Encoder Motors | Wheel movement and odometry tracking |
| SmartElex L298N Motor Driver | Motor speed and direction control |
| ESP32 | Data logging and remote communication |

### 💻 Software

- **Operating System:** Ubuntu
- **Robotics Middleware:** ROS 2
- **SLAM:** GMapping / SLAM Toolbox, depending on the configured ROS 2 implementation
- **Navigation:** ROS 2 Nav2
- **Visualization:** RViz
- **Programming Languages:** Python and C++

---

## 🏗️ System Architecture

The rover combines LiDAR-based environmental perception, wheel odometry, mapping, and autonomous navigation.

1. **Perception:** The LD24 LiDAR collects 2D laser scan data.
2. **Localization and Mapping:** SLAM estimates the robot's position while building a map of its environment.
3. **Path Planning:** Nav2 plans a path toward the specified goal.
4. **Obstacle Avoidance:** The navigation system uses sensor and costmap information to avoid obstacles.
5. **Motor Control:** The motor driver controls the N20 encoder motors based on movement commands.
6. **IoT Communication:** The ESP32 supports data logging and remote communication.

---

## 📥 Installation and Setup

### Prerequisites

Ensure the following are available:

- Raspberry Pi 4 or a compatible development system.
- A compatible Ubuntu installation.
- ROS 2 and the required navigation and SLAM packages.
- LD24 LiDAR, motor driver, encoder motors, and associated hardware for physical deployment.

> **Compatibility note:** Ubuntu 20.04 is not the standard platform for ROS 2 Jazzy. ROS 2 Jazzy targets Ubuntu 24.04 on supported Ubuntu architectures. Verify your Ubuntu and ROS 2 versions before installing dependencies.

### 1. Clone the Repository

```bash
git clone https://github.com/sandeep-1901/AUTONOMOUS-NAVIGATION-SYSTEM-BASED-ON-2D-LiDAR-SLAM.git

cd AUTONOMOUS-NAVIGATION-SYSTEM-BASED-ON-2D-LiDAR-SLAM
```

### 2. Install Dependencies

For a ROS 2 Jazzy installation, update the package lists and install the dependencies supported by your ROS distribution.

```bash
sudo apt update
sudo apt install python3-rosdep
```

Initialize `rosdep` if it has not already been initialized:

```bash
sudo rosdep init
rosdep update
```

Install the dependencies declared by the workspace, if a ROS package workspace is present:

```bash
rosdep install --from-paths . --ignore-src -r -y
```

Source the appropriate ROS 2 installation:

```bash
source /opt/ros/jazzy/setup.bash
```

**Note:** GMapping is primarily associated with ROS 1. For ROS 2, SLAM Toolbox is a common choice. Use the SLAM implementation and package names supported by your actual project configuration.

### 3. Build the ROS 2 Workspace

If the repository contains a ROS 2 workspace with a `src` directory, build it using:

```bash
cd <workspace_directory>

colcon build --symlink-install

source install/setup.bash
```

Replace `<workspace_directory>` with the actual workspace path in your repository.

### 4. Launch SLAM Mapping

To launch the mapping configuration, use the launch file provided by your workspace. For example, if the package and launch file exist as described below:

```bash
ros2 launch bumperbot_bringup simulated_robot.launch.py use_slam:=true
```

This mode is intended to enable SLAM for mapping the environment.

### 5. Launch Localization

To run the localization configuration, use the appropriate launch file and localization parameters provided by your workspace.

For example:

```bash
ros2 launch bumperbot_bringup simulated_robot.launch.py
```

The exact command and configuration depend on whether the launch file starts localization, simulation, or another operating mode. Configure the map and localization parameters as required.

> **Important:** The launch commands above are examples based on the intended workflow. Confirm the package names, launch filenames, and supported arguments against the actual repository before running them.

---

## 🧪 Testing and Validation

- [ ] Verify LiDAR data is being published and visualized.
- [ ] Confirm that SLAM generates a consistent 2D map.
- [ ] Validate robot odometry from encoder feedback.
- [ ] Test autonomous navigation to a target location.
- [ ] Verify obstacle detection and avoidance.
- [ ] Test motor direction and speed control.
- [ ] Validate ESP32 communication and data logging.
- [ ] Test the complete system on physical hardware.

---

## 🚀 Future Improvements

- 🔭 **3D SLAM:** Extend mapping capabilities with additional sensors.
- 🧠 **Intelligent Navigation:** Explore machine learning for advanced navigation behaviours.
- 🚧 **Improved Obstacle Avoidance:** Enhance local planning and dynamic obstacle handling.
- 📡 **Remote Monitoring:** Add a dashboard for rover status and sensor information.
- 🔋 **Power Optimization:** Improve battery management and runtime.
- 🗺️ **Navigation Enhancements:** Improve localization accuracy and path-planning performance.

---

## 🤝 Contributing

Contributions, bug reports, and feature suggestions are welcome!

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a pull request describing your improvements.

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 👤 Author

**Kaushik Gupta** — Embedded and Software Engineer

GitHub: [@Kaushikgupta469](https://github.com/Kaushikgupta469)

---

*Building autonomous robotics systems through embedded engineering, sensor integration, and ROS 2.* 🤖
