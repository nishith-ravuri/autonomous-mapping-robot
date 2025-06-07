# 🤖 Autonomous Mapping Robot (ROS 2 Simulation)

This project simulates a mobile robot that autonomously explores and maps an environment using **SLAM Toolbox**, **Nav2**, and **explore_lite** in **Gazebo**, based on the TurtleBot3 platform.

---

## 🛠️ Dependencies

Make sure these packages are installed:

```bash
sudo apt install \
  ros-humble-turtlebot3 \
  ros-humble-turtlebot3-gazebo \
  ros-humble-slam-toolbox \
  ros-humble-nav2-bringup \
  ros-humble-explore-lite
```

Also build this workspace:

```bash
cd ~/autonomous_mapping_ws
colcon build --symlink-install
source install/setup.bash
```

🚀 How to Run the System (4 Terminals)
Each of the following steps must be run in a separate terminal.

⚠️ Before running commands in any terminal, always source your workspace:

```bash
source ~/autonomous_mapping_ws/install/setup.bash
```

🖥️ Terminal 1: Launch the Simulation in Gazebo
```bash 
export TURTLEBOT3_MODEL=waffle_pi
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```
💡 You can also use turtlebot3_house.launch.py or another custom world if preferred.

.

🧭 Terminal 2: Launch SLAM Toolbox
```bash
ros2 launch slam_toolbox online_async_launch.py use_sim_time:=true
```

🗺️ Terminal 3: Launch Nav2 Navigation Stack
```bash
ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=true
```


🤖 Terminal 4: Launch Autonomous Exploration (explore_lite)
```bash
ros2 launch explore_lite explore.launch.py
```

📂 Repository Structure
```bash
autonomous_mapping_ws/
├── src/
│   ├── m-explore-ros2/
│   └── turtlebot3/
├── .gitignore
└── README.md
```



