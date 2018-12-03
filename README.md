# Docker + Alpine-3.8 + Mysql/MariaDB-10.3.10

#### parameter

* `MYSQL_ROOT_PWD` : root Password   default "mysql"
* `MYSQL_USER`     : new User
* `MYSQL_USER_PWD` : new User Password
* `MYSQL_USER_DB`  : new Database for new User

#### build image

```
$ docker build -t="meg4r0m/alpine-mysql" .
```

#### run a default contaier

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 meg4r0m/alpine-mysql
```

#### run a container with new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=rootdb -e MYSQL_USER=dev -e MYSQL_USER_PWD=devdb meg4r0m/alpine-mysql
```

#### run a container with new Database for new User and Password

```
$ docker run --name mysql -v /mysql/data/:/var/lib/mysql -d -p 3306:3306 -e MYSQL_ROOT_PWD=rootdb -e MYSQL_USER=dev -e MYSQL_USER_PWD=devdb -e MYSQL_USER_DB=userdbdev meg4r0m/alpine-mysql
