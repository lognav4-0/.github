## LOGNAV Project 👋

Docker Image:
```shell
docker pull ghcr.io/lognav4-0/ros2:latest
```

Run Container:
```shell
docker run -it --name lognav --privileged --net=host --ipc=host --gpus all -w /home/lognav -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/tmp/shared  -e DISPLAY=$DISPLAY -e NVIDIA_VISIBLE_DEVICES=all -e NVIDIA_DRIVER_CAPABILITIES=compute,graphics,utility ghcr.io/lognav4-0/ros2:latest
```
