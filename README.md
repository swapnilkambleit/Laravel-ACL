# Laravel 10 API‑First Project (PHP 8)

A starter template for building **API‑first Laravel applications** using PHP 8.1+, Laravel 10, and Sanctum for authentication. Includes authentication, CRUD for products, request validation, and PHPUnit feature tests.

---

## Features
- 🔐 Token‑based authentication using **Laravel Sanctum**
- 👤 Auth endpoints: Register, Login, Logout
- 📦 Product CRUD API (Create, Read, Update, Delete)
- ✅ Validation with Form Requests
- 🧪 PHPUnit Feature tests for authentication and CRUD
- ⚡ Uses SQLite in‑memory for fast test runs

---

## Installation

### Prerequisites
- PHP >= 8.1
- Composer
- SQLite or MySQL

### Setup
```bash
# Clone project
git clone <your-repo-url> api-demo
cd api-demo

# Install dependencies
composer install

# Copy env file
cp .env.example .env

# Generate app key
php artisan key:generate

# Run migrations
php artisan migrate
```

### Install Sanctum
```bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\\Sanctum\\SanctumServiceProvider"
php artisan migrate
```

---

## API Routes

### Public Routes
- `POST /api/register` → Register new user
- `POST /api/login` → Login and receive token

### Protected Routes (require `Authorization: Bearer <token>` header)
- `POST /api/logout` → Logout (invalidate token)
- `GET /api/products` → List products
- `POST /api/products` → Create product
- `GET /api/products/{id}` → Show product
- `PUT /api/products/{id}` → Update product
- `DELETE /api/products/{id}` → Delete product

---

## Example Requests

### Register
```http
POST /api/register
Content-Type: application/json

{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "password": "secret123",
  "password_confirmation": "secret123"
}
```

### Login
```http
POST /api/login
Content-Type: application/json

{
  "email": "jane@example.com",
  "password": "secret123"
}
```

Response:
```json
{
  "user": { "id": 1, "name": "Jane Doe", "email": "jane@example.com" },
  "token": "1|XyZAbCdEfGh..."
}
```

Use the token:
```
Authorization: Bearer 1|XyZAbCdEfGh...
```

---

## Running Tests

This project includes PHPUnit Feature tests for auth and products.

Run all tests:
```bash
php artisan test
```

Run only auth tests:
```bash
php artisan test --filter=AuthTest
```

Run only product tests:
```bash
php artisan test --filter=ProductTest
```

---

## Test Coverage (What is tested)

### AuthTest
- ✅ Register: creates user and returns token
- ✅ Login: valid credentials return token
- ✅ Invalid login: returns 401 with validation error
- ✅ Logout: revokes token

### ProductTest
- ✅ Guests cannot access product routes (401)
- ✅ Authenticated user can perform full CRUD
- ✅ Validation errors return 422

---

## Development Notes
- Uses **Sanctum tokens** (not cookies) → suitable for mobile apps & SPAs
- Uses **FormRequest validation** for clean controllers
- Uses **SQLite memory database** for tests → fast & isolated
- Extend with API Resources or Swagger docs for production
 
