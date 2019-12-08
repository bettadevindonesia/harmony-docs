---
layout: default
title: Configuration
nav_order: 2
---

# Configuration
{: .no_toc }
Harmony Docs has some specific configuration parameters that can be defined in your Harmony site's `.env` file.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


View this site's [.env](https://github.com/harmony-betta/harmony/tree/master/.env.example) file as an example.

## App Configuration

Set key and value pair to configure your app using environment variable

1. Application Setting
```bash
APP_NAME=Harmony # Application name
DISPLAY_ERROR=true # Display error in app
DEBUG=true # Debug mode for app
EDITOR=vscode # default Whoops error editor used
APP_HOST=http://localhost:8081 # Setting up your link for your app
```

2. Database Setting
```bash
DB_DRIVER=mysql # database drive
DB_HOST=127.0.0.1 # database host
DB_NAME=harmony # database name
DB_USER=root # database username
DB_PASS=root # database passowrd
```

3. Database Setting
```bash
DB_DRIVER=mysql # database drive
DB_HOST=127.0.0.1 # database host
DB_NAME=harmony # database name
DB_USER=root # database username
DB_PASS=root # database passowrd
```

4. Email Setting
```bash
EMAIL_HOST=smtp.mailtrap.io # email host
EMAIL_AUTH=true # email auth
EMAIL_PORT=465 # email port
EMAIL_SECURE=tls # email secure
EMAIL_USERNAME= # email username
EMAIL_PASSWORD= # email password
```

## Other Configuration

Or you can add more setting in `.env` file. 

### Google Analytics

```bash
# Google Analytics Tracking (optional)
# e.g, UA-1234567-89
ga_tracking: UA-5555555-55
```

and more...

**hidden**
{: .hidden}

[Home]({{ site.baseurl }}/){: .prev-page}
[MVC]({{ site.baseurl }}{% link docs/mvc/mvc.md %}){: .next-page}

**hidden**
{: .hidden}