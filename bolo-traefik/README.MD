# bolo

bolo 博客的 `traefik` 后端配置

只需要修改 env 文件与 `docker-compose` 中相应的 label 即可

本项目专注于使用 docker-compose 进行容器的编排，实现 Bolo 博客的一键启动，以避免广大人民群众在进行 bolo 部署时走不必要的弯路；降低了使用门槛，同时也大大增加了维护与迁移的便利性，同时也增加了 Let's Encrypt SSL证书的自动配置与续签。

一键部署脚本传送门(傻瓜式、欢迎试用) https://github.com/expoli/start-bolo

详细请参阅：https://github.com/expoli/start-bolo-with-docker-compose
