# laravel-init
Provides a set of commands and files I use in my laravel projects

```
composer update

sudo chmod -R 777 storage
sudo chmod -R 777 bootstrap

```
```
cd /etc/apache2/sites-avaiable
cp 000-default.conf projectname.conf

```
Or run ` curl https://raw.githubusercontent.com/beaverden/laravel-init/master/projectname.conf >>> projectname.conf `

Open projectname.conf and:

1. Change DocumentRoot to the respective path
2. Change DirectoryIndex to `index.php index.html` or whatever the directory index is
3. Add this code

```
<Directory path/to/projectname>
	Options Indexes FollowSymLinks
	AllowOverride All
	Require all granted
</Directory>
```

4. After everything is done run 

```
//Disables the default site listening on port 80
sudo a2dissite 000-default

//Enables our site (adds a link to projectname.conf into the /sites-enabled directory
sudo a2ensite projectname.conf

//That's what apache suggests after enabling a site
sudo service apache2 reload

//That's a restart
sudo service apache2 restart
```

sudo a2enmod rewrite
sudo service apache2 restart

```
