# Permissions for folders and files on the WebServer

#### Set the files, folders owner
````
sudo chown -R www-data:www-data /path/to/your/laravel/root/directory
````

### __
````
sudo usermod -a -G www-data ubuntu
````

#### Set the files permissions
````
sudo find /path/to/your/laravel/root/directory -type f -exec chmod 644 {} \; 
````


#### Set the folder permissions
`````
sudo find /path/to/your/laravel/root/directory -type d -exec chmod 755 {} \;
