# swarm_ws

> 本仓库为 [BoomBoomFly](https://github.com/BoomBoomFly/BoomBoomFly) 主仓库中异构协同子系统的独立镜像/发布工作区，日常主线研发请以主仓库为准。

## 目录结构

- `src/swarm_cooperation`：小车与 ACG720 AprilGrid 对齐、地图融合与协同 HTTP 控制台
- `sim/`：集群仿真预留目录

## 构建说明

独立构建本工作区前需先加载已构建的 `ugv_ws` overlay（推荐直接使用主仓库的统一 `ros2_ws`）：

```bash
source /opt/ros/humble/setup.bash
source ../ugv_ws/install/setup.bash
colcon build --packages-select swarm_cooperation --symlink-install --executor sequential
source install/local_setup.bash
ros2 launch swarm_cooperation cooperative_mapping.launch.py
```