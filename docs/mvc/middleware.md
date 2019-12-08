---
layout: default
title: Middleware
parent: MVC
nav_order: 5
---

# Middleware
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

You can run code before and after your Slim application to manipulate the Request and Response objects as you see fit. This is called _middleware_. Why would you want to do this? Perhaps you want to protect your app from cross-site request forgery. Maybe you want to authenticate requests before your app runs. Middleware is perfect for these scenarios.

## What is middleware?

Technically speaking, a middleware is a _callable_ that accepts three arguments:

1. `\Psr\Http\Message\ServerRequestInterface` - The PSR7 request object
2. `\Psr\Http\Message\ResponseInterface` - The PSR7 response object
3. `callable` - The next middleware callable

It can do whatever is appropriate with these objects. The only hard requirement is that a middleware **MUST** return an instance of `\Psr\Http\Message\ResponseInterface`. Each middleware **SHOULD** invoke the next middleware and pass it Request and Response objects as arguments.

## How does middleware work?

Different frameworks use middleware differently. Slim adds middleware as concentric layers surrounding your core application. Each new middleware layer surrounds any existing middleware layers. The concentric structure expands outwardly as additional middleware layers are added.

The last middleware layer added is the first to be executed.

When you run the Slim application, the Request and Response objects traverse the middleware structure from the outside in. They first enter the outer-most middleware, then the next outer-most middleware, (and so on), until they ultimately arrive at the Slim application itself. After the Slim application dispatches the appropriate route, the resultant Response object exits the Slim application and traverses the middleware structure from the inside out. Ultimately, a final Response object exits the outer-most middleware, is serialized into a raw HTTP response, and is returned to the HTTP client. Here’s a diagram that illustrates the middleware process flow:

![Image From Slim 3 Documentation](https://www.slimframework.com/docs/v3/images/middleware.png){: .w-50}

## How do I write middleware?

Middleware is a callable that accepts three arguments: a Request object, a Response object, and the next middleware. Each middleware MUST return an instance of `\Psr\Http\Message\ResponseInterface`.

```bash
$ php artisan make:middleware SomeMiddleware
File created (SomeMiddleware.php) in app/Middleware/SomeMiddleware.php
```

### Closure Middleware Example

This example middleware is a Closure.

```php
<?php

namespace App\Middleware;
use App\Middleware\System\Middleware;

class SomeMiddleware extends Middleware
{
    public function __invoke($request, $response, $next)
    {
        /**
         * Write your code
         */

        $response = $next($request, $response);
        return $response;
    }
}
```

### How do I add middleware?

You may add middleware to a Harmony, to an individual Harmony route or to a route group. All scenarios accept the same middleware and implement the same middleware interface.

When you create middleware with Artisan Command then middleware will be registered in `app/config/app.middleware.php`

```php
<?php
// app/config/app.middleware.php
$app->add(new \App\Middleware\SomeMiddleware($container));
```

if you need further explanation, you can read the documentation in [Slim Framework - Middleware](https://www.slimframework.com/docs/concepts/middleware.html)

**hidden**
{: .hidden}

[Controllers]({{ site.baseurl }}{% link docs/mvc/controllers.md %}){: .prev-page}
[Models]({{ site.baseurl }}{% link docs/mvc/models.md %}){: .next-page}

**hidden**
{: .hidden}