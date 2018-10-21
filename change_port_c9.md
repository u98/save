HOW TO RUN PHPMYADMIN AT THE SAME TIME AS YOUR NODEJS, RUBY ON RAILS OR OTHER APPLICATION
PHPMyAdmin uses Apache to run. So previously you couldn't have both it and NodeJS/Rails/Python running at the same time as they both wanted port 8080.

First Set Up PHPMyAdmin. Then do one of the following:

Run PHPMyAdmin on port 8080 and Application on 8081
This is the simplest way. All you need to do is specify 8081 as your app port instead of using the environment variable $PORT. Then you can access your app at https://projectname-username.c9users.io:8081/ ad PHPMyAdmin at http://<workspacename>-<username>.c9.io/phpmyadmin

Run PHPMyAdmin on port 8081
The other alternative is to run Apache on port 8081. You can do this with the following steps:

Edit `/etc/apache2/ports.conf` and change 8080 to 8081
Edit `/etc/apache2/sites-available/001-cloud9.conf` and change 8080 to 8081.
Restart apache with `sudo service apache2 restart` or by restarting your runner.
You'll then be able to access PHPMyAdmin at https://<workspacename>-<username>.c9users.io:8081/phpmyadmin
