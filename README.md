<a id="contenttab"></a>
<h1 style="text-align: center;">Program example for using databases on PFC200</h1>
Stéphane Rey</br>
05.03.2026</br>
</br>
Table of content

1. [MySQL example](#chapter1)</br>
2. [SQlite example](#chapter2)</br>

</br>
***
<a id="chapter1"></a>

# 1. MySQL example

In this example, we use a Docker container to host the MySQL database. The database is stored on the SD card, while the Docker containers are stored in internal flash memory.

## PFC configuration to use the SD card as data storage

```
ls /media/sdcard/ -l
mkdir -m 777 /media/sdcard/mysql
```
</br>

[back](#contentab)</br>

## Docker container installation

```
enable docker
docker info
docker network create --driver=bridge --subnet=172.28.0.0/16 --ip-range=172.28.0.0/20 mysqlnet
docker run -d --restart always --platform=linux/arm/v7 --network mysqlnet --ip 172.28.0.10 --name mysql -p 3306:3306 -v /etc/localtime:/etc/localtime -v /media/sdcard/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password1 -e MYSQL_PASSWORD=password1 -e MYSQL_USER=user1 -e MYSQL_DATABASE=database1 biarms/mysql:5
docker ps
```
</br>

[back](#contentab)</br>

## Check if the database is working

```
show databases;
use database1;
show tables;
CREATE TABLE  myTable ( id INT AUTO_INCREMENT PRIMARY KEY, nom VARCHAR(100), prenom VARCHAR(100), created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
show tables;
select * from myTable;
INSERT INTO myTable (nom, prenom) VALUES ('Rey', 'Stephane');
select * from myTable;
drop myTable;
```
</br>

[back](#contentab)</br>

<a id="chapter2"></a>
# 2. SQlite example

</br>

[back](#contentab)</br>

