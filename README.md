# INSTALL and Configure xDebug


 - Install `sudo apt-get install php-xdebug` 
 - Create a vh debug.loc using [vh](https://github.com/iloveyii/xdebug) 
 - Verify php -m

 - Change port to 9000 in /etc/php/7.4/apache2/conf.d/20-xdebug.ini, restart apache2
 - In PHPStorm Click Run > Edit configurations
 - Add web app, with server created in vh above
 - Click validate to validate config
 - contents of /etc/php/7.4/apache2/conf.d/20-xdebug.ini:
     ```
    zend_extension=xdebug.so
    xdebug.show_error_trace = 1
    zend_extension=/usr/lib/php/20190902/xdebug.so
    xdebug.remote_autostart = 1
    xdebug.remote_enable = 1
    xdebug.remote_handler = dbgp
    xdebug.remote_host = 127.0.0.1
    xdebug.remote_log = /tmp/xdebug_remote.log
    xdebug.remote_mode = req
    xdebug.remote_port = 9000
```