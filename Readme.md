# Pydio Cells with Mysql

# Install

Install docker and docker-compose

# Launch on localhost

`cd localhost`
Create / Update `.env` in the root dir

```h
PYDIO_URL=localhost
MYSQL_ROOT_PASSWORD=rootPassword
MYSQL_DATABASE=pydio
MYSQL_USER=pydio
MYSQL_PASSWORD=pydio
```

then

`docker-compose up`

> TIPS:
>If you `docker-compose down`
>You have to go to `Cels console/data managment/storages/` and update the datasources with the container id number actually running PyDio Cells 

# Launch on production

> with docker image jrcs' letsencrypt-nginx-proxy-companion

`cd production`

`docker-compose up`

> During the installation
> Select socket with `/var/run/mysqld/mysqld.sock` 

> After install success
> mod the pydio.json `sudo vim cells/pydio.json`

#### from

```json
 16   "defaults": {
 17     "database": "your_docker_id",
 18     "datasource": "pydiods1",
 19     "url": "http://sub.yourdomain:8888",
 20     "urlInternal": "http://0.0.0.0:8888"
 21   },
```

#### to

```json
 16   "defaults": {
 17     "database": "your_docker_id",
 18     "datasource": "pydiods1",
 19     "url": "https://sub.yourdomain",
 20     "urlInternal": "http://0.0.0.0:8888"
 21   },
```

`ERROR   pydio.rest.frontend     cannot init oidc provider`