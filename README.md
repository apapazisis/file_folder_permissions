# Permissions for folders and files on the WebServer

#### Create a custom User
````
adduser my-user
````

#### Set the files, folders owner
````
sudo chown -R my-user:www-data /path/to/your/laravel/root/directory
````

### (Optional) ````sudo usermod -a -G www-data ubuntu````
The webserver owns all the files, and is also the group, and you will have some problems uploading files or working with files via FTP, because your FTP client will be logged in as you, not your webserver, so add your user to the webserver user group:

#### Set the files permissions
````
sudo find /path/to/your/laravel/root/directory -type f -exec chmod 644 {} \; 
````


#### Set the folder permissions
````
sudo find /path/to/your/laravel/root/directory -type d -exec chmod 755 {} \;
````

#### Give the webserver the rights to read and write to storage and cache
````
sudo chgrp -R www-data storage bootstrap/cache
sudo chmod -R ug+rwx storage bootstrap/cache
````
