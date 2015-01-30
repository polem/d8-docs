---
layout: post
title:  "Installer drush 7"
date:   2015-01-30 12:07:09
categories: drupal drush
---

Drush 7 est la version de drush qui fonctionne avec Drupal 8.

* Installer composer de manière globale `brew install composer`
* Ajouter composer au PATH `export PATH="$HOME/.composer/vendor/bin:$PATH"`.
* `composer global require drush/drush:dev-master`.

Sources
* [Documentation de l’installation de drush][drush-install]
* [Documentation de composer][composer-install]

[drush-install]: http://docs.drush.org/en/master/install/
[composer-install]: https://getcomposer.org/doc/00-intro.md#system-requirements
