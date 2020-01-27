## Drush template for Drupal projects

Drush is an awesome shell interface for managing Drupal right from your cloud server command line. 
It is a very useful tool as it helps you perform various admin tasks using just one or two commands in the terminal,
replacing the need for many clicks and page refreshes in the UI.

This tutorial will go through some of the basic Drush commands and work with a standard Drupal installation to illustrate them.
It assumes then that you already have Drush installed on your cloud server and you have a working copy of Drupal on it. 
If you don't know how to do this, please refer to an earlier tutorial explaining all the steps.

### Install Drush

[Install Cygwin](https://www.cygwin.com)
#
Install necessary cygwin packages
```
  - ncurses packages
  - git package
  - bsdtar
  - curl package
```  
```
Add cygwin64\bin tp $path
```
install drush using [composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).
```
composer global require drush/drush:8.*
```
#
```
drush status
drush version
```
### Drupal with Drush

Install drupal 
```
  drush dl drupal-8 --select
```
Or
```
  drush dl --drupal-project-rename="project_name"
```
```
  cd project_name
```

```
  drush site-install --db-url=mysql://root:password@localhost/drush --site-name="Site Name" --site-mail="your_email" --account-name="your_login" --account-mail="your_email" --account-pass="your_password"
```

Clear Cache Drush
```
drush cache-rebuild
```
OR
```
drush cr
```

Let's install Views (I'm sure you know about this module). To do this, you first have to run the following command: 
```
  drush dl module_name
```
Exemple :
```
drush dl admin_toolbar coffee module_filter pathauto token ctools
```
Either one of these commands will download Module and place it in the appropriate modules folder. 
The second command is a short version of the first one. You'll notice that many commands have short versions for an even 
faster experience. For instance, the long version of the drush status command is drush core-status,
so don't be surprised if you see others using that one.

Now that Views is installed, enable it with the following command (the long version of which being pm-enable):
```
  drush en module_name -y
```
Exemple :
```
drush en admin_toolbar coffee module_filter pathauto token ctools -y
```

if you are looking to uninstall Views, you can use the following command:
```
 drush pm-uninstall module_name
```

Update core drupal
```
drush up drupal
```

Update Module
```
drush up module_name
```

Update Password Site
```
drush upwd admin --password=your_password
```

Update Default Theme 
 ```
drush config-set system.theme default bartik
drush config-set system.theme default classy
```