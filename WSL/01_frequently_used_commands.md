# WSL commands

## 常用的wsl命令

* `wsl -l -o`: 查看在线的发行版
* `wsl --install {Debian}`: 安装指定的发行版
* `wsl -l -v`: 查看本地安装过的发行版
* `wsl -l --running`: 查看本地的运行中的发行版
* `wsl -l --quiet`: 只查看发行版的名称
* `wsl -d {Debian}`: 运行指定的发行版
* `wsl -d {Debian} --user {ljy}`: 运行指定的发行版，并指定账户
* `wsl --user {ljy}`: 以指定的账户运行默认的发行版
* `wsl -s {Debian}`: 指定默认的发行版
* `{ubuntu2004} config --default-user {joe}`: 为某个发行版指定默认登录的账户
* `wsl --set-version {Ubuntu-20.04 1}`: 为发行版指定运行的版本
* `wsl -t {Ubuntu-20.04}`: 关机指定的发行版
* `wsl --unregister {Ubuntu-20.04}`: 卸载指定的发行版
* `wsl --status`: 查看默认发行版的状态
* `wsl --version`: 查看发行版的版本
* `wsl --set-default-version 2`: 设定WSL的版本
* `wsl hostnanme -i`: 查询默认发行版的IP地址

* `wsl --export {Ubuntu} {C:\Temp\Ubuntu_Backup.tar}`: 导出指定的发行版到指定的路径
* `wsl --import {Ubuntu-GUI} {C:\Temp\Ubuntu_Backup.tar}`: 以指定的名称导入指定的发行版
* 通过导入的方式的发行版不能通过`ubuntu config --default-user xxx`的方式修改默认的账户，只能修改`/etc/wsl.conf`文件来设定

## 在Windows中执行Linux命令

* 语法格式: `wsl Linux命令`
* `wsl ip addr`: 查看IP地址
* `wsl -d Debian hostname -i`: 查看指定发行版的IP地址
* `wsl ls -al ~`: 查看账户的所有文件信息

## 在Linux中执行Windows命令
* `{Windows命令}.exe 参数`
* `ping.exe www.google.com`
* `ipconfig.exe /all`
* `cd ~; explorer.exe .`
* `notepad.exe .bashrc`

## 在Windows中存取Linux子系统的文件
* `type \\wsl.localhost\Ubuntu\home\ljy\test.txt`
* `copy \\wsl.localhost\Ubuntu\home\ljy\test.txt D:\`

## 在Linux子系统存取Windows中的文件
* `cd /mnt/{d} && ls test.txt`