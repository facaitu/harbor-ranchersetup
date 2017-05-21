# harbor-ranchersetup
https://hub.docker.com/r/balldog/harbor-rancher-setup/

# harbor-rancher 安装指导

## 要点
我们在rancher中安装，最好每个机器都加上harbor_log=true的标签，开放1514端口，他们需要互通信息


## [设置指南](https://segmentfault.com/a/1190000007705296)

原始安装是可以进入 http://registry.example.com 的，但是没有设置好https.

用admin用户名及设置最初的密码登陆即可，但docker login会出现问题。

## [设置https](https://github.com/vmware/harbor/blob/master/docs/configure_https.md)

## 启用Https

### 我们以在aws部署为例，同时使用aws的免费ssl,第一步是建立负载均衡器，然后将reg.ball.dog的A记录指向该平衡器。

### 搭建harbor过程中，参考[官方ssl指导](https://github.com/vmware/harbor/blob/master/docs/configure_https.md)

首先要安装一个干净的环境
	$ sudo rm -r /data/database
	$ sudo rm -r /data/registry