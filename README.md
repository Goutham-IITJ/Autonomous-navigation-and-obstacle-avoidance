# Centralized Intelligence for Dynamic Swarm Navigation

An advanced autonomous navigation framework for robot swarms developed for the **Inter IIT Tech Meet 13, 2024**. This system provides optimized path planning, real-time object detection, and collaborative task execution in highly dynamic industrial environments such as warehouses and offices.

---

## 📺 Project Demonstration
![KalyaniBharatForge-ezgif com-speed](https://github.com/user-attachments/assets/709b08ae-a6f9-42ad-a3c2-a1486d283956)


---

## 🚀 Key Technical Features

* **Hybrid Swarm Architecture**:
    * **Master-Slave with Liveliness**: Features bidirectional communication for dynamic task reassignment and high coordination efficiency (optimal for 20-30 bots).
    * **Complete Autonomous**: A decentralized model where each robot operates independently for maximum resilience and scalability (up to 50+ bots).
* **Dual-Reinforcement Learning Strategy**:
    * **TD3 (Twin Delayed DDPG)**: Implemented for high-precision continuous control, effectively managing safety-exploitation trade-offs in unstructured environments.
    * **PPO (Proximal Policy Optimization)**: Used for stable learning and reliable navigation in settings with frequently appearing/disappearing obstacles.
* **Edge-Optimized Perception**: 
    * Utilizes **YOLOv8 Nano** for real-time object detection and labeling on resource-constrained devices like Raspberry Pi 4.
    * Achieved a **0.97 F1 Score** by refining the preprocessing pipeline with central cropping and data augmentation.
* **Shared Intelligence Database**: 
    * Integrates a **NoSQL MongoDB** database to synchronize map data, robot telemetry, and prioritized task queues across the entire swarm.

---

## 🏗️ System Architecture



The solution utilizes a dual-layered architecture:
* **Perception**: Integrated Camera, LiDAR, and Velodyne data for depth information and 3D mapping.
* **Decision Making**: Reward functions prioritizing goal-reaching while penalizing collisions and unsafe behavior.
* **Communication**: Robots interact with the shared database over HTTP for real-time synchronization.

---

## 📊 Performance Comparison

| Metric | Complete Autonomous | Master-Slave (Liveliness) |
| :--- | :--- | :--- |
| **Task Allocation Time** | 300 - 500 ms | 100 - 300 ms |
| **Fault Tolerance** | High (No single failure point) | Moderate (Dynamic Master election) |
| **Scalability** | 50+ Bots | 20 - 30 Bots |

---

## 🛠️ Tech Stack

* **Middleware**: ROS / ROS 2
* **Simulation**: Gazebo, RViz
* **Computer Vision**: YOLOv8n, OpenCV
* **Database**: MongoDB
* **Languages**: Python, C++

---

## 📁 Repository Structure

```text
├── SRC/
│   ├── autobot_recog/      # Core YOLOv8n perception nodes
│   ├── turtlebot3/         # Robot hardware/driver configurations
│   ├── turtlebot3_msgs/    # Custom message and service definitions
├── launch/                 # ROS launch files for multi-bot initialization
├── urdf/                   # Robot and sensor model definitions
├── worlds/                 # Automated Gazebo environment generation
└── scripts/                # Task assignment and database logic
