# Linux

## 1. 远程服务器传送文件

Linux的 `scp` 命令用于 Linux 之间复制文件和目录。
`scp` 是 `secure copy` 的缩写, `scp` 是 `linux` 系统下基于 `ssh` 登陆进行安全的远程文件拷贝命令。
`scp` 是加密的，`rcp`是不加密的，`scp` 是 `rcp` 的加强版。

```bash
# 从本地将文件传输到服务器
# scp 本地文件路径 服务器用户名@服务器地址: 服务器存放文件路径
scp /Desktop/test.zip root@192.168.1.1:/root

# 从本地将文件夹传输到服务器
# scp -r 本地文件路径 服务器用户名@服务器地址: 服务器存放文件路径
scp -r /Desktop/test root@192.168.1.1:/root

#从服务器上获取文件夹到本地
# scp 服务器用户名@服务器地址:服务器文件路径  本地文件路径
scp root@192.168.1.1:/root/test.zip /Desktop

# 从服务器上获取文件夹到本地
# scp -r 服务器用户名@服务器地址:服务器文件路径  本地文件路径
scp -r root@192.168.1.1:/root/test  /Desktop
```