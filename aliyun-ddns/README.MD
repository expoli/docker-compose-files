# 项目地址

https://github.com/sanjusss/aliyun-ddns

# 参数介绍

| 参数名称 | 注释 | 默认值 |
| :---- | :----- | :--- |
|u|阿里云的Access Key ID。[获取阿里云AccessToken](https://usercenter.console.aliyun.com/)|access key id|
|p|阿里云的Access Key Secret。|access key secret|
|d|需要更新的域名，可以用“,”隔开。<br>可以指定线路，用“:”分隔线路和域名([线路名说明](https://help.aliyun.com/document_detail/29807.html?spm=a2c4g.11186623.2.14.42405eb4boCsnd))。<br>例如：“baidu.com,telecom:dianxin.baidu.com”。|my.domain.com|
|i|更新间隔，单位秒。建议大于等于TTL/2。|300|
|t|服务器缓存解析记录的时长，单位秒，普通用户最小为600。|600|
|timezone|输出日志时的时区，单位小时。|8|
|type|需要更改的记录类型，可以用“,”隔开，只能是“A”、“AAAA”或“A,AAAA”。|A,AAAA|
|cnipv4|检查IPv4地址时，仅使用中国服务器。|false|
|webhook|WEBHOOK推送地址。|无|
|checklocal|是否检查本地网卡IP。此选项将禁用在线API的IP检查。|false|
|ipv4nets|本地网卡的IPv4网段。格式示例：“192.168.1.0/24”。多个网段用“,”隔开。|无|
|ipv6nets|本地网卡的IPv6网段。格式示例：“240e::/16”。多个网段用“,”隔开。|无|