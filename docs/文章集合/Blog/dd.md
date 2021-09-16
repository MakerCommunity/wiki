## 什么是DD？

DD是Linux系统下的磁盘读写命令，可以将远端系统镜像，比如Windows系统镜像写入硬盘进行安装。一般来说，在国外服务器上安装Windows系统需要另付费而DD则可以免去环节。

> [!tip]
> 填写你要的内容

### html

```html
<p>This is a paragraph</p>
<a href="//docsify.js.org/">Docsify</a>
```

### bash

```bash
echo "hello"
```




### php

```php
function getAdder(int $x): int 
{
    return 123;
}
```


### DD命令安装系统的优点

**1.可以绕开VPS服务器商家的系统安装渠道，自由为服务器切换其它系统。**

**2. 可以自己动手将原本的Linux系统，比如CentOS、Ubuntu、Debian，更换为Windows系统。**

**3. 如果对商家提供的Linux系统不满意， 同样可以自己动手更换为纯净的官方版本。**

Linux的DD方法之前已经写过了，可以参考这篇：[服务器自带的系统不喜欢？那就自己DD一个船新的系统吧！](https://breakthewa11.com/archives/dd.html)



### DD命令安装系统的缺点

这种更换系统的操作，并不被商家认可，反而可能会违反ToS（服务条列），尤其是将Linux系统DD为Windows系统，如果被发现部分商家可能会采取停机等惩戒措施。（支持自定义挂载镜像的商家，一般都支持DD Linux系统，腾讯云我已经咨询过可以DD，不过由于Windows系统不像Linux是开源的，而是需要付授权费用的，所以正经使用，还是建议购买官方系统后台自带Windows系统的版本，我们这边只是测试使用）



## 为什么需要DD

Linux玩腻了，想试试windows搭建服务器是什么样子的。

挂网课，挂QQ，各种挂机。



## 如何DD



### 一键DD  Windows脚本



目前网上流传最广的DD脚本，是Vicer（萌咖）的一键脚本，功能比较强大。

-  Vicer 脚本优点：可以实现Windows系统全自动安装，无需VNC 模式或救援，安装完成后可以通过远程桌面直接登录系统。

-  适用架构：不能是Open VZ 架构，支持KVM/XEN 

-  适用系统：GRUB引导的CentOS/Debian/Ubuntu 

-  硬盘空间：建议10G以上，最好15G以上



## 开始DD

1、首先保证服务上安装了如下的软件包

  ```bash
#确保安装了所需软件:
#Debian/Ubuntu:
apt-get install -y xz-utils openssl gawk file

#RedHat/CentOS:
yum install -y xz openssl gawk file
  ```

2、Putty或者Finalshell等远程连接工具（腾讯云可以直接用后台控制台登陆）连接VPS服务器，复制以下命令运行， 注意将命令中的汉字，替换为实际系统镜像链接地址，下文会提供相关链接。

```bash
#一键脚本，直链包链接自己找个替换下

#国内:
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -dd "引号里放dd包直链" --mirror 'http://mirrors.ustc.edu.cn/debian/'

#国外:
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -dd "引号里放dd包直链"
```



3、接下来就可以不用管了，安装所需时间与系统镜像载速度及你的VPS服务器性能有关。正常情况下，15-30分钟后应该可以安装成功。

对于VSP服务器后台自带VNC功能的，可以打开VNC观察安装进度。五分钟之后打开VNC，会看到下面的界面，提示Strating up the partitioner ，而且进度一直会卡在0%，不要担心，这是正常的（我第一次以为是出问题了，然后就重装了系统，导致一直没成功）



![ad29c1ff2e3e43d2a418cc7d0bb99b45](https://pic.loll.cc/images/2021/08/28/20210828090140.png)



此时，我们要做的就是耐心等待，可以选择打开你的电脑硬盘，去看一部片子，看完片子回来，再次打开VNC，就能看到熟悉的Windows界面了。

4、等待在VNC看到了Windows的系统界面，我们会发现VNC里面鼠标操作非常不爽，这个时候我们就可以需要远程登陆工具来登陆了。（个人使用Microsoft Remote Desktop，MAC用户直接在APP STORE下载就行很方便）

![053f180d38544738801083849faecdad](https://pic.loll.cc/images/2021/08/28/20210828090228.png)



### 可用的DD  Windows系统镜象地址

由于每个人需要安装的Windows系统版本并不相同，所以前文脚没有给出链接地址。可根据自身需求，选择下面的链接地址对脚本命令进行替换。

####  Vicer镜像地址

以下各系统都有两个下载链接，其中第一个为Google  Drive地址，国内被墙建议外VPS服务器使用；

第二个为OneDrive地址，建议国内VPS服务器使用。

```bash
# Windows 7 32位中文（Windows Thin PC）:
https://image.moeclub.org/GoogleDrive/1srhylymTjYS-Ky8uLw4R6LCWfAo1F3s7
https://moeclub.org/onedrive/IMAGE/Windows/win7emb_x86.tar.gz
 
# Windows 8.1 SP1 64位中文（Embedded）:
https://image.moeclub.org/GoogleDrive/1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J
https://moeclub.org/onedrive/IMAGE/Windows/win8.1emb_x64.tar.gz
 
# Windows 10 ltsc 64位中文:
https://image.moeclub.org/GoogleDrive/1OVA3t-ZI2arkM4E4gKvofcBN9aoVdneh
https://moeclub.org/onedrive/IMAGE/Windows/win10ltsc_x64.tar.gz
```


**注意事项：**

1、安装成功后，请尽快更改默认登录密码

- 默认用户名：`Administrator`

- 默认密码：`Vicer`


2、Win7版本默认已激活，Win8.1及Win10版本默认未激活，方法可参考文末相关内容。



#### Teddysun镜像地址

以下各系统版本都有两个下载链接，任选其一：

```bash
# Windows Server 2012 R2中文版：
https://file.yuntu.ca/iso/teddysun/cn_windows2012r2.gz
https://mirrors.yuntu.ca/teddysun/cn_windows2012r2.gz

# Windows Server 2016中文版：
https://file.yuntu.ca/iso/teddysun/cn_windows2016.gz
https://mirrors.yuntu.ca/teddysun/cn_windows2016.gz

# Windows Server 2019中文版
https://file.yuntu.ca/iso/teddysun/cn_windows2019.gz
https://mirrors.yuntu.ca/teddysun/cn_windows2019.gz
```

**注意事项：**

1、安装成功后，请尽快更改默认登录密码

- 默认用户名：`administrator`
- 默认密码：`Password147`



2、已测试可用的服务器商家包括腾讯云，Vultr 、DigitalOcean、Cloudcone、Kimsuf、Online 等，其它商家自测。

3、可用KMS方式激活系统，参考本文末相关内容。



#### 老司机镜像地址

```bash
# Windows Server 2008 SP1 R2 64位中文版：
http://soft.815494.com/dd/WinSrv2008x64-Chinese.vhd.gz
```

**注意事项：**

1、安装成功后，请尽快更改默认登录密码

- 默认用户名：`Administrator`
- 默认密码：`WinSrv2008x64-Chinese`

2、安装后会自动激活，无需另外激活。



#### Linode专用镜像：

```bash
# Windows Server 2003 中文版：
http://down.80host.com/iso/dd/cn2003-virtio-pass-Linode.gz
```

- 默认用户名：`Administrator`
- 默认密码：`Linode`



#### OVH  VPS专用镜像

```bash
# Windows 7中文版： 
http://down.80host.com/iso/dd/win7_cn_5gb_virtio_scsi.gz
http://down.80host.com/iso/dd/win7_cn_5gb_virtio_scsi_faster.gz
```


- 默认用户名：`administrator`
- 默认密码：`www.80host.com`



### Windows激活

#### 方案1  KMS方式激活

Windows系统安装成功后，用远程桌面连接Win+R快捷键调出运行窗口，输入CMD回车，运行如下命令：

```bash
slmgr -skms kms.moeclub.org
slmgr -ato
```


可能需要用到的密钥（按对应版本选，良心云轻量一般不需要这个）：`https://docs.microsoft.com/zh-cn/windows-server/get-started/kmsclientkeys`



![070eae0ab21246209420d6d1c3145519](https://pic.loll.cc/images/2021/08/28/20210828103844.png)




#### 方案2  激活工具

Windows激活工具下载： 点此进入下载页面：`https://www.jb51.net/softs/227076.html`

页面名称虽然为Win8.1 激活，但实际上可激活多个版本的系统，界面如下图：

![](https://pic.loll.cc/images/2021/08/28/20210828090509.png)

**建议用方案1激活，简单有效！**



## 做一些简单的安全防护工作





### 修改登录的密码



- 使用CMD更改登录密码

```bash
net user administrator 要修改的密码
```







### 修改远程桌面连接的3389端口

在VPS服务器上安装Windows系统，不同于家用电脑。因为服务器直接就是公网I P ，理论上任何人都可以通过远程桌面连接尝试登录服务器。为了安全考虑，我们有必要修改远默认的3389端口。

#### 修改方法

1、W i n + R快捷键调出运行窗口，输入`regedit`回车，打开注册表编辑器。

2、找到以下两个位置的`PortNumber` 值， 将默认的`3389`修改为其它较大端口号，比如`58888`：

 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal
Server\Wds\rdpwd\Tds\tcp`



 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal
Server\WinStations\RDP-Tcp`

3、修改完成后，需要将刚才的端口号添加至系统防火墙放行：


- 打开`开始菜单`——`控制面板`系统和`安全Windows防火墙`——`高级设置`——`入站规则`——`新建规则`。

- 在`新建入站`规则窗口中，依次选择类型为`端口`——`协议TCP` 、端口为刚才设置的`新的端口号`——操作设置为`允许连接`——最后的名称随便一个。

- 防火墙规则添加完成后，重启系统使设置生效。

- 远程桌面连接时，将原来的服务器IP修改为`IP:新端口`的形式，比如`127.0.0.1:58888`

  

## 其他



### 关于安装成功后磁盘变小



- 在控制面板中搜索 “磁盘管理”；
- 点击“创建并格式化磁盘分区”；
- 选中C盘，右键->扩展卷->扩展；
- 刷新后就可看到磁盘大小正常。



### 关于Ping

**安装Windows系统后，服务器IP Ping不通怎么办？**

在部分Windows系统版本中，防火墙规则默认是禁Ping的，这时Ping服务器是Ping不通的。如果你需要测试Ping值延迟，那么就需要在防火墙中允许`ICMP`协议入站。

#### 具体方法

1、打开`控制面板`中的`Windows防火墙`——`高级设置`——`入站规则`——`新建规则`

2、在弹出的`新建入站规则`窗口中，选择类型为`自定义`——程序默认`所有程序`——协议选择`ICMPv4`—— 一路`下一步`保存

3、规则添加成功后，就可以通过Ping命令测试服务器延迟了。



## 最后的叮嘱

**声明：** 这个只是测试使用，如果想要长期稳定使用，还是建议购买自带Windows版本的服务器套餐～

好了，愉快地玩耍起来吧！