Docker image for old MySQL 5.1 database, based on [official MySQL image](https://github.com/docker-library/mysql)

Build with:

```
docker build -t user/mysql51:latest .
```

Verify with:
```
docker images | grep user/mysql51
```

Run with (data at host:/var/lib/mysql) :
```
docker run --name mysql51 -p 3306:3306 -e MYSQL_ROOT_PASSWORD=12345 -v /var/lib/mysql:/var/lib/mysql -d user/mysql51:latest
```

View log with:
```
docker logs mysql51
```

Command-Line connect to mysql51 on host with:

```
mysql -h localhost --port=3306 --user=root --password --protocol=tcp 
# And type password 12345
```
