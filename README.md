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
Start Docker containers

bash
Copy code
docker compose up -d --build
Enter PHP container

bash
Copy code
docker exec -it laravel_app bash
Install Laravel inside src/ (if not already present)

bash
Copy code
cd /var/www
composer create-project --prefer-dist laravel/laravel .
Configure environment

bash
Copy code
cp .env.example .env
php artisan key:generate
Update .env for database connection:

env
Copy code
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=root
Run migrations (optional)

bash
Copy code
php artisan migrate
🌐 Access the Application
Open your browser at:

arduino
Copy code
http://localhost
You should see the Laravel welcome page.

🧱 Folder Structure
pgsql
Copy code
laravel-docker/
├── docker-compose.yml
├── php/
│   └── Dockerfile
├── nginx/
│   └── default.conf
└── src/                 <-- Your Laravel application
    ├── app/
    ├── bootstrap/
    ├── config/
    ├── database/
    ├── public/
    ├── routes/
    └── artisan
⚙ Useful Docker Commands
Stop containers:

bash
Copy code
docker compose down
View logs:

bash
Copy code
docker compose logs -f
Rebuild containers:

bash
Copy code
docker compose up -d --build
Enter PHP container:

bash
Copy code
docker exec -it laravel_app bash