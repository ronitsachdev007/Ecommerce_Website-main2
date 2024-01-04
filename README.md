## Installation with docker

1.Run composer install

Navigate into project folder using terminal and run

    docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs

2.Copy .env.example into .env

    cp .env.example .env

3.Start the project 

    docker-compose up -d

From now on whenever you want to run artisan command you should do this from the container.
Access to the docker container

    ./vendor/bin/sail bash

4.Set encryption key

    php artisan key:generate --ansi

5.Run migrations

    php artisan migrate

6.Run

    docker exec -it ecommerce_website-laravel.test-1 bash

    npm run dev

6.Add Filament Admin user

    php artisan make:filament-user

