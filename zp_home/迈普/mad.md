> <p style="font-size:30px">MAD</p>

注意事项：VST配置完成后重启确认VST正常再配置MAD

- <b><p style="font-size:17px">1. 配置命令</p>
|命令|注释|
|:-:|:-:|
enable|进入特权模式|
configure terminal|进入全局配置模式|
vlan 4094|配置检测VLAN|
 name MAD_VLAN|添加注释|
 mad fast-hello control-vlan|配置控制VLAN，用于传递MAD协议报文|
 exit|退出|
interface fortygigabitethernet1/0/51-1/0/52,2/0/51-2/0/52|进入BFD检测物理端口|
 description MAD|添加注释|
 switchport mode trunk|端口模式配置Trunk|
 no spanning-tree enable|关闭生成树|
 mad fast-hello vlan 4094|添加MAD控制VLAN|
 exit|退出|

 查看MAD状态：</p>
|命令|注释|
|:-:|:-:|
show mad fast-hello|查看MAD信息|
show mad status|查看MAD状态|