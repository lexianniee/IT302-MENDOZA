# Multi-Container Docker Compose Stack

This repository contains a self-contained development stack for PHP, Nginx, MySQL, Redis, phpMyAdmin, Mailhog, and a workspace container.

## Services

- `nginx` on ports `80` and `443`
- `php` built from `./php/Dockerfile`
- `mysql` on port `3306`
- `phpmyadmin` on port `8080`
- `workspace` for shell access
- `redis` on port `6379`
- `mailhog` on ports `1025` and `8025`

## Start

```bash
docker-compose up -d
```

If you are using the newer Docker Compose plugin, this also works:

```bash
docker compose up -d
```

## Verify

- Open `http://localhost` to confirm Nginx and PHP are serving `app/index.php`.
- Open `http://localhost:8080` to access phpMyAdmin.
- Open `http://localhost:8025` to access Mailhog.
- Use `docker-compose ps` to confirm all containers are running.

## Notes

- MySQL credentials are set to `it302_mendoza` for root password, database, user, and password.
- The Nginx virtual host forwards PHP requests to the `php` service on port `9000`.
