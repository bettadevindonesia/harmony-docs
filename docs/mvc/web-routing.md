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

In the example above, `$app` is an instance of the application. The `get()` function defines that the request made is `GET`. And there is `/` which is inside the `get` function brackets which indicates that when the URL is in` root` the content to be displayed is `Hello Harmony!`

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

---

**Previous**
- [Directory Structure]({{ site.baseurl }}{% link docs/mvc/directory-structure.md %})

**Next**
- [Controllers]({{ site.baseurl }}{% link docs/mvc/controllers.md %})