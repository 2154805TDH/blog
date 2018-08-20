# Centos 7 防火墙

## 基本参数

安装 firewalld：

`yum install -y firewalld firewall-config`

启动：`$ systemctl start firewalld.service`

自启: `$ systemctl enable firewalld.service`

停止：`$ systemctl stop firewalld.service`

禁用：`$ systemctl disable firewalld.service`

状态：`$ systemctl status firewalld.service`

查看版本：`$ firewall-cmd --version`

查看帮助：`$ firewall-cmd --help`

查看区域信息： `$ firewall-cmd --get-active-zones`

查看指定接口所属区域：`$ firewall-cmd --get-zone-of-interface=eth0`

拒绝所有包： `$ firewall-cmd --panic-on`

取消拒绝状态：`$ firewall-cmd --panic-off`

查看是否拒绝：`$ firewall-cmd --query-panic`

reload 后永久生效参数，当前不生效，对以下所有命令生效：

`--permanent`

更新防火墙规则：

`$ firewall-cmd --reload` # 无需断开连接

`$ firewall-cmd --complete-reload` # 断开连接，类似重启服务

## 设置区域

将接口添加到区域，默认接口都在 public：

`$ firewall-cmd --zone=public --add-interface=eth0`

设置默认接口区域：

`$ firewall-cmd --set-default-zone=public`

## 添加端口

查看所有打开的端口：

`$ firewall-cmd --zone=public --list-ports`

加入一个端口到区域：

`$ firewall-cmd --zone=public --add-port=8080/tcp`

在指定区域开启某个范围的端口号：

`$ firewall-cmd --zone=public --add-port=18881:65534/tcp`

## 添加服务

默认服务文件：

`/etc/firewalld/services`或`/usr/lib/firewalld/services`

添加：

`$ firewall-cmd --zone=public --add-service=smtp`

移除：

`$ firewall-cmd --zone=public --remove-service=smtp`
