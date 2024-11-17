# Learn the PHP Framework for Web Artisans

##  01. Introduction

**Welcome to the Laravel Bootcamp !**

In this guide we will walk through building a modern Laravel
application from scratch. To explore the framework, we'll build
a micro-blogging platform called `Chirper`.

###  Choose your own adventure: Blade, Livewire, or JavaScript

Laravel is incredibly flexible, allowing you to build your
front-end with a wide variety of technologies to suit your needs.

For this tutorial, we have prepared a few choices for you.

### Blade

`Blade` is the simple, yet powerful templating engine that is
included with Laravel. Your HTML will be rendered server-side,
making it a breeze to include dynamic content from your database.

We'll also be using Tailwind CSS to make it look great!

If you're not sure where to start, we think Blade is the most straight-forward. You can always come back and build Chirper again using Livewire or JavaScript.

```php
# welcome.blade.php
Greetings {{ $friend }}, let's build Chirper with Blade!
```

[Build Chirper with Blade](<https://bootcamp.laravel.com/blade/installation>)

### Livewire

`Livewire` is a powerful way of building dynamic, reactive,
front-end UIs using just PHP. Honestly, you won't believe it's not
JavaScript. If you're a Laravel developer, you'll feel right at home.

```php
# Class

#counter.blade.php
use Livewire\Volt\Component;

new class extends Component
{
    public int $count = 0;

    public function increment(): void
    {
        $this->count++;
    }
}; ?>

<div>
    <h1>{{ $count }}</h1>
    <button wire:click="increment">+</button>
</div>
```

```php
# Functional

#counter.blade.php
<?php
 
use function Livewire\Volt\{state};
 
state(['count' => 0]);
 
$increment = fn () => $this->count++;
 
?>
 
<div>
    <h1>{{ $count }}</h1>
    <button wire:click="increment">+</button>
</div>
```

[Build Chirper with Livewire](https://bootcamp.laravel.com/livewire/installation)

### JavaScript & Inertia

If you'd like to use `JavaScript`, we will be providing code samples
for both `Vue` and `React`. We'll also be using `Inertia` to connect
it all up and `Tailwind CSS` to make it look great!

If you're not sure which to select, we're big fans of `Vue` since it
is beginner-friendly and extremely powerful. After you've finished
the Bootcamp, you can always try it again with the other stack.

Go ahead and choose your stack:

```vue
# Welcome.vue

<Welcome>
    Hey {{ friend }}, let's build Chirper with Vue!
</Welcome>
```

```js
# Welcome.jsx
<Welcome>
    Nice to see you {friend}, let's build Chirper with React!
</Welcome>
```

At any point you may view the code for either framework to see what
life is like on the other side, just be sure not to mix the code in
your project.

[Build Chirper with JavaScript and Inertia](https://bootcamp.laravel.com/inertia/installation)
