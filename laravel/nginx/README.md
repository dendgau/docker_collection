# Build docker
cd laravel/nginx
docker-compose build
docker-compose up -d

# Exec docker and migrate database
docker exec -it backend bash
composer install
php artisan key:generate
php artisan migrate:fresh --seed