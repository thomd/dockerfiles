## build

    docker build -t thomd/nginx:0.1.0 .

## run

    echo Hello World > index.html
    docker run -d --rm --name nginx -p 80:80 -v $(pwd):/var/www/html thomd/nginx:0.1.0

## Nginx serving PHP

The file `default` will replace the default Nginx server configuration (virtualhost) so it works with PHP.

    echo "<?php phpinfo(); ?>" > public/index.php

  Spin up PHP, naming the container _myphp_

    docker run -d --name=myphp -v $(pwd):/var/www/html thomd/php:0.1.0

  Spin up Nginx, linking the container _myphp_ and aliasing it to _php_ so the hostname _php_ resolves to the IP address of the _myphp_ container

    docker run -d --link=myphp:php -p 80:80 -v $(pwd):/var/www/html thomd/nginx:0.1.0


