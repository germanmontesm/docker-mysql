docker-mysql
------------

Docker mysql container template used to create development environment.

To build run:

```
$ docker.io build -t wiliamsouza/mysql .
```

Change `wiliamsouza` to your Docker
[index](https://index.docker.io/u/wiliamsouza/) username.

Environment variable
--------------------

You pass with ``-e`` docker option.

* ``MYSQL_ROOT_PASSWORD``: Root password.
* ``MYSQL_DATABASE``: Database name.
* ``MYSQL_USER``: If ``MYSQL_DATABASE`` is specified create a user.
* ``MYSQL_PASSWORD``: Password for ``MYSQL_USER``.
* ``MYSQL_CHARACTER_SET``: Character set for ``MYSQL_DATABASE``.
* ``MYSQL_COLLATE``: Collate for ``MYSQL_DATABASE``.
* ``GRANT_HOSTNAME``: Hostname used on ``GRANT`` for ``MYSQL_DATABASE``.

Shell access:

```
$ docker.io run --name mysql -p 3306:3306 -i \
-v /home/wiliam/devel/docker-mysql/data/log:/var/log/mysql \
-v /home/wiliam/devel/docker-mysql/data/mysql:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=12345 -e MYSQL_DATABASE=api -e MYSQL_USER=api \
-e MYSQL_PASSWORD=12345 -t wiliamsouza/mysql /bin/bash
```

Usage:

```
$ docker.io run --name mysql -p 3306:3306 -d
-v /home/wiliam/devel/docker-mysql/data/log:/var/log/mysql \
-v /home/wiliam/devel/docker-mysql/data/mysql:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=12345 -e MYSQL_DATABASE=api -e MYSQL_USER=api \
-e MYSQL_PASSWORD=12345 -t wiliamsouza/mysql
```