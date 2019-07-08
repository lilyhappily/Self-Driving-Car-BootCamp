# 配置文件
## 检测器
从我们的 [主页](https://github.com/udacity/PIX-Self-Driving-Engineering-Base) 下载 `tl_detector/`文件夹
将`udacity/`文件夹下的所有文件（即 `frozen_inference_graph.pb` 所在路径下的所有文件）
例：
```
-saved_model/
 +variables/
 -saved_model.pb
-checkpoint
-frozen_inference_graph.pb
-model.ckpt.data-00000-of-00001
-model.ckpt.index
-model.ckpt.meta
-pipeline.config
```
![pix_model](./img/pix_model.png)
全部放到 `<your_path>/tl_detector/light_classification/light_graph/` 中。并将 `<your_path>/tl_detector` 所有文件夹移动到本地 `/home/up/Autoware/ros/src/`中。
## 其他文件
用同样的方法，下载以下文件夹，都在 [这里](https://github.com/udacity/PIX-Self-Driving-Engineering-Base)。并且执行以下操作
1. 将 `<your_path>/styx_msgs/` 复制到 `/home/up/Autoware/ros/src/`
2. 将 `<your_path>/vehicle_sender.cpp` 覆盖到 `/home/up/Autoware/ros/src/socket/packages/vehicle_socket/nodes/vehicle_sender/`
3. 将 `<your_path>/launch/` 复制到 `/home/up/Autoware/ros/`。
4. 将 `<your_path>/mindvision/` 复制到 `/home/up/Autoware/ros/src/`。
5. 将 `<your_path>/mindvision/3rdparty/lib/libMVSDK.so` 复制到 `/lib/` (`sudo cp <xxx> /lib/`)

**每次更新文件时都需要重新编译：**
```
$ ./catkin_make_release
```
## 启动 mindvision 摄像头
```bash
$ roscore
```

## 在另一个 Terminal 中输入：
```
$ cd ~
$ sudo su
$ cd /home/up/Autoware/ros/
$ source devel/setup.bash
$ rosrun mindvision mindvision_node
```

## 安装依赖包


在该文档目录下运行下运行以下命令：
```bash
pip3 install -r requirements.txt
```
