# 使用Virtualbox的CoreOS镜像安装CoreOS

> 通过Docker了解到Coreos这个linux发行版本，不过这个linux发行版
> 极其精简，没有包管理器等，专为虚拟化设计，所以启动迅捷，占用资源> 少，一切以容易的方式运行应用

> 想使用Virtualbox+CoreOS方式做个简单安装。发现下载CoreOS镜像
> 要翻墙，还要配置等,本来想简单体验下，因此没必要那么麻烦。在翻阅
> [CoreOS下载]()看到有virtualbox的镜像，欣喜之余，马上下载


### 安装步骤

1. 下载coreos_production_virtualbox.ovf和coreos_production_virtualbox_image.vmdk.bz2连个文件
2. 解压.bz2文件
3. 拷贝两文件到同一个目录中
4. 开启Virtualbox，点击“导入虚拟介质"菜单按照说明导入
5. 启动

### 设置密码
启动，发现CoreOS没法登录，没有密码，要做以下设置

1. 启动
2. ![](../images/coreos_vb_557-2-0.png)
3. 选择第二行，按“e”
4. 添加coreos.autologin
5. ![](../images/coreos_vb_557-2-3.png)
6. 按F10重启
7. 登录直接sudo passwd core,设置密码
8. 至此，可以直接登录了

### 使用NAT模式，加Putty登录
这个功能期望已久啊。以前都不知道NAT端口转发设置。
这就可以使用putty登录，又可以上网，又不用看丑陋的linux终端，嘿嘿。

1. 在网络设置里，选择“端口转发
2. 主机端口譬如设置为8022，子系统端口为22
3. 启动putty,输入IP地址：127.0.0.1，端口8022
4. OK啦。


[CoreOS下载]: http://stable.release.core-os.net/amd64-usr/current/
