cpp_pub

An adaptation of the standard cpp_pub ROS tutorial. Material to accompany a ROS debugging/visualizing video.

See media\RosStepDebugAndViewData.mkv video in this repo.

-------------------------------------------------------------------

How to step debug in ROS 

* see accompanying video demo

--- install ROS2 ---

- recommend distro install
- recommend default location '/opt/ros/foxy'
- guidance : https://docs.ros.org/en/crystal/Installation/Linux-Install-Binary.html

--- update bashrc ---

- put source in ~/.bashrc

sudo gedit ~/.bashrc
 
- add this: 
source /opt/ros/foxy/setup.bash

- save, exit

--- install plot juggler ---

- recommend distro install
- guidance: https://github.com/PlotJuggler/plotjuggler-ros-plugins

--- install VSCode ---

- guidance: https://code.visualstudio.com/

- open VSCode (type 'code' in terminal)

- open Extensions tab (on left pane)

- add ROS
- add C/C++ Extension Pack

- close VSCode

--- create ros workspace ---

- recommend location '~/ros2_ws'

- open new terminal

mkdir ~/ros2_ws/src

cd ~/ros2_ws/src

- create/clone/etc <your-project git>

git clone https://github.com/gaia-platform/cpp_pub.git

cd ~/ros2_ws

colcon build --cmake-args -DCMAKE_BUILD_TYPE=RelWithDebInfo

- close terminal

--- update bashrc again ---

- put source in ~/.bashrc

sudo gedit ~/.bashrc

- add this: 
source /your home path here/ros2_ws/install/local_setup.bash

- save, exit

--- run ---

- open new terminal

ros2 run hello

- stop

<ctrl>C

--- setup project -------------------------------

- open VSC

- open ros2_ws/src/<your-project folder>

- code will ask: allow configure? yes
- configure Intellisense? yes
- Always configure? no

- set active kit: clang<cversion>
- set build variant: debug

- set breakpoint in code (click left column in code window, red dot appears)

- start debug (hit bug symbol in bottom bar)

- code will stop on breakpoint

- inspect objects (select, right click, add to watch)

- step, etc (click in in top center panel)

- let program run free

--- see messages ---

- open new terminal

ros2 topic echo topicint

- numbers will print in sequence

<ctrl>C

ros2 run plotjuggler plotjuggler

- <see video>

