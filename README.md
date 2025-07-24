1) Install Laravel
composer create-project laravel/laravel

2) Install spatie
composer require spatie/laravel-permission

3)Puslish vendor service provider
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"

4) Install Laravel UI
composer require laravel/ui

5)Install bootstrap auth for login/registration
php artisan ui bootstrap --auth

6) Run Migration 
php artisan migrate 

7) Run Seeder - Permission Table Seeder
php artisan db:seed --class=PermissionTableSeeder

8) Run Seeder - Admin User Seeder
php artisan db:seed --class=CreateAdminUserSeeder 
 
9) php artisan serve

10) login for Admin
User- admin@gmail.com
password - admin@123