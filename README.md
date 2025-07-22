# Laravel 12 JWT Authentication API

A simple RESTful API in Laravel 12 using JWT (JSON Web Token) authentication.

---

## 🚀 Features

- User Registration
- JWT-based Authentication (Login & Logout)
- Protected Routes (via `auth:api`)
- Token Invalidation on Logout
- Token-Based User Info (`/me`)

---

## ⚙️ Installation Steps

```bash
# Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Install dependencies
composer install

# Create .env file
cp .env.example .env

# Generate application key
php artisan key:generate

# Configure your database in the .env file

# Run migrations
php artisan migrate

# Install JWT Auth package
composer require tymon/jwt-auth

# Publish JWT config
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"

# Generate JWT secret
php artisan jwt:secret

# Set Guard to api(In config/auth.php, set your API driver to jwt)
'guards' => [
    'api' => [
        'driver' => 'jwt',
        'provider' => 'users',
    ],
],

# (Optional) Publish CORS config if not available
composer require fruitcake/laravel-cors
php artisan vendor:publish --tag="cors"
