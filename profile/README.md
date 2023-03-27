## LOGNAV Project 👋

If you are using an NVIDIA GPU follow this tutorial to install the Docker2 (nvidia container toolkit): https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker

Otherwise, just install the docker in your system (probably it is already installed).

DockerHub login (dockerhub account):
```shell
docker login
```

Github container repository login (github token account):
```shell
docker login ghcr.io
```

Docker image:
```shell
docker pull ghcr.io/lognav4-0/freedom_vehicle:0.94
```

Run container using NVIDIA GPU (for the docker2 users):
```shell
docker run -it --name lognav --privileged --net=host --ipc=host --gpus all -w /home/lognav -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/tmp/shared  -e DISPLAY=$DISPLAY -e NVIDIA_VISIBLE_DEVICES=all -e NVIDIA_DRIVER_CAPABILITIES=compute,graphics,utility ghcr.io/lognav4-0/freedom_vehicle:0.94
```

Run container without NVIDIA GPU (for the docker users):
```shell
docker run -it --name lognav --privileged --net=host --ipc=host -w /home/lognav -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/tmp/shared  -e DISPLAY=$DISPLAY ghcr.io/lognav4-0/freedom_vehicle:0.94
```

### Troubleshooting:

_If you had any authorization problem redo all the steps again adding the sudo command before each command line._
