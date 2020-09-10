 #  视频教程<a href="https://www.youtube.com/channel/UC2t8e5Yffkyy2ncXVaxHOhQ"><img src="../../tu/youtube.jpg"></a> 
## https://www.youtube.com/channel/UC2t8e5Yffkyy2ncXVaxHOhQ

 ### 系统要求
Centos / Debian / Ubuntu 14.04以上
### 推荐Debian / Ubuntu，这个是我一直使用的系统，我的脚本在这个系统上面出错率最低。

### 安装步骤
wget -N --no-check-certificate https://raw.githubusercontent.com/zwz1018/zwz1018/master/zhongzhuan/zhongzhuan.sh && chmod + x zhongzhuan.sh && bash zhongzhuan.sh

### 运行脚本后，会显示菜单：
<p>iptables扩展转发一键管理脚本[vx.xx] doub.io/wlzy-20-

 <p>0.升级脚本</p><br>
 <p>1. 安装iptables</p><br>
 <p>2.清空iptables扩展转发</p><br>
 <p>3.查看iptables扩展转发</p><br>
 <p>4.添加iptables扩展转发</p><br>
 <p>5.删除iptables扩展转发—</p><br>
<p>注意：初次使用前请请执行1.安装iptables（替代安装）</p><br>
<p>请输入数字[0-5]：</p><br>

### 选择4.添加iptables扩展转发后，会提示你依次输入欲转发IP，欲转发端口，本地监听端口，本地IP，转发类型：
<p>请输入iptables欲转发至的远程端口[1-65535]（支持端口段如2333-6666，被转发服务器）：10000-11000</p><br>

<p>欲转发端口：10000-11000</p><br>

<p>请输入iptables欲转发至的远程IP（被转发服务器）：2.2.2.2</p><br>

<p>欲转发服务器IP：2.2.2.2</p><br>

<p>请输入iptables本地监听端口[1-65535]（支持端口段如2333-6666）（默认端口：10000-11000）：</p><br>

<p>本地监听端口：10000-11000</p><br>

<p>请输入本服务器的公网IP网卡IP（注意是网卡绑定的IP，而多个公网IP，回车自动检测）：</p><br>

<p>本服务器IP：1.1.1.1</p><br>

<p>请输入数字来选择iptables转换类型：</p><br>

<p>TCP协议</p><br>
<p>UDP协议</p><br>
<p>TCP + UDP</p><br>
（TCP：UDP）：</p><br>

<p>请检查iptables是否转发错误！</p><br>

<p>本地监听端口：10000-11000服务器IP：2.2.2.2</p><br>

<p>欲转发的端口：10000-11000欲转发的IP：1.1.1.1转发类型：TCP + UDP</p><br>
<p>最后会提示您确认配置是否有误，如果没有问题就按任意键继续，启动成功后就会提示：

本地监听端口：10000：11000服务器IP：1.1.1.1</p><br>

<p>欲转发的端口：10000：11000欲转发的IP：2.2.2.2转发类型：TCP + UDP</p><br>
### 选择3.查看iptables扩展转发后，会显示如下：
当前有2个iptables扩展转发规则。

类型：tcp监听端口：10000：20000转发IP和端口：2.2.2.2:10000-20000
类型：udp侦听端口：10000：20000返回IP和端口：2.2.2.2:10000-20000选择5.删除iptables将转发向前，也将显示列表，然后让您选择要删除的端口转发规则序号。

### Shadowsocks v2ray客户端说明
假设您的海外服务器（被中转）中构建的Shadowsocks服务端的IP是2.2.2.2，SS端口是10000。

假设中转服务器的IP是1.1.1.1，本地监听端口和SS端口替代，本地监听端口是20000。

那么，你的Shadowsocks客户端，添加Shadowsocks服务器，IP填充1.1.1.1（公网ip），端口填充20000，其他的密码/加密方式/协议/无需等全部和原Shadowsocks账号一样！

### 其他说明
CentOS 7默认的防火墙是防火墙，要使用本脚本，请先卸载或关闭防火墙服务器，并安装iptables完整软件。

### 关于国内腾讯云等服务器转发失败解释
国内的很多服务器，例如腾讯云，在VPS网卡上面绑定的都是内部网IP，这样的话，如果你用脚本自动检测外部网IP，会转发失败，需要在添加转发规则的时候，本服务器IP手动写你的服务器网卡上面绑定的IP。

### ifconfig输入命令后会看到网卡信息，我们看第二行的inet地址：xxx.xxx.xxx.xxx，这里的xxx就是你的网卡绑定的IP。

### 提示wget：未知主机“ raw.githubusercontent.com”之类的错误
这是无法解析我的域名，多半是DNS的问题，请更换DNS为谷歌DNS。
<p>echo -e "nameserver 8.8.8.8\nnameserver 8.8.4.4" > /etc/resolv.conf</p>

### 提示wget：找不到命令的错误
这是你的系统精简的太干净了，wget都没有安装，所以需要安装wget。
 <p>Centos系统:</p><br>
<p>yum install -y wget</p><br>

<p>Debian/Ubuntu系统:</p><br>
apt-get install -y wget

### 更换aptsource，解决安装错误：[错误] iptables安装失败等等
一些VPS的apt源太老旧，导致无法安装或升级iptables，所以我这里写上如何更换aptsource。所以我只针对了这两个系统，Centos的自己去了谷歌yum重置源。
