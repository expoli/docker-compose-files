# Custom DERP Servers

Tailscale 运行分布在世界各地的 DERP 中继服务器，以在 NAT 遍历期间将您的 Tailscale 节点对等连接作为侧通道，并作为 NAT 遍历失败和无法建立直接连接的后备。 

本文将会介绍如何让 Tailscale 使用自定义的 DERP Servers。

镜像地址：https://github.com/fredliang44/derper-docker

# 配置详解

| env                 | required | description                                                            | default value     |
| ------------------- | -------- | ---------------------------------------------------------------------- | ----------------- |
| DERP_DOMAIN         | true     | derper server hostname                                                 | your-hostname.com |
| DERP_CERT_DIR       | false    | directory to store LetsEncrypt certs(if addr's port is :443)           | /app/certs        |
| DERP_CERT_MODE      | false    | mode for getting a cert. possible options: manual, letsencrypt         | letsencrypt       |
| DERP_ADDR           | false    | listening server address                                               | :443              |
| DERP_STUN           | false    | also run a STUN server                                                 | true              |
| DERP_HTTP_PORT      | false    | The port on which to serve HTTP. Set to -1 to disable                  | 80                |
| DERP_VERIFY_CLIENTS | false    | verify clients to this DERP server through a local tailscaled instance | false             |


# 运行
```
docker-compose up -d
```

官方文档：https://tailscale.com/kb/1118/custom-derp-servers/
原理详解：https://icloudnative.io/posts/custom-derp-servers/