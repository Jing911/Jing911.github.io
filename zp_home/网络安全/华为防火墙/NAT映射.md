> <p style="font-size:30px">NAT-Server映射</p>

1、配置NAT策略</br>
新建规则“源地址转换_TO_互联网”——“trust向untrust转换”


2、配置服务器映射</br>
添加服务器映射—配置名称—安全区域—公网地址—私网地址—公网/私网端口


3、配置安全策略</br>
新建策略—允许“untrust”访问“dmz”—服务里填写端口号


4、命令补充</br>
在防火墙命令行界面，输入以下内容来启用NAT-Server</br>
nat server 策略名称 protocol tcp global interface Dialer0 公网端口 inside 设备IP 私网端口 no-reverse nat-disable</br>
