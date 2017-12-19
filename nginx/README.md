# Nginx

## Build

    docker build -t thomd/nginx:0.1.0 .

## Run

    echo Hello World > public/index.html
    docker run -d --rm --name nginx -p 80:80 -v $(pwd):/var/www/html thomd/nginx:0.1.0

## Serve PHP

The file `default` will replace the default Nginx server configuration so it works with PHP.

Build a new image

    docker build -t thomd/nginx-php:0.1.0 -f Dockerfile_php .

Create a php file

    echo "<?php phpinfo(); ?>" > public/index.php

Spin up a [PHP container](https://github.com/thomd/dockerfiles/tree/master/php-fpm), naming the container _myphp_

    docker run -d --name=myphp -v $(pwd):/var/www/html thomd/php:0.1.0

Spin up Nginx, linking the container _myphp_ and aliasing it to _php_ so the hostname _php_ resolves to the IP address of the _myphp_ container

    docker run -d --link=myphp:php -p 80:80 -v $(pwd):/var/www/html thomd/nginx-php:0.1.0


