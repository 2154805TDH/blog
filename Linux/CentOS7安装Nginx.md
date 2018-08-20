# Cent OS 7 安装 Nginx

1. 添加 Nginx 库

```shell
$ wget https://nginx.org/keys/nginx_signing.key
$ sudo rpm --import nginx_signing.key
$ sudo vim /etc/yum.repos.d/nginx.repo
```

2. 开启仓库

```conf
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/7/$basearch/
gpgcheck=1
enabled=1
```

3. 重建缓存

```shell
   yum clean all
   yum makecache
```

4. 安装

```shell
sudo yum install -y nginx
```
