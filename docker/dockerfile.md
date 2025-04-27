## dockerfile
- 镜像原理：多层叠加文件系统

![image](https://github.com/user-attachments/assets/3d495cf1-003b-4bfb-80b2-1e570d8a8c15)

## docker制作镜像
1. 容器转为镜像
```sh
  docker commit 容器id 镜像名称：版本号
  # 镜像不能传输，压缩后方可
  docker save -o 压缩文件名称 镜像名称：版本号
  # 解压压缩文件
  docker load -i 压缩文件名称
```

2. dockerfile
```sh
FROM #指定dockerfile基于那个镜像
ADD springboot.jar app.jar
MAINTAINER #作者信息
LABEL
RUN
CMD java -jar app.jar
ENV
ARG
VOLUME
EXPOSE
WORKDIR # 暴露端口
```
- 创建容器
```docker build -f ./dockerfilename -t app .```

## docker compose
是一个编排多容器分布式部署的工具。使用步骤：

1. dockerfile定义运行环境镜像
2. 使用docker-compose.yml定义组成应用的各服务
```sh
version:
services:
  image1:
     xxx
  image2: 
     xxx
```

3. 运行docker-compose up启动应用
```docker-compose -version # 查看版本 ```

## 创建私有仓库
```sh
docker pull registry 
docker run -id --name=registry -p 5000:5000 registry
http://私有仓库服务器IP:5000/v2/_catalog
vim /etc/docker/daemon.json
{"insecure-registries":["私有仓库服务器IP:5000"]}
systemctl restart docker
docker start registry
```
