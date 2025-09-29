# AUV Systems Core

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ROS 2](https://img.shields.io/badge/ROS%202-Humble-blue.svg)](https://docs.ros.org/en/humble/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![C++](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![CMake](https://img.shields.io/badge/CMake-3.16%2B-green.svg)](https://cmake.org/)
[![Docker](https://img.shields.io/badge/Docker-Supported-blue.svg)](https://www.docker.com/)
[![Jetson](https://img.shields.io/badge/NVIDIA%20Jetson-Supported-green.svg)](https://developer.nvidia.com/embedded/jetson-developer-kit)

> **Advanced Autonomous Underwater Vehicle (AUV) Systems Framework**

A comprehensive ROS 2-based framework for developing, deploying, and managing autonomous underwater vehicle systems. Built for marine robotics applications with support for navigation, control, sensor integration, and mission planning.

## 🚀 Features

- **Modular Architecture**: Component-based design for easy customization and extension
- **ROS 2 Integration**: Full ROS 2 Humble support with modern C++ and Python APIs
- **Hardware Support**: Optimized for NVIDIA Jetson platforms and embedded systems
- **Simulation Ready**: Gazebo integration for testing and validation
- **Docker Support**: Containerized deployment for consistent environments
- **Mission Planning**: Advanced path planning and mission execution capabilities
- **Sensor Integration**: Support for IMU, depth sensors, cameras, and sonar systems
- **Real-time Control**: High-performance control loops for precise vehicle maneuvering

## 📋 Prerequisites

### System Requirements
- **Operating System**: Ubuntu 22.04 LTS (recommended)
- **ROS 2**: Humble Hawksbill
- **Python**: 3.8 or higher
- **CMake**: 3.16 or higher
- **C++**: C++17 compatible compiler

### Hardware Support
- NVIDIA Jetson AGX Orin/Xavier
- Intel NUC systems
- Custom embedded platforms

## 🛠️ Installation

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/triton-mining/auv-systems-core.git
   cd auv-systems-core
   ```

2. **Install dependencies**
   ```bash
   # Install ROS 2 Humble (if not already installed)
   sudo apt update
   sudo apt install ros-humble-desktop-full

   # Install additional dependencies
   sudo apt install python3-colcon-common-extensions python3-rosdep
   sudo rosdep init
   rosdep update
   ```

3. **Build the workspace**
   ```bash
   colcon build --symlink-install
   source install/setup.bash
   ```

### Docker Installation

```bash
# Build the Docker image
docker build -t auv-systems-core .

# Run with GUI support (for simulation)
docker run -it --rm \
  --privileged \
  -e DISPLAY=$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  auv-systems-core
```

## 🏗️ Project Structure

```
auv-systems-core/
├── src/                    # Source packages
│   ├── navigation/         # Navigation and path planning
│   ├── control/           # Vehicle control systems
│   ├── sensors/           # Sensor drivers and processing
│   ├── mission/           # Mission planning and execution
│   └── utils/             # Common utilities and tools
├── config/                # Configuration files
├── launch/                # Launch files
├── docs/                  # Documentation
├── tests/                 # Unit and integration tests
└── docker/                # Docker configurations
```

## 🚢 Usage

### Basic Launch

```bash
# Launch the complete AUV system
ros2 launch auv_systems_core complete_system.launch.py

# Launch simulation environment
ros2 launch auv_systems_core simulation.launch.py

# Launch individual components
ros2 launch auv_systems_core navigation.launch.py
ros2 launch auv_systems_core control.launch.py
```

### Mission Execution

```bash
# Load and execute a mission
ros2 run mission_planner mission_executor --mission-file missions/example_mission.yaml

# Monitor system status
ros2 topic echo /auv/status
ros2 topic echo /auv/navigation/pose
```

## 📊 Monitoring and Diagnostics

The system provides comprehensive monitoring capabilities:

- **Real-time Status**: Vehicle state, sensor health, and system performance
- **Mission Progress**: Current mission status and completion metrics
- **Diagnostic Tools**: Built-in diagnostics for troubleshooting
- **Logging**: Comprehensive logging for analysis and debugging

## 🧪 Testing

```bash
# Run unit tests
colcon test

# Run integration tests
colcon test --packages-select auv_systems_core

# Run with coverage
colcon test --packages-select auv_systems_core --cmake-args -DCMAKE_BUILD_TYPE=Debug
```

## 📚 Documentation

- [API Documentation](docs/api/)
- [User Guide](docs/user_guide.md)
- [Developer Guide](docs/developer_guide.md)
- [Hardware Setup](docs/hardware_setup.md)
- [Mission Planning](docs/mission_planning.md)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Install pre-commit hooks
pre-commit install

# Run linting
pre-commit run --all-files
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏢 About Triton Mining Co

Developed by **Triton Mining Co**, a leader in marine robotics and autonomous underwater systems. Our mission is to advance underwater exploration and resource extraction through cutting-edge technology.

## 📞 Support

- **Documentation**: [docs.triton-mining.com](https://docs.triton-mining.com)
- **Issues**: [GitHub Issues](https://github.com/triton-mining/auv-systems-core/issues)
- **Discussions**: [GitHub Discussions](https://github.com/triton-mining/auv-systems-core/discussions)
- **Email**: support@triton-mining.com

## 🙏 Acknowledgments

- ROS 2 community for the excellent robotics framework
- NVIDIA for Jetson platform support
- Open source contributors and marine robotics researchers

---

**⚠️ Safety Notice**: This software is designed for research and development purposes. Always follow proper safety protocols when operating autonomous underwater vehicles in real-world environments.

**🔬 Research Use**: This project is actively used in marine robotics research. If you use this software in your research, please cite our work appropriately.
