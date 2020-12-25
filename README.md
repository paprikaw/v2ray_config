# v2ray_config

> This repository includes both server and client end of configuration for v2ray
> 
> This configuration use AWS ec2 debian 9 instance as server.
# 基础配置步骤：

#### 服务器端：
* 利用官方安装脚本在service end 安装v2ray
  * 打开脚本[github repositry](https://github.com/v2fly/fhs-install-v2ray)
  * 按照指示安装
* 下载配置文件到正确的配置位置
    
    通常v2ray的配置文件路径是/usr/local/etc/v2ray/config.json, 以下命令中这个路径可被替换成任何有效的配置文件路径

    ```
     curl -o /usr/local/etc/v2ray/config.json https://raw.githubusercontent.com/paprikaw/v2ray_config/main/server_end/config.json 
     ```
    
#### 客户端：
在这里我使用的是 [V2rayU](https://github.com/yanue/V2rayU/releases), 完全使用客户端GUI配置. 具体配置选项如下：


# 参考
[v2ray+tls配置方法](https://github.com/bannedbook/fanqiang/blob/master/v2ss/%E8%87%AA%E5%BB%BAV2Ray%2BTLS%E7%BF%BB%E5%A2%99%E9%85%8D%E7%BD%AE%E6%96%B9%E6%B3%95.md)

[v2ray各平台基础配置（包括移动平台）](https://book.v2rayx.org/index.html)f

