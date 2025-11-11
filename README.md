# Laravel Docker Project

A Laravel project running inside **Docker** with:

- PHP 8.3-FPM
- Nginx
- MySQL
- Node.js & npm (for frontend tooling)
- Composer installed globally

This setup ensures a fully isolated development environment for Laravel applications.

---

## 🚀 Features

- Laravel development environment using Docker
- PHP 8.3 with necessary extensions: `pdo_mysql`, `mbstring`, `exif`, `pcntl`, `bcmath`, `gd`
- Nginx as web server
- MySQL 8.0 database
- Node.js & npm for Laravel Mix / frontend assets
- Composer globally installed
- File permissions configured for Laravel

---

## 🛠 Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

---

## ⚡ Installation / Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
## 🚀 Start the Project


### 1️⃣ Start Docker Containers
```bash
docker compose up -d --build


docker exec -it laravel_app bash

cd /var/www
composer create-project --prefer-dist laravel/laravel .


cp .env.example .env
php artisan key:generate


DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=root


php artisan migrate
