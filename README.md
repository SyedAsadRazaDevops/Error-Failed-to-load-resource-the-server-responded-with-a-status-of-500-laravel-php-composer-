# Error-Failed-to-load-resource-the-server-responded-with-a-status-of-500-laravel-php-composer-
Getting a 500 Internal Server Error 

**solution #1:**

Install the required packages by running the composer command from the the root of the project:
```
sudo composer install
```
*UPDATE*:
You should not run this command on a production server, but some issues with composer can be resolved with this on local envs.
*EDIT:*

take a look at https://getcomposer.org/doc/faqs/how-to-install-untrusted-packages-safely.md 
to see why running composer install as root is not a good idea.
If you need to run it as root, provide the following flags
to block third-party code from executing durin the install --no-plugins --no-scripts

**solution #2:**

For solving the problem i ran the following commands through terminal.
```
sudo chmod -R 755 MYlaravel_project
```
and then type below to allow laravel to write file to storage folder
```
chown -R www-data:www-data /path/to/your/root/dir/
```
```
chmod -R 775 /bootstrap
chmod -R 775 /storage
```
After that clear your caches using the below commands:

//---Delete Configuration Cahce
```
php artisan config:cache
```
//---Clear Application Cache
```
php artisan cache:clear
```
