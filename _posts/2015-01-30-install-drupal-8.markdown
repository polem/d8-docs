---
layout: post
title:  "Installer drupal 8"
date:   2015-01-30 12:07:09
categories: drupal
---

L’installation de Drupal 8 avec `composer` n’est pas prête.
On installe donc avec drush.

`drush dl drupal-8 --select --all`

```
Choose one of the available releases for drupal:
 [0]   :  Cancel
 [1]   :  8.0.x-dev      -  2015-Jan-30  -  Development
 [2]   :  8.0.0-beta6    -  2015-Jan-28  -  Supported
 [3]   :  8.0.0-beta4    -  2014-Dec-17  -
 [4]   :  8.0.0-beta3    -  2014-Nov-12  -
 [5]   :  8.0.0-beta2    -  2014-Oct-15  -  Security
 [6]   :  8.0.0-beta1    -  2014-Oct-01  -
 [7]   :  8.0.0-alpha15  -  2014-Sep-19  -
 [8]   :  8.0.0-alpha14  -  2014-Aug-06  -
 [9]   :  8.1.x-dev      -  2014-Jul-29  -  Development
 [10]  :  8.0-alpha13    -  2014-Jul-02  -
 [11]  :  8.0-alpha12    -  2014-May-28  -
 [12]  :  8.0-alpha11    -  2014-Apr-23  -
 [13]  :  8.0-alpha10    -  2014-Mar-19  -
 [14]  :  8.0-alpha9     -  2014-Feb-19  -
 [15]  :  8.0-alpha8     -  2014-Jan-22  -
 [16]  :  8.0-alpha7     -  2013-Dec-18  -
 [17]  :  8.0-alpha6     -  2013-Nov-22  -
 [18]  :  8.0-alpha5     -  2013-Nov-19  -
 [19]  :  8.0-alpha4     -  2013-Oct-18  -
 [20]  :  8.0-alpha3     -  2013-Sep-04  -
 [21]  :  8.0-alpha2     -  2013-Jun-24  -
```

On choisit donc 2.

```
mv drupal-8.0.0-beta6 d8-project
cd d8-project
drush si --db-url="mysql://root@localhost/d8project" --locale=fr
```

```
You are about to create a /Users/paulemileminy/Sites/d8-project/sites/default/settings.php file and CREATE the 'd8project' database. Do you want to continue? (y/n): y
Starting Drupal installation. This takes a while. Consider using the --notify      [ok]
global option.
Installation complete.  User name: admin  User password: cMSuFHJpRz                [ok]
Félicitations, vous avez installé Drupal !
```

On vide le cache `drush cr`

On ajoute les droits pour tous a `sudo chmod -R a+w sites/default/file` (/!\ à ne pas faire en prod)

Au lancement de update.php

```
Drupal\Core\Database\DatabaseExceptionWrapper
SQLSTATE[22004]: Null value not allowed: 1138 Invalid use of NULL value: ALTER TABLE {users} CHANGE `uid` `uid` INT unsigned NOT NULL COMMENT &#039;The user ID.&#039;; Array ( )
Drupal\Core\Entity\Sql\SqlContentEntityStorageSchema-&gt;createSharedTableSchema() (ligne 1112)
/Users/paulemileminy/Sites/d8-project/core/lib/Drupal/Core/Entity/Sql/SqlContentEntityStorageSchema.php
```


