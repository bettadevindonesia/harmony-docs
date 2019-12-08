---
layout: default
title: Directory Structure
parent: MVC
nav_order: 2
---

# Directory Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Introduction

The default Harmony application structure is intended to provide a great starting point for both large and small applications. But you are free to organize your application however you like. Harmony imposes almost no restrictions on where any given class is located - as long as Composer can autoload the class.

```bash
.
├── app
   ├── Controllers
   ├── Database
   ├── Middleware
   ├── Support
   ├── Libraries
   ├── Models
├── bootstrap
├── config
   ├── app.container.php
   ├── app.middleware.php
├── public
├── resources
   ├── assets
   ├── views
├── routes
   ├── web.php
├── artisan
├── bin
├── composer.json
├── composer.lock
├── gulpfile.js
├── package.json
├── README.md
└── vendor
```

## The Root Directory

### The App Directory
The `app` directory contains the core code of your application. We'll explore this directory in more detail soon; however, almost all of the classes in your application will be in this directory.

### The Bootstrap Directory
The `bootstrap` directory contains the `app.php` file which bootstraps the framework. This directory also houses a of all core a boilerplate included.

### The Config Directory
The `config` directory contains the `app.container.php` file which bootstraps all the container (Dependency Injection) and `app.middleware.php` file which bootstraps all the middleware of the framework. all of files filled by artisan command.

### The Config Directory
The `public` directory contains the `index.php` file, which is the entry point for all requests entering your application and configures autoloading. This directory also houses your assets such as images, JavaScript, and CSS.

### The Resources Directory
The `resources` directory contains your views as well as your raw, un-compiled assets such as LESS, SASS, or JavaScript. This directory also houses all of your language files.

### The Routes Directory
The `routes` directory contains all of the route definitions for your application. By default, route files are included with Harmony: `web.php` or create and specify with your own.

## The App Directory

### The Controllers Directory
The `Controllers` directory contains your controllers and form requests. Almost all of the logic to handle requests entering your application will be placed in this directory.

### The Database Directory
The `Database` directory contains your database migrations and seeds.

### The Middleware Directory
The `Middleware` directory contains your all your middleware generate by `artisan` command. Also include core middleware for the application.

### The Support Directory
The `Support` directory contains your all the core artisan command and also can add more with you own. In `Support` directory contains Auth Scaffolding and authentication logic, core of email customization, and more.

### The Libraries Directory
The `Libraries` directory is optional and up to you, the default harmony created project come with this directory to allow you create own libraries for application.

### The Models Directory
The `Models` directory, like other framework harmony created `Models` directory after you add Auth Scaffolding using artisan command.

**hidden**
{: .hidden}

[See MVC - Introduction]({{ site.baseurl }}{% link docs/mvc/introduction.md %}){: .prev-page}
[Web Routing]({{ site.baseurl }}{% link docs/mvc/web-routing.md %}){: .next-page}

**hidden**
{: .hidden}