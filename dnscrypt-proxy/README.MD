# dnscrypt-proxy

## 主项目地址

https://github.com/DNSCrypt/dnscrypt-proxy
https://github.com/melchor629/docker-dnscrypt-proxy

## 软件介绍

灵活的 DNS 代理，支持现代加密 DNS 协议，例如 DNSCrypt v2、DNS-over-HTTPS、匿名 DNSCrypt 和 ODoH（Oblivious DoH）。
> A flexible DNS proxy, with support for modern encrypted DNS protocols such as DNSCrypt v2, DNS-over-HTTPS, Anonymized DNSCrypt and ODoH (Oblivious DoH).

## 本项目特点

1. 使用 docker-compose 进行配置、开箱即用
2. 支持自定义配置
3. 默认启用 chinalist 
4. 提供多种配置模板

## docker-compose 文件

```yaml
version: '3.6'

services:
  server:
    image: melchor9000/dnscrypt-proxy
    ports:
      - target: 5353
        published: 53
        protocol: udp
        mode: host
      - target: 5353
        published: 53
        protocol: tcp
        mode: host
    restart: always
    volumes:
      #Here I have the toml and txt files
      #The cache is stored in another folder, but is not persisted
      - "./conf/dnscrypt-proxy.toml:/etc/dnscrypt-proxy/dnscrypt-proxy.toml"
      - "./conf/chinalist.txt:/etc/dnscrypt-proxy/chinalist.txt"
      - "./conf/cloaking-rules.txt:/etc/dnscrypt-proxy/cloaking-rules.txt"
      - "./conf/resolvers:/etc/dnscrypt-proxy/resolvers"
#    deploy:
#      mode: replicated
#      replicas: 2
```

