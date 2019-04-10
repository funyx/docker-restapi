#docker-php-boilerplate
lamp setup using docker ([docs](https://docs.docker.com/)). Uses :
  - [httpd:2.4.37-alpine](https://hub.docker.com/_/httpd?tab=tags)
  - [php:7.3.4-fpm-alpine3.9](https://hub.docker.com/_/php?tab=tags)
  - [mysql:8.0](https://hub.docker.com/_/mysql?tab=tags)
  - [redis:5.0.4-alpine3.9](https://hub.docker.com/_/redis?tab=tags)

#### setup
- copy `.env.example` into `.env` 
- change the variables in `.env`
- place your app in the `www` folder
- start the service (in the root folder)
```bash
docker-compose up
```

