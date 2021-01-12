# LARAVEL 6 with MYSQL

> composer create-project --prefer-dist laravel/laravel app2 "6.*"

> docker run --name docker-mysql -v /dockermysqldata:/var/lib/mysql -p 3306:3306/tcp -c 900 -e MYSQL_ALLOW_EMPTY_PASSWORD=yes -d mysql:5.7.9
<br>



OS permissions issues...

```sh
sudo groupadd docker
sudo gpasswd -a ${USER} docker
sudo systemctl enable docker
sudo systemctl start docker
newgrp docker
```


afterwards.<br>
to stop docker.... `docker stop docker-mysql`

to start docker.... `docker start docker-mysql`

<br>


Setup a MySql connection in DBeaver to check results, also create a  database named 'Laravel'.

<br>

Change following parameters as below:
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=Laravel
DB_USERNAME=root
DB_PASSWORD=

```

Run `php artisan migrate`


.....happy coding......