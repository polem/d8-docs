---
layout: post
title:  "Installer Console"
date:   2015-01-30 12:10:09
categories: drupal console
---

[Console][drupal-console] permet d'ajouter des commandes, comme par exemple la génération de module, pour faciliter le développement avec Drupal.

* Télécharger console `curl -LSs http://drupalconsole.com/installer | php`
* Déplacer le fichier `mv console.phar /usr/local/bin/drupal`.
* `drupal generate:module` pour générer un module.
* `drupal router:debug` pour voir les routes.

Sources

* [Documentation de l’installation de console][drush-console]

[drush-install]: http://docs.drush.org/en/master/install/
[composer-install]: https://getcomposer.org/doc/00-intro.md#system-requirements
[drupal-console]: https://www.drupal.org/project/console