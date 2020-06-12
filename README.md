# GoIp2Locate

> 基于 Go语言 和 纯真IP库 编写的 Ip 地址归属地查询微服务, 支持在线更新Ip地址库.  部署简单, 自动运维。未来将支持更多的IP地址库，提供更全面的GEO地理识别信息及POI信息。

### 特性
- 轻量化,高可用微服务架构
- 1核1G服务器,实测并发高达1万+
- 自动定期更新纯真IP库
- 自动识别真实客户端IP地址

### 依赖及安装

1. Linux -- 目前支持 CentOS, UBuntn
2. Linux cron -- 操作系统计划任务
3. wget
4. Go 1.9.x 或以上

##### CentOS
```
yum install -y wget
yum install -y epel-release
yum install golang

```

##### UBuntn
```
sudo apt-get wget
sudo add-apt-repository ppa:longsleep/golang-backports
sudo apt-get update
sudo apt-get install golang-go
```

### 安装

1. 下载 goip2locate.zip 包,将解压.
2. 创建主程序目录,并将解压后，得到的所有文件复制到 /usr/local/goip2locate下.
3. 创建主程序执行用户,避免使用权限过高的用户运行本程序(例如:root)
4. 注册开机自启动服务
5. 添加计划任务定期更新Ip库
6. 完装结束结束
```
wget https://github.com/GenjiLuo/GoIp2Locate/blob/master/goip2locate.zip
useradd goip2locate -s /sbin/nologin
unzip 
mkdir -p /usr/local/goip2locate
cp -rf 
chmod -R 0770 /usr/local/goip2locate

```

### 使用
查询自己的IP归属地信息
> http://你的域名|IP:端口号/me

查询目标IP地址的归属地信息
> http://你的域名|IP:端口号/?ip=需要检测归属地的IP地址

>> 默认端口 6619 , 支持与 nginx或apache等web服务器集成, 实现 backend 服务模式,转发到 80端口。(推荐)

#####nginx配置
```

```

### TODO List
- 支持配置热加载
- 支持IP明细GEO信息查询，用于高并发下的IP模糊定位
- 支持IP明细POI信息查询, 用于IP定位下的周边兴趣点信息挖掘
- 
