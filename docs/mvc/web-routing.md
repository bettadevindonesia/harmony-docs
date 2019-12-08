---
layout: default
title: Web Routing
parent: MVC
nav_order: 3
---

# Web Routing
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Introduction

Web Routing on Harmony Modern Slim Boilerplate. Making a route or path to determine the URL will move and direct users to other pages and can be used to process data to be displayed or stored in a database or file.

In most website applications the term "Friendly-URL" is very necessary, so that users can easily remember the website address that was visited. Harmony also comes with the same thing.

## Route Structure
```php
<?php
// routes/web.php
$app->get('/', function($request, $response) {
	echo "Hello Harmony!";
});
```
**:sleepy: Explaination**

In the example above, `$app` is an instance of the application. The `get()` function defines that the request made is `GET`. And there is `/` which is inside the `get` function brackets which indicates that when the URL is in `root` the content to be displayed is `Hello Harmony!`

## Route & Controllers
Route file : `routes/web.php`
```php
<?php
$app->get('/', 'HomeController:index');
```

Controller file : `app/Controllers/HomeController.php`
```php
<?php

namespace App\Controllers;

use Slim\Views\Twig as View;

class HomeController extends Controller
{
    public function index($request, $response)
    {
        return "Hello Harmony!";
    }
}
```
**:sleepy: Explaination**

`HomeController` is the name of Controller you have inside `app/Controllers/`, make sure you have specified filename is the same with controller name.

## Naming Route (aliases)

Just like a popular framework :sleepy: with Harmony you can also give alias names to each rote you make with `setName()` function, so that you can easily access it via `view` (This will be discussed in the next session).

```php
<?php
// routes/web.php
$app->get('/', function($request, $response) {
	echo "Hello Harmony!";
})->setName('home');
```
or 
```php
<?php
// routes/web.php
$app->get('/', 'HomeController:index')->setName('home');
```

## Route with Parameters

```php
$app->get('/user/{name}', function($request, $response, $args) {
	echo "Hai " . $args['name'];
});
```
**:sleepy: Explaination**

Route parameters will be captured by the callback as an associative array.

## Route Optional Parameters

To make a section optional, simply wrap in square brackets:
```php
$app->get('/users[/{id}]', function ($request, $response, $args) {
    // responds to both `/users` and `/users/123`
    // but not to `/users/`
});
```

Multiple optional parameters are supported by nesting:
```php
$app->get('/news[/{year}[/{month}]]', function ($request, $response, $args) {
    // reponds to `/news`, `/news/2016` and `/news/2016/03`
});
``

For “Unlimited” optional parameters, you can do this (but its so...):
```php
$app->get('/news[/{params:.*}]', function ($request, $response, $args) {
    $params = explode('/', $args['params']);

    // $params is an array of all the optional segments
});
```
In this example, a URI of `/news/2016/03/20` would result in the `$params` array containing three elements: `['2016', '03', '20']`.

## Route with Regular expression matching

By default the placeholders are written inside `{}` and can accept any values. However, placeholders can also require the HTTP request URI to match a particular regular expression. If the current HTTP request URI does not match a placeholder regular expression, the route is not invoked. This is an example placeholder named `id` that requires one or more digits.
```php
<?php
$app->get('/users/{id:[0-9]+}', function ($request, $response, $args) {
    // Find user identified by $args['id']
});
```

## Route Group

To help organize routes into logical groups, the `Slim\App` also provides a `group()` method. Each group’s route pattern is prepended to the routes or groups contained within it, and any placeholder arguments in the group pattern are ultimately made available to the nested routes:
```php
$app->group('/users/{id:[0-9]+}', function (App $app) {
    $app->map(['GET', 'DELETE', 'PATCH', 'PUT'], '', function ($request, $response, $args) {
        // Find, delete, patch or replace user identified by $args['id']
    })->setName('user');
    $app->get('/reset-password', function ($request, $response, $args) {
        // Route for /users/{id:[0-9]+}/reset-password
        // Reset the password for user identified by $args['id']
    })->setName('user-password-reset');
});
```
The group pattern can be empty, enabling the logical grouping of routes that do not share a common pattern.
```php
$app->group('', function(App $app) {
    $app->get('/billing', function ($request, $response, $args) {
        // Route for /billing
    });
    $this->get('/invoice/{id:[0-9]+}', function ($request, $response, $args) {
        // Route for /invoice/{id:[0-9]+}
    });
})->add( new SharedMiddleware() );
```
Note inside the group closure, `$this` can be used instead of `$app`. Slim binds the closure to the application instance for you, just like it is the case with route callback binds with container instance.

inside group closure, $this is bound to the instance of `Slim\App`
inside route closure, $this is bound to the instance of `Slim\Container`

**hidden**
{: .hidden}

[Directory Structure]({{ site.baseurl }}{% link docs/mvc/directory-structure.md %}){: .prev-page}
[Controllers]({{ site.baseurl }}{% link docs/mvc/controllers.md %}){: .next-page}

**hidden**
{: .hidden}