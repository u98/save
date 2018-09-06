You can use phpbrew on Cloud9. I found that the standard installation process works fine, just run the commands below.

We first install the libmcrypt-dev package to avoid running into dependency issues during build:
```sh
$ sudo apt-get update
$ sudo apt-get install libcurl4-openssl-dev
$ sudo apt-get install libmcrypt-dev

```
Next, we download phpbrew and move it to /usr/local/bin:
```sh
$ curl -L -O https://github.com/phpbrew/phpbrew/raw/master/phpbrew
$ chmod +x phpbrew
$ sudo mv phpbrew /usr/local/bin/
$ phpbrew init
# add this to your ~/.bashrc:
$ [[ -e ~/.phpbrew/bashrc ]] && source ~/.phpbrew/bashrc
$ phpbrew lookup-prefix ubuntu
```
Once set up, we install and load PHP 7:
```sh
$ phpbrew install 7.0 +default
$ phpbrew switch php-7.0.1
$ phpbrew use php-7.0.1
$ php -v
PHP 7.0.1 (cli) (built: Dec 29 2015 22:04:43) ( NTS )
Copyright (c) 1997-2015 The PHP Group
Zend Engine v3.0.0, Copyright (c) 1998-2015 Zend Technologies
```