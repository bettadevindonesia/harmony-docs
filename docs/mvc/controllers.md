---
layout: default
title: Controllers
parent: MVC
nav_order: 4
---

# Controllers
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Introduction
Instead of defining all of your request handling logic as Closures in route files, you may wish to organize this behavior using Controller classes. Controllers can group related request handling logic into a single class. Controllers are stored in the `app/Controllers` directory.

## Basic Controllers

### Defining Controllers
Below is an example of a basic controller class. Note that the controller extends the base controller class included with Harmony:
```php
<?php

namespace App\Controllers;

use Slim\Views\Twig as View;

class HomeController extends Controller
{
    public function index($request, $response)
    {
        return $this->view->render($response, 'index.twig');
    }
}
```

You can define a route to this controller action like so:

```php
<?php
$app->get('/', 'HomeController:index');
```

You may generate an controller by using make:controller Artisan command:

```bash
$ php artisan make:controller HomeController
```

**hidden**
{: .hidden}

[Web Routing]({{ site.baseurl }}{% link docs/mvc/web-routing.md %}){: .prev-page}
[Middleware]({{ site.baseurl }}{% link docs/mvc/middleware.md %}){: .next-page}

**hidden**
{: .hidden}