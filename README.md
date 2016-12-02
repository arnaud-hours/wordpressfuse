# wordpressfuse

### vhost configuration

```
<VirtualHost *:80> 
    ServerName wordpressfuse.local
    DocumentRoot "/web/www/wordpressfuse/public"
    SetEnv APPLICATION_ENV "development" 
    <Directory "/web/www/wordpressfuse/public"> 
        DirectoryIndex index.php 
        Options Indexes FollowSymLinks Includes ExecCGI 
        AllowOverride All 
        Order allow,deny 
        Allow from all
        Require all granted
    </Directory>
</VirtualHost>
```

### installation

- run composer install
- open your wordpress in your web browser in order to create the database
- copy public/wp-config-sample.php to public/wp-config.php
- setup your database parameters
- find the code below and replace it by [this one](https://api.wordpress.org/secret-key/1.1/salt/) or those in your public/wp/wp-config.php
```
define('AUTH_KEY',         'put your unique phrase here');
define('SECURE_AUTH_KEY',  'put your unique phrase here');
define('LOGGED_IN_KEY',    'put your unique phrase here');
define('NONCE_KEY',        'put your unique phrase here');
define('AUTH_SALT',        'put your unique phrase here');
define('SECURE_AUTH_SALT', 'put your unique phrase here');
define('LOGGED_IN_SALT',   'put your unique phrase here');
define('NONCE_SALT',       'put your unique phrase here');
```
- then you should be able to login here /wp/wp-login.php
