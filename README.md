# Centralized Intelligence for Dynamic Swarm Navigation

[cite_start]An advanced autonomous navigation framework for robot swarms developed for the **Inter IIT Tech Meet 13, 2024**[cite: 2, 4]. [cite_start]This system provides optimized path planning, real-time object detection, and collaborative task execution in highly dynamic industrial environments such as warehouses and offices[cite: 11, 59].

---

## 📺 Project Demonstration
> **[Watch the Simulation Video Here](INSERT_YOUR_VIDEO_LINK_HERE)**
> *Demonstrating real-time swarm coordination, TD3/PPO obstacle avoidance, and LLM-based task assignment.*

---

## 🚀 Key Technical Features

* **Hybrid Swarm Architecture**:
    * [cite_start]**Master-Slave with Liveliness**: Features bidirectional communication for dynamic task reassignment and high coordination efficiency (optimal for 20-30 bots)[cite: 79, 81, 370].
    * [cite_start]**Complete Autonomous**: A decentralized model where each robot operates independently for maximum resilience and scalability (up to 50+ bots)[cite: 67, 70, 370].
* **Dual-Reinforcement Learning Strategy**:
    * [cite_start]**TD3 (Twin Delayed DDPG)**: Implemented for high-precision continuous control, effectively managing safety-exploitation trade-offs in unstructured environments[cite: 275, 425].
    * [cite_start]**PPO (Proximal Policy Optimization)**: Used for stable learning and reliable navigation in settings with frequently appearing/disappearing obstacles[cite: 27, 240, 242].
* **Edge-Optimized Perception**: 
    * [cite_start]Utilizes **YOLOv8 Nano** for real-time object detection and labeling on resource-constrained devices like Raspberry Pi 4[cite: 86, 92].
    * [cite_start]Achieved a **0.97 F1 Score** by refining the preprocessing pipeline with central cropping and data augmentation[cite: 374, 401].
* **Shared Intelligence Database**: 
    * [cite_start]Integrates a **NoSQL MongoDB** database to synchronize map data, robot telemetry, and prioritized task queues across the entire swarm[cite: 25, 159, 161].
* **Natural Language Control Interface**: 
    * [cite_start]An **LLM-based ChatBot** translates high-level user commands into actionable JSON inputs for robot coordination and task feedback[cite: 341, 344, 347].



## 🏗️ System Architecture

[cite_start]The solution utilizes a dual-layered architecture[cite: 20]:
* [cite_start]**Perception**: Integrated Camera, LiDAR, and Velodyne data for depth information and 3D mapping[cite: 63, 447, 449].
* [cite_start]**Decision Making**: Reward functions incentivizing goal-reaching (+100) while penalizing collisions (-100)[cite: 305, 307].
* [cite_start]**Communication**: Robots interact with the shared database over HTTP for real-time synchronization[cite: 470].

## 📊 Performance Benchmarks

| Metric | Complete Autonomous | Master-Slave (Liveliness) |
| :--- | :--- | :--- |
| **Task Allocation Time** | [cite_start]300-500 ms [cite: 370] | [cite_start]100-300 ms [cite: 370] |
| **Fault Tolerance** | [cite_start]High (No single failure point) [cite: 370] | [cite_start]Moderate (Dynamic Master election) [cite: 81, 370] |
| **Scalability** | [cite_start]50+ Bots [cite: 370] | [cite_start]20-30 Bots [cite: 370] |
| **Coordination** | [cite_start]High DB consistency required [cite: 370] | [cite_start]Centralized efficiency [cite: 370] |



## 🛠️ Tech Stack

* **Middleware**: ROS / ROS 2
* **Simulation**: Gazebo, RViz
* **Computer Vision**: YOLOv8n, OpenCV
* **Database**: MongoDB
* **Languages**: Python, C++

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