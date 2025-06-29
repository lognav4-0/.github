## LOGNAV Project 👋
Welcome! This is the oficial organization for LOGNAV project. Here, you can access every repository containing content for freedom autonomous robot development.
Each single repository has its features, README, and other stuff. Please, read them before contibuting!
Our main repository right now is the "lognav" repo. It contains all our development in a single package.


If you are using an NVIDIA GPU follow this tutorial to install the Docker2 (nvidia container toolkit): https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker

Otherwise, just install the docker in your system (probably it is already installed).

DockerHub login (dockerhub account):
```shell
docker login
```

Github container repository login (github token account) --> [if you have a problem follow https://gist.github.com/yokawasa/841b6db379aa68b2859846da84a9643c]:
```shell
docker login ghcr.io
```

Docker image:
```shell
docker pull ghcr.io/lognav4-0/freedom_vehicle:0.99
```

Run container using NVIDIA GPU (for the docker2 users):
```shell
docker run -it --name lognav --privileged --net=host --ipc=host --gpus all -w /home/lognav -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/tmp/shared  -e DISPLAY=$DISPLAY -e NVIDIA_VISIBLE_DEVICES=all -e NVIDIA_DRIVER_CAPABILITIES=compute,graphics,utility ghcr.io/lognav4-0/freedom_vehicle:0.99
```

Run container without NVIDIA GPU (for the docker users):
```shell
docker run -it --name lognav --privileged --net=host --ipc=host -w /home/lognav -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/tmp/shared  -e DISPLAY=$DISPLAY ghcr.io/lognav4-0/freedom_vehicle:0.99
```

### Troubleshooting:

_If you had any authorization problem redo all the steps again adding the sudo command before each command line._

_Take a look at the docker post-instalation for more details how correct your problem without needed to use sudo:_
https://docs.docker.com/engine/install/linux-postinstall/
