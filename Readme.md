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

> with with jrcs' letsencrypt-nginx-proxy-companion

`cd production`