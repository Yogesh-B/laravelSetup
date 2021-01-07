# Laravel Setup docs
[1.Setup project](#setup)





# setup

1. Install PHP by firing following command
>sudo pacman -S php

2. Install Composer. <br>
	(i). Make a file named `setup.sh` and put following contents in it and save it.

```sh
#!/bin/sh

EXPECTED_CHECKSUM="$(wget -q -O - https://composer.github.io/installer.sig)"
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
ACTUAL_CHECKSUM="$(php -r "echo hash_file('sha384', 'composer-setup.php');")"

if [ "$EXPECTED_CHECKSUM" != "$ACTUAL_CHECKSUM" ]
then
    >&2 echo 'ERROR: Invalid installer checksum'
    rm composer-setup.php
    exit 1
fi

php composer-setup.php --quiet
RESULT=$?
rm composer-setup.php
exit $RESULT
```
	(ii). Make it executable by running `sudo chmod 776 ./setup.sh` and than execute it to install Composer

 3. Install Laravel. <br>
 	Run following commands.(First time it takes more time to setup a project afterwards it is much faster.)
 	```sh
 	composer create-project laravel/laravel example-app

	cd example-app

	php artisan serve
 	```
   (Optional setup/ AUTH)<br>
	(i). Setup auth in Project UI
>composer require laravel/ui

>php artisan ui:auth 
>npm install && npm run dev

(ii). Setup database (sqlite for example)<br>
	a. Open `.env` file and comment all lines having `DB_*` at line start by adding `#` at start.<br>	
	b. Add `DB_CONNECTION=sqlite` line before those commented lines.  <br>
	c. Create file `database/database.sqlite`.(do not write anything! Let it be empty)
	d. Run `php artisan migrate`

Now you are all set with database




