# Sentinel 2 extended with ban/suspend features

This repo adds a couple of useful features to the [Sentinel 2](https://cartalyst.com/manual/sentinel/2.0) authorization and authentication package for [Laravel 5.2](https://laravel.com/docs/5.2). To see the full explanation, head over to [this](http://www.jm.kleger.com/add-suspend-and-ban-features-to-sentinel-2) article.

1. You can ban an abusive registered user to prevent her from signing in to your application
2. You can suspend a registered user for a given time period

Wanna give it a shot? Follow the (very straightforward) installation process and get up and running with a fully functional access control service. 

## Installation

Make sure you have a running web server on your computer (*xampp* for example). Open your favorite CLI and move to the folder that will hold the project (typically C:\xampp\htdocs for xampp users). Then type the following commands: 

First clone the repo
```
git clone https://github.com/jeanquark/sentinelBanSuspend.git
```

Install all dependencies
```
composer install
```

Generate application key 
```
php artisan key:generate
```

Create a database that will hold sentinel tables. You can do so with phpmyadmin.
Open the .env.example file, edit it to match your database name, username and password and save it as .env file. Then build tables with command

```
php artisan migrate
```

Now fill the tables
```
php artisan db:seed
```

Nice. You should be good to go. Open your web browser and go to the login page of the application project (if you followed the above-mentioned directives with xampp, path is: http://localhost/sentinel/public/login). Enter provided admin credentials and start managing users from the admin portal.
Quick note:
To make use of the OAuth service, you need to register your app to the service provider. I explain how to do it as well as all the steps needed to go from Sentinel to Sentinel OAuth in this [blog post](http://www.jmkleger.com/post/add-oauth-to-sentinel-2).

## Features

1. Static blog homepage (frontend theme is [bootstrap blog](http://startbootstrap.com/template-overviews/blog-home/))
2. Register page
1. Sign in page
2. Admin area with user management (backend theme is [SB Admin](http://startbootstrap.com/template-overviews/sb-admin/))

## Screenshots

Admin area:
![admin](https://github.com/jeanquark/sentinelBanSuspend/raw/master/public/admin.png "Admin area")

Suspended user signin tryout:
![suspended](https://github.com/jeanquark/sentinelBanSuspend/raw/master/public/suspended.png "Suspended user")

Banned user signin tryout:
![banned](https://github.com/jeanquark/sentinelBanSuspend/raw/master/public/banned.png "Banned user")


### License
Please refer to [Sentinel 2 The BSD 3-Clause License](https://github.com/cartalyst/sentinel/blob/2.0/LICENSE).