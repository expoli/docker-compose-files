# Transmission

## 本项目特点

1. 支持 web-ui
2. 支持 ipv6 (host模式)
3. 支持 PT
4. 使用 traefik 实现自动服务发现

## 注意

1. 使用前请配置好 `docker-compose.yaml` 中的 label 项目
2. 测试时发现改容器存在性能限制、无法多核同时工作
