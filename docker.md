## docker命令

- 服务的启动与关闭
```bash
systemctl start docker  
systemctl status docker
systemctl stop docker
systemctl restart docker
systemctl enable docker
```

- 镜像命令
```bash
docker images # images list
docker search [softname] # search images
docker pull [softname:version] # latest
docker rmi [image id] 
       rm-> remove 
         i-> image
docker rmi `docker images -q` # delete all
```

- 容器命令
```bash
docker run -it --name=c1 softname:version /bin/bash
           参数  容器名 =可以用空格
           -t分配终端 -i表示保持容器运行
           -d 以守护模式运行
               要用docker exec -it [c2] /bin/bash 
exit

docker ps -a # 查看运行中容器
docker stop [c2]
docker start [c2]
docker rm [c1]
    不能删除正在运行的容器
docker inspect # 查看容器信息
```

## 数据卷用来解决数据互通
- 数据卷
```bash
docker run -it --name=c1 -v /root/data:/root/data_container softname:version /bin/bash
                         -v 数据卷 宿主目录不存在则创建：容器目录
```

- 数据卷容器
```bash
1.docker run -it --name=c3 -v /volume softname:version /bin/bash
                            /volume方式实现 c3数据卷容器
# c1,c2分别挂载到c3数据卷容器
2-1.docker run -it --name=c1 --volumes-from cs softname:version /bin/bash
2-2.docker run -it --name=c2 --volumes-from cs softname:version /bin/bash
```

## docker 应用部署
1. 搜索images
2. pull images
3. create container
4. oper container [softname]

- mysql部署:
```bash
mkdir mysql
cd mysql

docker run -id \
-p 3307:3306 \ # 端口映射
--name=c_mysql \
# $PWD -> /root/mysql/
-v $PWD/conf:/etc/mysql/conf.d \
-v $PWD/logs:/log \
-v $PWD/data:/var/lib/mysql \ # 数据目录
-e MYSQL_ROOT_PASSWORD=123456 \
mysql:5.6
# 启动c_mysql容器
docker exec -it c_mysql /bin/bash
# 登录mysql
mysql -uroot -p123456
```


