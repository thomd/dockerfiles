# PHP

The file `php-fpm.conf` has two changes from the defaults:

    error_log = /proc/self/fd/2
    daemonize = no

The file `www.conf` has two changes from the default:

    listen = 0.0.0.0:9000
    access.log = /proc/self/fd/1

## Build

    docker build -t thomd/php:0.1.0 .

## Run

    docker run -it --rm thomd/php:0.1.0 php -v
    docker run -it --rm thomd/php:0.1.0 composer -v
