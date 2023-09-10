# nyaShines-Computer-Problems-and-Solutions

这个项目是用来记录我在使用电脑过程中遇到的问题以及我找到的解决方案。

## 问题和解决方案

### 问题1: 在Ubuntu 22.04 LTS上使用Linux版MotionPro连接东华大学校园网后，断开连接无法正常连接网络

**问题描述：**
在Ubuntu 22.04 LTS上，我使用Linux版的MotionPro连接到东华大学的校园网。当我断开连接后，我发现无法正常连接到网络。通过分析，我发现问题在于，启动MotionPro后，它更改了`resolv.conf`和DNS解析器。在关闭MotionPro后，虽然它恢复了`resolv.conf`，但并没有恢复DNS解析器。

**解决方案：**
在停止MotionPro，执行`/opt/MotionPro/vpn_cmdline -s`后，使用`sudo systemctl restart systemd-resolved`命令即可恢复网络连接。
