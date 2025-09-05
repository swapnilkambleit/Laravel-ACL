# Laravel 10 Project with Spatie Roles & Permissions + Bootstrap Auth

This project is a Laravel 10 application preconfigured with:

- [Spatie Laravel Permission](https://spatie.be/docs/laravel-permission) for role & permission management
- [Laravel UI](https://github.com/laravel/ui) with Bootstrap authentication scaffolding (login & registration)
- Pre-seeded Admin user with roles/permissions

---

## 🚀 Installation Guide

Follow these steps to set up the project locally.

### 1. Install Laravel
```bash
composer create-project laravel/laravel project-name
cd project-name
```

### 2. Install Spatie Laravel Permission
```bash
composer require spatie/laravel-permission
```

### 3. Publish Vendor Files
```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
```

### 4. Install Laravel UI
```bash
composer require laravel/ui
```

### 5. Scaffold Bootstrap Auth (Login & Registration)
```bash
php artisan ui bootstrap --auth
npm install && npm run dev
```

### 6. Run Migrations
```bash
php artisan migrate
```

### 7. Seed Permissions
```bash
php artisan db:seed --class=PermissionTableSeeder
```

### 8. Seed Admin User
```bash
php artisan db:seed --class=CreateAdminUserSeeder
```

### 9. Serve the Application
```bash
php artisan serve
```

---

## 🔑 Default Admin Login

Use the following credentials to log in as an **Admin**:

- **Email:** `admin@gmail.com`  
- **Password:** `admin@123`

---

## 📦 Features

- Laravel 10 + PHP 8.1+
- Spatie Roles & Permissions
- Bootstrap 5 Authentication (Login / Register)
- Preloaded Admin Role & User
- Example Seeders (`PermissionTableSeeder`, `CreateAdminUserSeeder`)
 
