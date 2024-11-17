# READ ME BUILD  : LARAVEL CHIRPERS BLADE

## 1 Install

- Create a new Laravel project via Composer:

```bash
composer create-project laravel/laravel chirper
```

- After the project has been created, start Laravel's local development server using Laravel Artisan's serve command

```bash
cd chirper
 
php artisan serve

```

## Installing Laravel Breeze

- Open a new terminal in the project directory and install your chosen stack with the given commands:

```bash
composer require laravel/breeze --dev
 
php artisan breeze:install blade
```

- Breeze will install and configure your front-end dependencies for you, so we just need to start the Vite development server to automatically recompile our CSS and refresh the browser when we make changes to our Blade templates

```bash
npm run dev
```

- If you refresh your new Laravel application in the browser, you should now see a "Register" link at the top-right. Follow that to see the registration form provided by Laravel Breeze.

## Models, migrations, and controllers

- `Models` provide a powerful and enjoyable interface for you to interact with the tables in your database.
- `Migrations` allow you to easily create and modify the tables in your database. They ensure that the same database structure exists everywhere that your application runs.
- `Controllers` are responsible for processing requests made to your application and returning a response.

Almost every feature you build will involve all of these pieces working together in harmony, so the `artisan make:model` command can create them all for you at once.

- You can see all the available options by running the `php artisan make:model --help` command

- the command `php artisan make:model -mrc Chirp`  will create three files for you:
  - `app/Models/Chirp.php` - The Eloquent model.
  - `database/migrations/<timestamp>_create_chirps_table.php` - The database migration that will create your database table.
  - `app/Http/Controllers/ChirpController.php` - The HTTP controller that will take incoming requests and return responses.

## Routing

We will also need to create URLs for our controller.

To start with, we are going to enable two routes:

- The `index` route will display our form and a listing of Chirps.
- The `store` route will be used for saving new Chirps.

We are also going to place these routes behind two middleware:

- The `auth` middleware ensures that only logged-in users can access the route.
- The `verified` middleware will be used if you decide to enable email verification.

This will create the following routes:

| Verb |   URI   | Action |  Route Name  |
|:----:|:-------:|:------:|:------------:|
| GET  | /chirps | index  | chirps.index |
| POST | /chirps | store  | chirps.store |

NOTE:  You may view all of the routes for your application by running the `php artisan route:list` command.

- Let's test our route and controller by returning a test message from the index method of our new ChirpController class:

##  Blade

- Let's update the index method of our ChirpController class to render a Blade view: `app/Http/Controllers/ChirpController.php`

- then create our Blade view template with a form for creating new Chirps

`resources/views/chirps/index.blade.php`

```php
<x-app-layout>
    <div class="max-w-2xl mx-auto p-4 sm:p-6 lg:p-8">
        <form method="POST" action="{{ route('chirps.store') }}">
            @csrf
            <textarea
                name="message"
                placeholder="{{ __('What\'s on your mind?') }}"
                class="block w-full border-gray-300 focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 rounded-md shadow-sm"
            >{{ old('message') }}</textarea>
            <x-input-error :messages="$errors->get('message')" class="mt-2" />
            <x-primary-button class="mt-4">{{ __('Chirp') }}</x-primary-button>
        </form>
    </div>
</x-app-layout>
```
