# laravel-8-authentication-useing-jetstream

# Hello Developers 
Recently the team of Laravel released the latest version which is Laravel 8, and as expected, there is some difference between the previous Laravel 7 and this present version.  
Previously, in Laravel 7 and Laravel 6 in other to do user authentication, we use an artisan command composer require laravel/ui while from Laravel 5.9 downwards uses php artisan make:auth

In Laravel 8, there is a major change in that area in the sense that many things are introduced and a lot of configurations have been done to get you started and not minding the boilerplate of your application, one of those changes is the introduction of Jetstream, Laravel Jetstream is a beautifully designed application scaffolding for Laravel. A major shift from the legacy authentication UI of Laravel.

Without saying much, let’s dive into the new features of Laravel 8.

# Step 1: Install a new Laravel app with Composer 

   Follow https://laravel.com/docs/8.x/installation First.
   You can create a new Laravel project by using Composer directly.for That Just Do -> 
    
    composer create-project laravel/laravel example-app

    cd example-app

    php artisan serve
    
# The Laravel Installer
   Or, you may install the Laravel Installer as a global Composer dependency:

    composer global require laravel/installer

    laravel new example-app

    cd example-app

    php artisan serve
    
 # Step 2: Database Setup
Edit the .env file by suing your IDE or text editor . Change the DB_DATABASE to the name of your databaseand if you have set a Username and password for your phpmyadmin, specify it, otherwise, leave the username as root and password blank.Before migrate, let’s catch one bug before it throws an error, go to App/Providers/AppServiceProvider.php
and add

    Schema::defaultstringLength(191);

to the boot function, also add

    use Illuminate\Support\Facades\Schema;

to the top.
# Step 3: Migration
Now Run the migration command.
     
     php artisan migrate
    
# Step 4: install Jetstream
Install jetstream via composer 
    
    composer require laravel/jetstream
 
# Step 5: Install livewire or inertia
We need to install one of the stacks, either a livewire or an inertia stack, in this tutorial, I will only be using livewire because it set up everything I need for the app

    php artisan jetstream:install livewire
  
There will be a suggest for run npm install && npm run dev to build all the javaScript files and CSS we need for our app. On successful build, Laravel will send a notification at the bottom left.

# There will be created some new migrate file 
# Step 5: Migrate the new table that is created
    
    php artisan migrate


Now time to run our app

    php artisan serve
 
http://127.0.0.1:8000/ will serve our app in our default browser

# Note 
Some time in your new larevel installation, you can get one issue with  Mix Manifest. Sometime there showing a error that it does not exist. Then Just delete files from 
/boostrap/cache directory . Then delete all folder from storage/framwork/ directory. And then create a new folder in storage/framwork 1. cache 2. sessions 3. views.Then 
run 
    
    npm install  
    npm run dev
    composer update 
    php artisan serve
Problem will be solved.
