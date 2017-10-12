## build

    docker build -t thomd/nginx:0.1.0 .

## run

    echo Hello World > index.html
    docker run -d --rm --name nginx -p 80:80 -v $(pwd):/var/www/html thomd/nginx:0.1.0
