# Drupal 8 migration node terms

Module to migrate Drupal 8 node terms to Drupal 8
This module migrates article nodes.

Instructions:
-------------

## Install Drupal Console
If you don't have it yet, follow the installation instructions [here](https://docs.drupalconsole.com/en/getting/project.html)

## Enable custom module.

`$ drupal module:install drupal8_migration_node_terms`

## Setup migration.

Provide credentials to legacy Drupal 8 database, you will be prompted to specify these information:

 - Database type.
 - Database host.
 - database name.
 - Database user.
 - Database password.
 - Database prefix.
 - Database port.
 - Local file directory.

`$ drupal migrate:setup`

![alt text][setup]

[setup]: ./images/drupal-migrate-setup.png "Drupal Console migrate setup prompt"


## Execute migration.

You will be prompted to specify the Source site URL and the same information as above in the Setup command.

`$ drupal migrate:execute migration_term_tags migration_articles`

![alt text][execute]

[execute]: ./images/drupal-migrate-execute.png "Drupal Console migrate execute prompt"

You will see confirmation messages like:

![alt text][result]

[result]: ./images/drupal-migrate-execute-result.png "Drupal Console migrate execute prompt"
