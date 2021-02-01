# Running steps

## Dockerized environment

As we have set up the docker environment to run everything, it is very important to follow the steps to make it work.

### Pre-req

Please make sure that you have `docker` and `docker-compose` installed appropriately in your machine. More over please do check the rights are in order as well.

### Steps

#### - Setup Environment (Laravel)

- `cp .env.example .env`
- `nano .env`
- Find and replace

    ```env
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=laravel
    DB_USERNAME=laraveluser
    DB_PASSWORD=your_laravel_db_password
    ```

#### - Let the compose do the magic

- `docker-compose up -d`

#### - Precaution

- Make sure after the above you have 3 visible containers running
- Use `docker ps` to view them
- The should look something of a sort:

    | CONTAINER ID | NAMES     | IMAGE                | STATUS       | PORTS                                      |
    |--------------|-----------|----------------------|--------------|--------------------------------------------|
    | c31b7b3251e0 | db        | mysql:5.7.22         | Up 2 seconds | 0.0.0.0:3306->3306/tcp                     |
    | ed5a69704580 | app       | digitalocean.com/php | Up 2 seconds | 9000/tcp                                   |
    | 5ce4ee31d7c0 | webserver | nginx:alpine         | Up 2 seconds | 0.0.0.0:8899->80/tcp, 0.0.0.0:443->443/tcp |
- At this stage, you are running your laravel swiftly

#### - Laravel specifics

- Do run these commands on your terminal
    - `docker-compose exec app php artisan key:generate`
    - `docker-compose exec app php artisan config:cache`

#### - Magic

Try browsing this site [http://localhost:8899/](http://localhost:8899/) in your favourite browser