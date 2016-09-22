# laravel-init
Provides a set of commands and files I use in my laravel projects

```
composer update

sudo chmod -R 777 storage
sudo chmod -R 777 bootstrap

```
```
cd /etc/apache2/sites-avaiable
cp 000-default.conf [projectname].conf

```
Or run ` curl >>> [projectname].conf `

Open [projectname].conf and:
1. Change DocumentRoot to the respective path
2. Change DirectoryIndex to `index.php index.html` or whatever the directory index is
3. Add this code
```
<Directory path/to/[projectname]>
	Options Indexes FollowSymLinks
	AllowOverride All
	Require all granted
</Directory>
```
4. After everything is done run 
```
sudo a2dissite 000-default
sudo a2ensite [projectname].conf
sudo service apache2 reload
sudo service apache2 restart
```

sudo a2enmod rewrite
sudo service apache2 restart

```
