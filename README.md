# ROS2 + RViz + TSX Web UI: Beginner Project

A beginner-friendly project to control a robot in RViz via a TypeScript (TSX) web UI and optionally a backend service.

## Project Overview

* Move the robot in RViz using UI buttons/sliders.
* Backend automation can calculate positions and publish to the same ROS2 topics.
* RViz visualizes all movements in real time.
* Focus is on learning ROS2 topics, message publishing, and the separation of control vs visualization.

## Minimal Tech Stack

**Robotics / Middleware:**

* [ROS2](https://docs.ros.org/en/rolling/index.html)
* RViz2
* rosbridge_suite (WebSocket bridge)

**Frontend:**

* React + TypeScript (TSX)
* Vite (or similar bundler)
* roslibjs (WebSocket client)

**Backend (Optional):**

* Python (`rclpy`) or Node.js (`rclnodejs`) to publish messages to ROS2 topics

## Core Concepts

* ROS2: Middleware for robot software communication.
* Topics: Channels for publishing and subscribing messages.
* RViz: Visualization tool that listens to topics.
* rosbridge_suite: WebSocket bridge allowing the browser to interact with ROS2.
* Frontend & backend publish messages; RViz only visualizes.

## Project Requirements

1. Connect a TSX web UI to ROS2 using WebSockets (rosbridge_suite).
2. Provide UI controls to move the robot.
3. Backend service can optionally publish automated movements.
4. Publish messages (PoseStamped or Marker) to ROS2 topics.
5. Visualize robot movements in RViz.
6. Handle connection lifecycle and verify messages reach ROS2.

## Minimal Setup for Beginners

### 1. Install ROS2

Follow the official guide: [ROS2 Installation](https://docs.ros.org/en/rolling/Installation.html)

### 2. Source ROS2

```bash
source /opt/ros/<your_distro>/setup.bash
```

Replace `<your_distro>` with your ROS2 version (e.g., humble, iron).

### 3. Launch rosbridge_suite

```bash
ros2 launch rosbridge_server rosbridge_websocket_launch.xml
```

* Starts a WebSocket server at `ws://localhost:9090`.

### 4. Start RViz2

```bash
rviz2
```

* Add displays subscribing to your topics (e.g., `/demo_pose`).

### 5. Frontend Setup

```bash
npm create vite@latest
cd <project_name>
npm install
npm install roslib
```

* Use `roslibjs` to publish messages from UI buttons/sliders.

### 6. Backend Setup (Optional)

* Python: use `rclpy` to create a node and publish PoseStamped messages.
* Node.js: use `rclnodejs` for ROS2 communication.

### 7. Test Workflow

* Connect UI to `ws://localhost:9090`.
* Publish messages from UI and/or backend.
* Verify updates in RViz.

## Workflow Example

1. User clicks **Move Forward** → publishes PoseStamped to `/demo_pose`.
2. RViz visualizes the movement.
3. Backend can publish PoseStamped to move robot automatically.
4. UI and RViz remain synced.

## Suggested Learning Goals

* Understand ROS2 topics and message types.
* Use roslibjs to publish messages from a browser.
* Learn distinction between control (UI/Backend) and visualization (RViz).
* Explore PoseStamped and Marker messages.
* Practice debugging WebSocket, frontend, backend, and ROS2 communication.

## Notes

* Implementation details are left to the developer.
* Start minimal: one pose, simple UI, verify RViz updates.
* Expand gradually: automated backend, multiple poses, path planning, or markers.

## References

* [ROS2 Documentation](https://docs.ros.org/en/rolling/index.html)
* [rosbridge_suite Documentation](http://wiki.ros.org/rosbridge_suite)
* [RViz User Guide](https://docs.ros.org/en/rolling/Tutorials/Intermediate/RViz/RViz-User-Guide/RViz-User-Guide.html)
