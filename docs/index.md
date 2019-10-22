<center>![alt text](img/guki.png "Guki Logo")</center>
# GUKI - A simple PHP Docker development environment
A really simple docker setup with Nginx, PHP-FPM, MySQL and Redis

## Features
* Multiple PHP FPM versions (5.6, 7.2)
* PHP Package Manager Composer Installed as a docker container
* Light Weight
* No complex configurations

## Prerequisite
* Docker with Docker-Compose
* NodeJS - To generate SSL certificates we are using a Node package.
* A CLI Tool - preferably bash

!!! tip
    If you are a Mac user, you may please download and install Homebrew, this will make your life lot easier!

## Installation

1. Clone the Repo from [https://github.com/shineklbm/guki](https://github.com/shineklbm/guki)
2. Using terminal navigate to the directory guki.
3. Copy sample.env to .env and make any required changes.
4. Type the following command docker-compose up.
5. Done!

## How to create a new project?
* Create a directory inside code with YOUR_PROJECT_NAME. Now, create a file inside that directory with the following content.

``` php
<?php
    phpinfo();
?>
```
* Copy sample.conf from configs/vhosts directory and paste it .
* Replace all occurances of sample with the PROJECT_NAME you choose. (Not necessory, but for simplicity using the same folder name)
* Install Create SSL Certificate Plugin for NPM using npm i -g create-ssl-certificate
* Using terminal goto configs/certs directory, then type
```
npx create-ssl-certificate --hostname PROJECT_NAME --domain YOUR_DOMAIN_EXTENSTION
```
* Please rename the generated files to PROJECT_NAME(This also you can customize)
* Install generated .cert file to your machine (Mac and Linux uses different steps for the same, please google it)
* Add your newly created local domain to your etc/hosts file. Now run docker-compose up.
* Once everything done, goto https://PROJECT_NAME.YOUR_DOMAIN_EXTENSTION in Google Chrome.
* Done!

## FAQ

* What is the default credentials for PHPMyAdmin? 
> You may please use root as the username and password. Please don't forget to use mysql as the host name.

* How can I login to a running docker container? 
> Please use the docker-compose exec YOUR_CONTAINER_NAME bash command like the one bellow.
```
docker-compose exec nginx bash
```

* How can I connect to mysql running in docker from host machine?
> Please use the following details to connect docker mysql from host machine.
```
Host Name : 127.0.0.1

Username : rkme

Password : Rkme#001

Port : 3307
```

## Support
If you are facing any issues, please feel free to reach me out in Skype (shine.sudarsanan) or [Email Me](mailto:shine@richkenmedia.com)