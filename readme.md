# ROS (ROBOT OPERATING SYSTEM) 🤖

### What is ROS?

ROS is a set of software libraries and tools that help you build robot applications. From drivers to state-of-the-art algorithms, and with powerful developer tools, ROS has what you need for your next robotics project. And it's all open source.

### What is ROS 2?

ROS 2 is the next generation of ROS. It's a complete rewrite of ROS, and is not backwards compatible with ROS 1. ROS 2 is designed to be more modular, more scalable, and more flexible than ROS 1. It's also designed to be more accessible to new users, and to be easier to use in real-time applications.

### What is ROS package?

A ROS package is a directory that contains ROS source code, data, build scripts, and documentation. A package is the smallest unit of code that can be built and executed in ROS. A package can contain multiple ROS nodes.

### What is ROS node?

In ROS (Robot Operating System), a node is a process that performs a specific computational task. A node is typically implemented as an executable file or a script, and it can communicate with other nodes using ROS communication mechanisms, such as topics, services, and actions.

### ROS package Vs ROS node: 🚀

- **Packages are used to provide a set of specific functionalities**. Packages are used to organize and distribute ROS code, and they can contain one or more ROS nodes.

- On the other hand, **a node is a process that performs a specific computational task**. Nodes are the primary computational units in ROS and they can communicate with each other using ROS communication mechanisms such as topics, services, and actions.

#### Example:
 We can have a package, that opens door when a person is standing nearby. This package can have multiple nodes, one for opening the door, one for detecting the person, one for detecting the door, etc.

---

## How to create a ROS workspace?

- A workspace is simply a directory that contains ROS packages. It is a convenient way to organize ROS projects.

- It should have a directory **`src`** that **contains ROS packages**. When we will build the package, we will get some additional directories in the workspace, `build`, `install`, and `log`.

```bash
mkdir -p myros_workspace/src
cd myros_workspace
```

---

## How to create a ROS package?

- We create all our ROS packages inside the `src` directory of the workspace.

- We will be using `c++` for this repository.

```bash
cd src
ros2 pkg create --build-type ament_cmake <package_name>
```

- Once you run the command, a new directory with the name of the package will be created inside the `src` directory.

- Within that directory, you will find the `package.xml` file, which contains the package metadata, and the `CMakeLists.txt` file, which contains the build instructions for the package.

- It will also create a `src` directory, which contains the source code for the `nodes`.

---

## How to build a ROS package?

- We can build a ROS package using the `colcon` build tool.

```bash
cd myros_workspace # go to the workspace directory

# if you wish to build all the packages in the workspace:
colcon build

# if you wish to build a specific package:
colcon build --packages-select <package_name>

```

- This will create a `build` directory in the workspace, which contains the build artifacts for all the packages in the workspace.

- It will also create an `install` directory in the workspace, which contains the install artifacts for all the packages in the workspace.

- The `install` directory is used to install the packages in the workspace.

---

## How to run a ROS package?

- Source the `setup.bash` file in the `install` directory, and then run it.

```bash
# install/setup.bash is generated when you build the package
. install/setup.bash

# to run a node from a package:
ros2 run <package_name> <node_name>
```