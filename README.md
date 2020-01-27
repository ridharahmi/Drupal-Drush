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
### drupal with drupal

Install drupal 
```
  drush dl drupal-8 --select
```