## 获取 server：
     apt install curl
     head -c 16 /dev/urandom | xxd -ps
     

## 代码1：
   mkdir /home/mtproxy && cd /home/mtproxy
## 代码2：
    curl -s -o mtproxy.sh https://raw.githubusercontent.com/zwz1018/zwz1018/master/tgdaili/mtproxy.sh && chmod +x mtproxy.sh && bash mtproxy.sh
 使用方式

运行服务

bash mtproxy.sh start

调试运行

bash mtproxy.sh debug

停止服务

bash mtproxy.sh stop

重启服务
 
 bash mtproxy.sh restart

查看配置

 cd /home/mtproxy
 
 bash mtproxy 

卸载安装
 
 rm -rf /home/mtproxy
 
意外情况解决方法
 
 

无法开启执行：yum install vim-common
 

连接不上查看端口是否被墙
 

端口扫描

国外与国内端口扫描对比

 http://tool.chinaz.com/port/

 https://www.yougetsignal.com/tools/open-ports/
 

开启防火墙：

 方法一

 
 启动防火墙   systemctl start firewalld.service
 
 开启 80 443 端口  firewall-cmd --zone=public --add-port=8888/tcp –permanent
 
 重启防火墙：firewall-cmd –reload

方法二
 
 $ /sbin/iptables -I INPUT -p tcp --dport 8888 -j ACCEPT
 
 $ /etc/init.d/iptables save      # 保存

 $ /etc/init.d/iptables status    # 查看端口状态

或者打开配置文件/etc/sysconfig/iptables，加入如下语句，然后重启防火墙：
 
 -A INPUT -p tcp -m state --state NEW -m tcp --dport 你的端口 -j ACCEPT

然后重启防火墙：
 
 $ /etc/init.d/iptables restart
