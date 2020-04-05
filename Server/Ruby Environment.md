# Ruby Environment

1. Install Apache
   * sudo apt-get update
   * sudo apt-get install apache2

2. Set ServerName
   * Get IP address first
   * ifconfig eth0 | grep inet | awk ‘{ print $2 }’
   * cd /etc
   * sudo vim hosts
   * Add IP and domain

3. Install Ruby
   * wget —no-check-certificate  [https://raw.githubusercontent.com/joshfng/railsready/master/railsready.sh](https://raw.githubusercontent.com/joshfng/railsready/master/railsready.sh)  && bash railsready.sh
   * rvm install ruby-2.2.2 (to get the latest ruby version)
   * rvm —default use ruby-2.2.2
   * gem update —system (to get the latest gem version)
   * sudo apt-get install ruby-railties-4.0
   * gem install rails (to install rails)
   * gem install nodejs (to install nodejs—apparently rails needs nodejs)
   * may need to move passenger from older version of ruby to newer version of ruby using

``` text
sudo mv /home/puzzler/.rvm/gems/ruby-2.1.5/gems/passenger-5.0.7 passenger_module /home/puzzler/.rvm/gems/ruby-2.2.2/gems/passenger-5.0.7
```

## rbenv

```bash
# list all available versions:
$ rbenv install -l

# install a Ruby version:
$ rbenv install 2.0.0-p247
```





What’s included

* Ruby 
* libs needed to run Rails (sqlite, mysql, etc)
* Bundler, Passenger, and Rails gems
* Git

4. Run passenger-install-apache2-module after done installing and follow the instructions there. This is for setting up Apache so that it can run Ruby
   `sudo a2enmod passenger`

5. Add this to Apache config
   `cd /etc/apache2/mods-available`
   `sudo vim passenger.load`

``` text
LoadModule passenger_module /home/puzzler/.rvm/gems/ruby-2.2.2/gems/passenger-5.0.7/buildout/apache2/mod_passenger.so
```

``` text
`sudo vim passenger.conf`
```

``` text
<IfModule mod_passenger.c>
  PassengerRoot /home/puzzler/.rvm/gems/ruby-2.2.2/gems/passenger-5.0.7
  PassengerDefaultRuby /home/puzzler/.rvm/gems/ruby-2.2.2/wrappers/ruby
</IfModule>
```

`sudo a2enmod rewrite`
`sudo service apache2 restart`

6. Create an app
   `cd /var/www/html`
   `rails new blog`

7. Set up virtual host
   `cd /etc/apache2/sites-available`
   `sudo vim 000-default`

``` text
<VirtualHost *:80>
ServerName rubystoragebox.cloudapp.net
DocumentRoot “/var/www/html/blog/public”
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
<Directory “/var/www/html/blog/public”>
AllowOverride all
Options -MultiViews
Order allow,deny
Allow from all
```

# Uncomment this if you’re on Apache >= 2.4:

``` text
#Require all granted
</Directory>
RailsEnv “development”
</VirtualHost>
```