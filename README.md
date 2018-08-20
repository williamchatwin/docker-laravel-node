## Docker Laravel Node Starter Kit  

This Project is a simple starter kit so that you can get started easily with docker, laravel, and node

#### Use (docker CE required)  
Simply run the command:  
` docker-compose up -d`

## Web Server: 
nginx web server: `http://localhost:8080`

## Container Actions:

` docker-compose exec php bash`  

This command will land you at `/var/www/app`  
###### Versions:
* `php -v`
* `composer -V`
* `php artisan --version`
* `node -v`
* `npm -v`

###### Commands:  
* Run `php artisan [commands]`
* Run `composer [commands]`
* Run `node [commands]`


##### Description: 
This will launch a php code base, nginx web server on port 8080, and a mysql db.

Visit: locolhost:8080 after you have ran the above command. You should see the Laravel Home page

This starter kit will be useful for developing php Packages.  

