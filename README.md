# Manipulate-with-turtlesim-package-in-ROS2
This project demonstrates basic manipulation of turtlesim using ROS 2 commands, including moving turtles with the keyboard, spawning multiple turtles, and controlling their motion via topics.

---

## Operations Performed with turtlesim

### 1. Launch the First Turtle (turtle1)

Run the command:

ros2 run turtlesim turtlesim_node
1. Starts the turtlesim_node which opens a window showing a turtle.

This node controls the turtle’s movement and display.<img width="815" height="1071" alt="Screenshot 2025-07-27 153120" src="https://github.com/user-attachments/assets/83a20f61-801d-47f2-83ca-e3b94c6c73e9" />
2. Spawn a Second Turtle at a Specific Location
<img width="785" height="1073" alt="Screenshot 2025-07-27 153202" src="https://github.com/user-attachments/assets/f2b4d233-979f-48f0-a4c7-93338a191995" />
3. Move the Second Turtle in a Straight Line
Run the command:

bash
Copy code
ros2 topic pub /turtle2/cmd_vel geometry_msgs/Twist "{linear: {x: 2.0}, angular: {z: 0.0}}"
Sends velocity commands to move the second turtle forward.

No rotation (angular velocity is zero).

<img width="803" height="1089" alt="Screenshot 2025-07-27 153251" src="https://github.com/user-attachments/assets/2b9f0fd9-3b44-4d23-80ab-cbac7625e02e" />
4. Move the First Turtle Using Keyboard
Run the command:

bash
Copy code
ros2 run turtlesim turtle_teleop_key
This node reads keyboard input.

It publishes velocity commands to /turtle1/cmd_vel.

The turtlesim_node subscribes to this topic to move the turtle.

Use arrow keys to move the turtle.
<img width="835" height="1039" alt="Screenshot 2025-07-27 153850" src="https://github.com/user-attachments/assets/3e50395b-556c-4e9b-be8f-14cbb3f3f167" />

5. Make the First Turtle Move in a Circular Path
Run the command:

bash
Copy code
ros2 topic pub /turtle1/cmd_vel geometry_msgs/Twist "{linear: {x: 2.0}, angular: {z: 2.0}}"
Moves the first turtle forward while turning, resulting in a circular path.

<img width="894" height="1083" alt="Screenshot 2025-07-27 153949" src="https://github.com/user-attachments/assets/6c4e53df-cfaf-4fe3-8cae-68959a34df80" />
Difference Between a Node and a Topic in ROS 2
Node: A program or process that performs a specific function in ROS 2. Nodes can publish or subscribe to topics. Examples: turtlesim_node, turtle_teleop_key.

Topic: A named communication channel for sending messages between nodes. Nodes publish to or subscribe from topics. Example: /turtle1/cmd_vel topic for sending movement commands.



