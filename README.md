# catch-the-turtle-ros2
A ROS2 project using Turtlesim where a robot autonomously catches turtles.  This project demonstrates publishers, subscribers, services, and custom messages in ROS2 with Python.

# ROS2 Turtle Catcher 🐢

## Overview
This project demonstrates a **ROS2-based turtle catching simulation** using the classic `turtlesim` package.  
A main robot (`turtle1`) autonomously chases and catches other turtles that spawn randomly in the simulation.  

It is my **first ROS2 project**, designed to learn and practice:
- Publishers & Subscribers  
- Services & Clients  
- Custom ROS2 messages  
- Parameter handling  
- Simulation control with Turtlesim  

---

## How It Works
The project runs with **two main nodes**:

### 1. `TurtleSpawnerNode`
- Spawns turtles at random positions in the Turtlesim environment.  
- Publishes all alive turtles on the `alive_turtles` topic using a custom message `TurtleArray`.  
- Provides a service `catch_turtle` that removes a turtle when caught.  

### 2. `TurtleControllerNode`
- Subscribes to the robot’s pose (`/turtle1/pose`) and the list of `alive_turtles`.  
- Selects the **closest turtle** as the target.  
- Publishes velocity commands (`/turtle1/cmd_vel`) to move towards the target.  
- Calls the `catch_turtle` service when close enough.  
- **Bonus:** Dynamically changes the Turtlesim background color every time a turtle is caught 🎨.  

---

## Skills Learned
- Writing **ROS2 Python nodes**  
- Creating **custom messages and services**  
- Using **topics, services, and parameters** in ROS2  
- Controlling robots in simulation (Turtlesim)  
- Structuring a multi-node robotics project  

---

## Demo
📽️ Demo videos are available showing the turtle catching other turtles in real time.  
(You can embed a YouTube/GIF link here once uploaded.)  

---

## Project Structure
ros2_ws/
├── src/
│ ├── my_robot_interfaces/ # Custom messages & services
│ └── my_robot_bringup/ # Nodes & launch files
│ ├── turtle_controller.py # Main robot controller
│ └── turtle_spawner.py # Spawns and manages turtles


---

## How to Run

### 1. Clone the repo
```bash
git clone https://github.com/<your-username>/ros2-turtle-catcher.git

2. Build the workspace
colcon build
source install/setup.bash

3. Run the simulation
Start Turtlesim:

bash
Copy code
ros2 run turtlesim turtlesim_node
Run the spawner node:

bash
Copy code
ros2 run my_robot_bringup turtle_spawner
Run the controller node:

bash
Copy code
ros2 run my_robot_bringup turtle_controller
Example Output
New turtles spawn randomly:

css
Copy code
[INFO] [turtle_spawner]: New alive turtle: turtle3
Controller targeting turtles:

less
Copy code
[INFO] [turtle_drawing]: Now targeting: turtle3
[INFO] [turtle_drawing]: Turtle turtle3 was caught successfully!
[INFO] [turtle_drawing]: Background changed to RGB(123, 45, 200)

###### Tech Stack
1.ROS2 Jazzy (works on Humble/Foxy with minor changes)
2.Python
3.Turtlesim

######License

This project is licensed under the MIT License.
Feel free to use and modify for learning and research purposes.

---

⚡ This README is **professional and recruiter-friendly**. Once you upload videos/GIFs later, you can just edit the **Demo** section.  

Do you also want me to prepare a **LICENSE file (MIT)** so your repo looks fully complete?

