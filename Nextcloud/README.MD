# Nextcloud

Nextcloud docker-compose 配置

## 本项目特点

1. 使用 mariadb 作为数据库、支持arm架构
2. 启用 redis 支持
3. 启用定时任务
4. 使用环境变量完成自动化配置

## 注意

1. 使用前请相应配置好 `docker-compose.yaml` 文件中的 label 标签，保证 `treafik` web服务器的正常工作。
2. 试用前请配置好数据库的密码与用户的连接操作

## 环境变量

- nextcloud.env
自动化配置环境变量，注意同步修改
```env
NEXTCLOUD_ADMIN_USER=
NEXTCLOUD_ADMIN_PASSWORD=
NEXTCLOUD_TRUSTED_DOMAINS=nextcloud.example.org
SMTP_HOST=smtp.163.com
SMTP_SECURE=ssl
SMTP_NAME=
SMTP_PASSWORD=
MAIL_FROM_ADDRESS=
MAIL_DOMAIN=163.com
```

- db.env

```env
MYSQL_PASSWORD=
MYSQL_DATABASE=nextcloud
MYSQL_USER=nextcloud
```