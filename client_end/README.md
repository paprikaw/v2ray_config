* 本配置DNS及routing部分参考 [Loyalsoldier的v2ray-rules增强版](https://github.com/Loyalsoldier/v2ray-rules-dat) 中的自用配置
* 此配置中的geoip和geosite包是 [Loyalsoldier的v2ray-rules增强版](https://github.com/Loyalsoldier/v2ray-rules-dat) 中所构建的，如果需要使用本配置需要安装此增强包

目前位置的路由设置路径：
假设客户端收到一个本地域名, 接下来将会经历以下几个步骤：
* inbound收到域名
* 域名将进入routing，进行路由规则匹配
* 第一种情况，域名匹配到geosite，将直接走Direct
  * 由于Direct走的是freedom协议，而freedom设置了domainStrategy，所以域名将使用v2ray内建DNS服务器
    * 如果域名匹配到中国地址并且在经过DNS查询只有获得了正确的中国ip，那么直接向此ip发起DOH连接
    * 如果域名未正确找到中国ip，那么将使用谷歌的https dns服务器查询。此时，DNS服务器向谷歌的HTTPS DNS服务器发起连接，这个连接将经过路由规则，被重新分流至内置的DNS服务器。内置的DNS服务器匹配到dns.google, 所以会直接向8.8.8.8发起DNS请求。返回的结果被接收到再走一次路由规则，最后由于没有匹配任何规则，走proxy。
* 第二种情况

什么情况下会用到DNS设置？
* 域名没有任何匹配的情况下