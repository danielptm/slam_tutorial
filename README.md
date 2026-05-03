# Tutorial Commands
```
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
ros2 run turtlebot3_teleop teleop_keyboard
ros2 topic list
ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True
ros2 run nav2_map_server map_saver_cli -f maps/my_map
ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True map:=maps/my_map.yaml
```





## Add terminator launch config
To add terminator launch config so 1 window is opened with many panes each pane execting their own command to start up. Add this to `~/.config/terminator/config` then you can run `terminator -l launch_ros` to launch terminator with that layout config

```
[layouts]
  [[default]]
    [[[window0]]]
      type = Window
      parent = ""
    [[[child1]]]
      type = Terminal
      parent = window0
  [[launch_ros]]
    [[[window0]]]
      type = Window
      parent = ""
    [[[child1]]]
      type = HPaned
      parent = window0
    [[[terminal1]]]
      type = Terminal
      parent = child1
      profile = default
      command = bash -c "sleep 1; echo hello; exec bash"
    [[[terminal2]]]
      type = Terminal
      parent = child1
      profile = default
      command = bash -c "sleep 1; echo world; exec bash"

```
