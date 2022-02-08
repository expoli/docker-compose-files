# Gitea

## 环境变量
您可以通过环境变量配置 Gitea 的一些设置：

（默认值以粗体显示）

- APP_NAME：**“Gitea: Git with a cup of tea”**：应用程序名称，在页面标题中使用。
- RUN_MODE：**prod**：应用程序运行模式，会影响性能和调试。“dev”，“prod"或"test”。
- DOMAIN：**localhost**：此服务器的域名，用于 Gitea UI 中显示的 http 克隆 URL。
- SSH_DOMAIN：**localhost**：该服务器的域名，用于 Gitea UI 中显示的 ssh 克隆 URL。如果启用了安装页面，则 SSH 域服务器将采用以下形式的 DOMAIN 值（保存时将覆盖此设置）。
- SSH_PORT：**22**：克隆 URL 中显示的 SSH 端口。
- SSH_LISTEN_PORT：**%(SSH_PORT)s**：内置 SSH 服务器的端口。
- DISABLE_SSH：**false**：如果不可用，请禁用 SSH 功能。如果要禁用 SSH 功能，则在安装 Gitea 时应将 SSH 端口设置为 0。
- HTTP_PORT：**3000**：HTTP 监听端口。
- ROOT_URL：""：覆盖自动生成的公共 URL。如果内部 URL 和外部 URL 不匹配（例如在 Docker 中），这很有用。
- LFS_START_SERVER：**false**：启用 git-lfs 支持。
- DB_TYPE：**sqlite3**：正在使用的数据库类型[mysql，postgres，mssql，sqlite3]。
- DB_HOST：**localhost:3306**：数据库主机地址和端口。
- DB_NAME：**gitea**：数据库名称。
- DB_USER：**root**：数据库用户名。
- DB_PASSWD：**"<empty>”** ：数据库用户密码。如果您在密码中使用特殊字符，请使用“您的密码”进行引用。
- INSTALL_LOCK：**false**：禁止访问安装页面。
- SECRET_KEY：**""** ：全局密钥。这应该更改。如果它具有一个值并且 INSTALL_LOCK 为空，则 INSTALL_LOCK 将自动设置为 true。
- DISABLE_REGISTRATION：**false**：禁用注册，之后只有管理员才能为用户创建帐户。
- REQUIRE_SIGNIN_VIEW：**false**：启用此选项可强制用户登录以查看任何页面。
- USER_UID：**1000**：在容器内运行 Gitea 的用户的 UID（Unix 用户 ID）。如果使用主机卷，则将其与 /data 卷的所有者的 UID 匹配（对于命名卷，则不需要这样做）。
- USER_GID：**1000**：在容器内运行 Gitea 的用户的 GID（Unix 组 ID）。如果使用主机卷，则将其与 /data 卷的所有者的 GID 匹配（对于命名卷，则不需要这样做）。

## 完整配置文件链接

[https://github.com/go-gitea/gitea/blob/main/custom/conf/app.example.ini](https://github.com/go-gitea/gitea/blob/main/custom/conf/app.example.ini)