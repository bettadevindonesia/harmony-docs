---
layout: default
title: Models
parent: MVC
nav_order: 6
---

# Models
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Introduction
The model represents the data structure. Usually the model contains functions that help someone in managing the database such as entering data into database, update data and others.

![Model Illustrations](https://harmony-betta.github.io/img/models.png)

The model on Harmony is adapted from [Eloquent](https://laravel.com/docs/5.7/eloquent#eloquent-model-conventions) so it is very easy to model the data to interact with each other.

## How to create Model?
To create a model you can use artisan as a generator tool.

1. Open the terminal / Commad Prompt on your computer.
2. Navigate to your Harmony Framework project directory.
3. Type the command `php artisan make:model <name-model>`
4. Press Enter

```bash
$ php artisan make:model Users
File created (Users.php) in app/Models/Users.php
```

The `Users.php` file located in `app/Models` looks like this:

```php
# app/Models/Users.php
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class Users extends Model
{
    /**
     * Write your code
     */

}
```

everything you need to do the data interaction is already prepared.

**hidden**
{: .hidden}

[Middleware]({{ site.baseurl }}{% link docs/mvc/middleware.md %}){: .prev-page}
[View]({{ site.baseurl }}{% link docs/mvc/view.md %}){: .next-page}

**hidden**
{: .hidden}