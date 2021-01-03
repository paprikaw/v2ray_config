# v2ray_config

> - This repository includes both server and client end of configurations for v2ray
> - This configuration use AWS ec2 debian 9 instance as server.

# 基础配置步骤：

### 服务器端：

- 下载 nginx，使用默认配置
- 利用官方安装脚本在 service end 安装 v2ray
  - 打开脚本[github repositry](https://github.com/v2fly/fhs-install-v2ray)
  - 按照指示安装
- 下载配置文件到正确的配置位置

  > 通常 v2ray 的配置文件路径是/usr/local/etc/v2ray/config.json, 以下命令中这个路径可被替换成任何有效的配置文件路径

  ```
  curl -o /usr/local/etc/v2ray/config.json https://raw.githubusercontent.com/paprikaw/v2ray_config/main/server_end/config.json
  ```

### 客户端：
#### 配置文件位置：
* v2ray 资源文件：/usr/local/share/v2ray
* v2ray 配置文件：/usr/local/etc/v2ray
  
#### 配置步骤：
- mac 用户 GUI 可以选择 [V2rayU](https://github.com/yanue/V2rayU/releases)，windows 用户和 Linux 用户请自行搜索 GUI 客户端
- 使用 v2ray command-line version 可以使用以下命令获取 config.json：
  > 同理，请将以下命令中 confij.json 的路径替换成你的路径
  ```
  curl -o /usr/local/etc/v2ray/config.json https://raw.githubusercontent.com/paprikaw/v2ray_config/main/client_end/config.json
  ```

# Useful shell script
## sync-config
* 根据本地的v2ray_config仓库，同步更新客户端和服务端v2ray配置，具体用法请移步 [我的shell script 仓库](https://github.com/paprikaw/shell_script_learning)

# 参考

[v2ray+tls 配置方法](https://github.com/bannedbook/fanqiang/blob/master/v2ss/%E8%87%AA%E5%BB%BAV2Ray%2BTLS%E7%BF%BB%E5%A2%99%E9%85%8D%E7%BD%AE%E6%96%B9%E6%B3%95.md)

[v2ray 各平台基础配置（包括移动平台）](https://book.v2rayx.org/index.html)

[TLS + TCP + VLESS 配置参考](<https://github.com/v2fly/v2ray-examples/tree/master/VLESS-TCP-TLS-WS%20(recommended)>)
