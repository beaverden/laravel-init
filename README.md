# laravel-init
Provides a set of commands and files I use in my laravel projects

1. Make sure everything is up to date
```
composer update

//If there are any node modules
npm install
//OR
npm update
```

2. Add permissions to the directories

```
//Might also need to add permissions to upper directories (755)
sudo chmod -R 777 storage
sudo chmod -R 777 bootstrap
```

3. Setup apache2 server

```
//Make sure everything is up to date
sudo apt-get update
sudo apt-get upgrade

//Might also need to install php
sudo apt-get install php7.0

//Go to directory
cd /etc/apache2/sites-avaiable

//Make a exact copy of the default site provided
cp 000-default.conf projectname.conf

//OR run this will copy the config from this repo
curl https://raw.githubusercontent.com/beaverden/laravel-init/master/projectname.conf >>> projectname.conf


//Disables the default site listening on port 80
sudo a2dissite 000-default

//Enables our site (adds a link to projectname.conf into the /sites-enabled directory
sudo a2ensite projectname.conf

//That's what apache suggests after enabling a site
sudo service apache2 reload

//That's a restart
sudo service apache2 restart
```
