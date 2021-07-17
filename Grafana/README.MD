# Grafana

## 本项目特点

1. 需要与 prometheus 配合使用、添加 prometheus 数据源之后即可导入相应的监控模板
2. 持久化数据存储
3. 使用 traefik 进行反代自动化配置

```bash
docker-compose up -d
```

## 图标演示

1. traefik

![](images/Traefik-2-2-Copy-Grafana.png)

2. node-status

![](images/1-Node-Exporter-for-Prometheus-Dashboard-CN-v20201010-Grafana.png)