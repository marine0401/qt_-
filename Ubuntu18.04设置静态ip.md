## Ubuntu18.04设置静态ip

在开始之前先弄清楚networking服务和network-manager服务的区别。

networking是控制系统网络设置的，如果你修改了相关的网络配置需要重启此服务。

而network-manager是管理networking服务的一个图形化管理工具的后台服务程序。

为了继续下面的操作，需要大家安装一下net-tools,以及ifupdown,并重启一下系统。

```
sudo apt install -y ifupdown net-tools
init 6
```

通过修改`/etc/network/interfaces` 配置静态IP