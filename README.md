<p>
1) Install Laravel
composer create-project laravel/laravel
</p>
<p>
2) Install spatie
composer require spatie/laravel-permission
</p>
<p>
3)Puslish vendor service provider
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
</p>
<p>
4) Install Laravel UI
composer require laravel/ui
</p>
<p>
5)Install bootstrap auth for login/registration
php artisan ui bootstrap --auth
</p>
<p>
6) Run Migration 
php artisan migrate 
</p>
<p>
7) Run Seeder - Permission Table Seeder
php artisan db:seed --class=PermissionTableSeeder
</p>
<p>
8) Run Seeder - Admin User Seeder
php artisan db:seed --class=CreateAdminUserSeeder 
</p>
<p> 
9) php artisan serve
</p>
<p>
10) login for Admin
User- admin@gmail.com
password - admin@123
</p>
