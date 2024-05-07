## A Simple Run command for DB

```
docker run -d --name db \
  -e MYSQL_ROOT_PASSWORD=somewordpress \
  -e MYSQL_DATABASE=wordpress \
  -e MYSQL_USER=wordpress \
  -e MYSQL_PASSWORD=wordpress \
  -v db_data:/var/lib/mysql \
  --network mynet \
  -p 3306:3306 \
  mariadb:10.6.4-focal
```


## A Simple Run command for Wordpress


```
docker run -d --name wordpress \
  -e WORDPRESS_DB_HOST=db \
  -e WORDPRESS_DB_USER=wordpress \
  -e WORDPRESS_DB_PASSWORD=wordpress \
  -e WORDPRESS_DB_NAME=wordpress \
  -p 80:80 \
  --network mynet \
  wordpress:latest
```


## A Simple Wordpress App


```
 docker compose up -d --build
```
