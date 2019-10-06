# GUKI - A simple PHP Docker development environment
A really simple docker setup with Nginx, PHP-FPM, MySQL and Redis

## Prerequisite
* Docker with Docker-Compose
* NodeJS - To generate SSL certificates we are using a Node package.
* A CLI Tool - preferably bash

## Installation
1. Clone the Repo
2. Using terminal navigate inside to the directory `guki`.
3. Type the following command `docker-compose up`.
4. Done!

## How to create a new project?
1. Create a directory inside `code` directory with your PROJECT_DIRECTORY_NAME. Please also create an `index.php` or `index.html` file inside it.
2. Copy `sample.conf` from `configs/vhosts` directory.
3. Replace all occurances of `sample` with the PROJECT_DIRECTORY_NAME you choose. (Not necessory, but for simplicity using the same folder name)
4. Install `Create SSL Certificate Plugin` for NPM using `npm i -g create-ssl-certificate`
5. On `terminal` goto `configs/certs` directory, then type `npx create-ssl-certificate --hostname PROJECT_DIRECTORY_NAME --domain YOUR_DOMAIN_EXTENSTION`
6. Please rename the generated files to PROJECT_DIRECTORY_NAME (This also you can customize)
7. Install generated `.cert` file to your machine (Mac and Linux uses different steps for the same, please google it)
8. Add your newly created local domain to your `etc/hosts` file. Now run `docker-compose up`.
9. Once everything done, goto https://PROJECT_DIRECTORY_NAME.YOUR_DOMAIN_EXTENSTION in Google Chrome.
10. Done!

## Support
If you are facing any issues, please feel free to reach me out in Skype (shine.sudarsanan) or Email (shine@richkenmedia.com)

I am planning to create a dedicated website for this, will keep you posted!
