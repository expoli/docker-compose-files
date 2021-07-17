# qbittorrent

## 本项目特点

1. 支持多种CPU架构
2. 支持 docker 多线程工作、去除下载瓶颈
3. 使用 traefik 作为服务自动发现代理，无需自动配置路由与HTTPS
4. 支持IPv6
5. 支持PT做种
6. 拥有 Web-ui

## 注意

1. 使用时如果使用 `host` 模式、请放行相应的做种端口
2. 同步修改 [web/nginx.conf](web/nginx.conf) 中的后端地址
3. 若开启防火墙、请注意放行对应的web端口 `8888`

```conf
    upstream backend {
        server 192.168.1.106:8888;
    }
```

## 展示

![](images/qBittorrent-Web-UI.png)

![](images/qBittorrent-v4-3-6-Web-UI.png)
