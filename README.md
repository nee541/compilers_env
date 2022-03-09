# compilers\_env

## Build
```bash
cd build
docker build -t name:v1 .
```
1. cd 指令进入build目录
2. 通过docker的build指令搭建image
    - -t name:v1 指定名为name, 版本为v1的镜像, 版本可不填
    - -f <Dockerfile> 通过-f指定Dockerfile地址, 由于Dockerfile就在当前文件夹内，可不填
    - . 注意指令最后还有一个., 指定工作目录

## Usage

### 概念

image相当于系统的模板，container相当于系统的实例。通过上述的docker build指令可以在本地构造一个image(docker image ls 查看)

### 指令

[官方文档](https://docs.docker.com/engine/reference/commandline/docker/)

- docker run image <指令(可空)> -> 寻找image创建container并且运行
    - [-i] interactive, 交互
    - [-t] tty 终端
    - [--name] 指定创建的container的名字
    - [-d] detach 后台运行
    - [-p] host port:container port, 绑定端口
    - [-v] host folder:container folder 挂载host目录
    - [--mount] 同上，有如下参数
        - type type=bind表示绑定主机目录和container目录
        - source 指定host folder
        - target 指定container folder
        - readonly 设置为只读

- docker start container <指令(可空)> -> 开始运行container

- docker stop container -> 结束运行container

- docker exec container <指令> -> 执行一个指令，如果设置参数为 -it, 就可以进入container内部执行
    
