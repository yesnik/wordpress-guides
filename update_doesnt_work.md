# Wordpress Update doesn't work

If Wordpress during update asks you to enter FTP credential on your VDS server do these steps to fix this error:

1. Add this constant to `wp-config.php`:

```php
define('FS_METHOD', 'direct');
```

2. Ensure that you have correct permissions on your project's files:

```
cd /var/www/
chown -R root:nginx mysite.com
chmod g+xw -R mysite.com
```
