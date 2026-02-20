# ROS2 + RViz + TSX Web UI: Beginner Project Tech Stack Setup

This document provides a **minimal tech stack overview** for a beginner-friendly project that moves a robot in RViz via a web UI and optionally a backend service. It focuses on **all software, languages, and tools needed** without including project code.

## Project Goal

* Move a robot in RViz using a TSX web UI (buttons/sliders).
* Optionally automate movement using a backend service.
* Visualize all movements in RViz.

## Tech Stack Overview

### Robotics / Middleware

* **ROS2** (e.g., Humble) — middleware for robot communication.

  * Official docs: [ROS2 Documentation](https://docs.ros.org/en/rolling/index.html)
* **RViz2** — visualization tool for robot positions and markers.

  * User guide: [RViz User Guide](https://docs.ros.org/en/rolling/Tutorials/Intermediate/RViz/RViz-User-Guide/RViz-User-Guide.html)
* **rosbridge_suite** — WebSocket bridge for frontend to communicate with ROS2.

  * Documentation: [rosbridge_suite](http://wiki.ros.org/rosbridge_suite)

### Frontend

* **React + TypeScript (TSX)** — create interactive UI for controlling the robot.
* **Vite** — bundler for React + TypeScript projects.
* **roslibjs** — JS library to connect frontend with ROS2 via WebSocket.

### Backend (Optional)

* **Python** with `rclpy` — to publish ROS2 messages programmatically.
* **Node.js** with `rclnodejs` — alternative backend for ROS2 communication.

### Development Tools

* **VS Code** or another code editor.
* **Node.js / npm** — for frontend project setup.
* **Terminal / shell** — to run ROS2, rosbridge, and RViz.

## Setup Overview

1. **Install ROS2**: Follow official guide for your OS.
2. **Install rosbridge_suite**: Allows frontend WebSocket communication.
3. **Install RViz2**: Visualize robot positions and markers.
4. **Frontend tools**: React + TypeScript project with `roslibjs`.
5. **Optional Backend**: Python or Node.js to automate robot movements.

## References

* [ROS2 Installation Guide](https://docs.ros.org/en/rolling/Installation.html)
* [rosbridge_suite Documentation](http://wiki.ros.org/rosbridge_suite)
* [RViz User Guide](https://docs.ros.org/en/rolling/Tutorials/Intermediate/RViz/RViz-User-Guide/RViz-User-Guide.html)
