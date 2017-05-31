---
title: 通过docker安装gogs
---
# 通过docker安装gogs
## 命令行step1
```
docker pull gogs/gogs
docker pull mysql
```
## 命令行step2
```
docker run -ti -d -v  ~/dockerdata/logs/mysql:/var/log/mysql -v ~/dockerdata/data/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=yzBXf7KGe8 --name mysql-gogs -p 13306:3306  --restart=always mysql
docker run -ti -d --name gogs -p 10022:22 -p 3000:3000  --link mysql-gogs:gogsdb -v ~/dockerdata/data/gogs:/data gogs/gogs
```