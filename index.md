---
layout: default
title: Home
nav_order: 1
description: "Official Documentation for Harmony Modern Slim Boilerplate by Betta Dev Indonesia"
permalink: /
---

# Harmony Modern Slim Boilerplate
{: .fs-9 }
Build websites easily using Harmony Modern Slim Boilerplate. Equipped with artisan, eloquent, database migration and database seeders, also tinker.
{: .fs-6 .fw-300 }

<img src="{{ '/assets/images/harmony-banner.png' | absolute_url }}" alt="Harmony Betta" width="100%">

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](https://github.com/harmony-betta/harmony){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started

### Requirements

- PHP7.1 or higher
- Composer
- NodeJs
- GulpJs (optional, but recomended)

### Quick start: install harmony using `composer create-project`

```bash
$ composer create-project --prefer-dist harmony-betta/harmony project-name -vvv
```
<small>You must have [Composer]('https://getcomposer.org/') installed on your computer</small>

### Global installation: Use Harmony Installer

when you install Harmony globally then you no longer need to repeat commands `create-project` composer.
```bash
$ composer global require "harmony-betta/installer"
```
<small>Make sure you have `/home/user/.composer` directory. Then check your `$PATH` to `/home/user/.composer/vendor/bin`</small>

if the installation is complete please type the command in your Terminal / Command Prompt as follows:
```bash
$ harmony --version
```

Now you can install using Harmony Installer
```bash
$ harmony new harmony-project # or your project name
```
<small>define the name of your project at the end of the command like `harmony new your-project-name`</small>

### Configure `.env`

- [See configuration options]({{ site.baseurl }}{% link docs/configuration.md %})

---

## About the project

This project created by :shit: developer. The reason he made this project was that he was stupid and could not develop to keep up with technological trends too quickly. Back again, he was indeed a fool. And he makes English-language documentation with [Google Translate](https://translate.google.com/) and one more thing you have to know; he made this documentation on each page with the source from [Slim 3](https://www.slimframework.com/docs/v3/) and [Laravel](https://laravel.com/docs/5.7/) Documentation.

Harmony Modern Slim Boilerplate is &copy; 2017-{{ "now" | date: "%Y" }} by [Imam Ali Mustofa](https://twitter.com/ddarkterminal).

### License

Harmony Slim Boilerplate is distributed by an [AGPL-3.0 license](https://github.com/harmony-betta/harmony/blob/master/LICENSE).

### Contributing

When contributing to this repository, please first discuss the change you wish to make via issue, email [Betta Dev Indonesia](mailto:bettadevindonesia@gmail.com), or any other method with the owners of this repository before making a change.
