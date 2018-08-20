# Centos7 安装 Docker

1. 卸载旧版本 Docker

```shell
$ sudo yum remove docker \
                docker-client \
                docker-client-latest \
                docker-common \
                docker-latest \
                docker-latest-logrotate \
                docker-logrotate \
                docker-selinux \
                docker-engine-selinux \
                docker-engine
```

2. 安装必要工具

```shell
$ sudo yum install -y yum-utils \
    device-mapper-persistent-data \
    lvm2
```

3. 添加源，这里使用了阿里云的源

```shell
$ sudo yum-config-manager \
    --add-repo \
https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

4. 安装 docker 社区版

```shell
$ sudo yum install docker-ce -y
```

5. 启动 Docker

```shell
$ sudo systemctl start docker
```

6. 测试

```shell
$ sudo docker run hello-world
```

7. 安装 Docker-compose 所需依赖

```shell
$ sudo yum install -y install python-pip
```

8. 安装 Docker-compose

```shell
$ pip install --upgrade --force-reinstall --no-cache-dir docker-compose
```
