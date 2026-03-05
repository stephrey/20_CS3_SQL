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


<a id="chapter2"></a>
# 2. SQlite example

</br>

[back](#contentab)</br>

