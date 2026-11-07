# 车机必须更新的文件对应表

最新交付仓库为 https://github.com/wxk1316/plan ，使用main分支。包含原有算法、记录器、自适应预瞄以及首次目标前规划节点退出和底盘禁用消息处理的修复。

本文按实车终端显示的源码根目录 /home/nvidia/Desktop/Wxk/car_gpt/src 编写。如果实际工作空间不同，只替换这个根目录；表中的相对路径保持一致。

## 已安装上一版但出现启动报错的车机

如果已安装前一版六包代码，遇到RealtimeVehicleBridgeCore没有_goal属性的启动报错，本次必须覆盖下面三个文件。即使只是复制Python文件，仍请重新构建/source并完整重启launch。

| 仓库文件 | 车机目标文件 |
| --- | --- |
| `rda_dwa_real/rda_dwa_real/realtime_vehicle_core.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/realtime_vehicle_core.py` |
| `rda_dwa_real/rda_dwa_real/bridge_node.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/bridge_node.py` |
| `control/car_ctr/src/car_ctr.cpp` | `/home/nvidia/Desktop/Wxk/car_gpt/src/control/car_ctr/src/car_ctr.cpp` |

## 从最初版本升级的车机

相对本对话开始时保存的原始源码，共25个文件新增或修改；全部使用plan仓库中的最新版本。未列出的文件没有本次必要更新，不需要用交付包覆盖现车配置。

| 仓库文件 | 车机目标文件 | 操作 |
| --- | --- | --- |
| `car_launch/launch/run_rda_dwa.launch.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/car_launch/launch/run_rda_dwa.launch.py` | 覆盖 |
| `car_launch/package.xml` | `/home/nvidia/Desktop/Wxk/car_gpt/src/car_launch/package.xml` | 覆盖 |
| `control/car_ctr/CMakeLists.txt` | `/home/nvidia/Desktop/Wxk/car_gpt/src/control/car_ctr/CMakeLists.txt` | 覆盖 |
| `control/car_ctr/package.xml` | `/home/nvidia/Desktop/Wxk/car_gpt/src/control/car_ctr/package.xml` | 覆盖 |
| `control/car_ctr/src/car_ctr.cpp` | `/home/nvidia/Desktop/Wxk/car_gpt/src/control/car_ctr/src/car_ctr.cpp` | 覆盖 |
| `msg/common/include/common/myudp.hpp` | `/home/nvidia/Desktop/Wxk/car_gpt/src/msg/common/include/common/myudp.hpp` | 覆盖 |
| `msg/common/include/common/udp_diagnostics.hpp` | `/home/nvidia/Desktop/Wxk/car_gpt/src/msg/common/include/common/udp_diagnostics.hpp` | 新建 |
| `rda_dwa/rda_dwa/motion_safety.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa/rda_dwa/motion_safety.py` | 新建 |
| `rda_dwa/rda_dwa/realtime_ackermann.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa/rda_dwa/realtime_ackermann.py` | 新建 |
| `rda_dwa_real/config/real_vehicle.yaml` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/config/real_vehicle.yaml` | 覆盖 |
| `rda_dwa_real/launch/diag_recorder.launch.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/launch/diag_recorder.launch.py` | 覆盖 |
| `rda_dwa_real/launch/rl_dwa_car.launch.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/launch/rl_dwa_car.launch.py` | 覆盖 |
| `rda_dwa_real/package.xml` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/package.xml` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/adaptive_preview.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/adaptive_preview.py` | 新建 |
| `rda_dwa_real/rda_dwa_real/async_planner.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/async_planner.py` | 新建 |
| `rda_dwa_real/rda_dwa_real/bridge_node.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/bridge_node.py` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/diag_recorder_node.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/diag_recorder_node.py` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/kf_tracker.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/kf_tracker.py` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/lidar_track_node.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/lidar_track_node.py` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/obstacle_fusion.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/obstacle_fusion.py` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/realtime_vehicle_core.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/realtime_vehicle_core.py` | 新建 |
| `rda_dwa_real/rda_dwa_real/telemetry_recording.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/telemetry_recording.py` | 新建 |
| `rda_dwa_real/rda_dwa_real/traj_tracker_core.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/traj_tracker_core.py` | 覆盖 |
| `rda_dwa_real/rda_dwa_real/traj_tracker_node.py` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real/rda_dwa_real/traj_tracker_node.py` | 覆盖 |
| `rda_dwa_real_msgs/msg/Obstacle.msg` | `/home/nvidia/Desktop/Wxk/car_gpt/src/rda_dwa_real_msgs/msg/Obstacle.msg` | 覆盖 |

## 保留现车配置与依赖

car_launch包中本次必要更新仅为launch/run_rda_dwa.launch.py和package.xml。请保留现车的launch/run_fastlio.launch.py与launch/run_sensor.launch.py：前者包含车机实际地图路径和TF，交付仓库附带的未改副本有旧绝对路径，直接覆盖会影响定位启动。

FAST_LIO、PCD地图、雷达/IMU驱动与标定、control_msgs均未在这25个改动文件中。control_msgs出现在编译命令中是依赖关系；不要因此替换它。msg/common只需更新表中两个头文件，其他公共库文件保留现车版本。

所有表中写入位置均为src内源码。不要直接往build或install覆盖文件；也不要将第二份同名ROS包克隆到现有src中。仓库中的documentation、tools和tests用于说明/检查，不是需要替换的车机算法包。

record_data.zip、222.zip和zhongduan.docx是分析输入，不能覆盖任何车辆源码。较早发布的完整源码/六包压缩包可能不含最新启动修复；部署以plan/main或本次生成的plan更新压缩包为准。

## 更新顺序

先停止车辆和ROS launch并保存本次记录，备份需要覆盖的旧源码。在工作空间外拉取/解压plan仓库，然后按上表复制文件。校正日志中停在1970年的系统时间后再构建；禁止车辆运行中大幅调整系统时间。

从原始版本整体升级，在ROS工作空间根目录执行：

```bash
cd /home/nvidia/Desktop/Wxk/car_gpt
colcon build --symlink-install --packages-up-to common control_msgs rda_dwa_real_msgs rda_dwa car_ctr rda_dwa_real car_launch --cmake-clean-cache
source install/setup.bash
```

已安装前一版、只覆盖三个修复文件时：

```bash
cd /home/nvidia/Desktop/Wxk/car_gpt
colcon build --symlink-install --packages-up-to rda_dwa_real car_ctr --cmake-clean-cache
source install/setup.bash
```

更新后的启动与记录示例：

```bash
ros2 launch car_launch run_rda_dwa.launch.py diag_out_dir:=/home/nvidia/Desktop/Wxk/car_gpt/record_data
```

此参数把记录目录明确放入当前car_gpt工作空间；未指定时原默认仍是旧car工作空间下的record_data。检查diag_recorder启动行、recorder_health和raw_bag元数据，确认实际记录成功。

重新启动后，/rda_dwa_real_bridge应持续存在；发布目标前/rda/diag应为reason=no_goal、goal=null，发布有效目标后goal_received=true。定位、障碍物数据不新鲜时继续安全等待，不代表启动缺陷再次发生。
