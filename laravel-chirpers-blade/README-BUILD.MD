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
