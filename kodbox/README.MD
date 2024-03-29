# kodbox

## 项目地址

https://github.com/KodCloud-dev/docker

## 本项目特点

1. 容器版本更新
2. 使用环境变量自动配置
3. 通过相应 secret 文件简化配置

## docker-compose

```yaml
version: "3.5"

services:
  db:
    image: mariadb:10.6.1
    command: --transaction-isolation=READ-COMMITTED --binlog-format=ROW
    volumes:
      - "./db:/var/lib/mysql"
      - "./mysql-init-files:/docker-entrypoint-initdb.d"
    environment:
      - "TZ=Asia/Shanghai"
      - "MYSQL_ALLOW_EMPTY_PASSWORD=yes"
      - "MYSQL_DATABASE_FILE=/run/secrets/mysql_db"
      - "MYSQL_USER_FILE=/run/secrets/mysql_user"
      - "MYSQL_PASSWORD_FILE=/run/secrets/mysql_password"
    restart: always
    secrets:
      - mysql_db
      - mysql_password
      - mysql_user

  app:
    image: kodcloud/kodbox:v1.20
#    ports:
#      - 80:80
    links:
      - db
      - redis
    volumes:
      - "/data/1TB/kodbox:/var/www/html"
      - "/data/1TB/Transmission/downloads/complete:/downloads"
    environment:
      - "MYSQL_SERVER=db"
      - "MYSQL_DATABASE_FILE=/run/secrets/mysql_db"
      - "MYSQL_USER_FILE=/run/secrets/mysql_user"
      - "MYSQL_PASSWORD_FILE=/run/secrets/mysql_password"
      - "SESSION_HOST=redis"
    restart: always
    secrets:
      - mysql_db
      - mysql_password
      - mysql_user
    labels:
      - "traefik.enable=true"
      - "traefik.port=80"
      - "traefik.http.routers.kodbox.rule=Host(`kodbox.example.org`)"
      - "traefik.http.routers.kodbox.entrypoints=websecure"
      - "traefik.http.routers.kodbox.tls.certresolver=myresolver"

  redis:
    image: redis:alpine3.12
    environment:
      - "TZ=Asia/Shanghai"
    restart: always

secrets:
  mysql_db:
    file: "./mysql_db.txt"
  mysql_password:
    file: "./mysql_password.txt"
  mysql_user:
    file: "./mysql_user.txt"

```
