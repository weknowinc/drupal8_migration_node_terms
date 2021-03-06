# Drupal 8 migration node terms

Module to migrate Drupal 8 node terms to Drupal 8
This module migrates article nodes.

# Documentation:

## Filter by content type

Currently this module migrates nodes from all content types in the legacy Drupal 8.
If you want to migrate only one content type you have to uncomment the 'node_type' option 
in migrate_plus.migration.migration_nodes.yml file and set the content type you want to migrate.

## Define tag field

By default this module will migrate the **field_tags** field, but if you want to migrate another
taxonomy field, you should change the machine-name in these files:

- src/Plugin/migrate/source/Node.php -> line 67.
- config/install/migrate_plus.migration.migration_nodes.yml -> line 31.


# Instructions:

## Install Drupal Console
If you don't have it yet, follow the installation instructions [here](https://docs.drupalconsole.com/en/getting/project.html)

## Enable custom module.

This command also will install the module dependencies:

  - migrate_plus
  - migrate_tools
  - migrate_drupal
  - drupal8_migration_terms(*)

(*) This module migrates taxonomy terms from Drupal 8, you can download it [here.](https://github.com/weknowinc/drupal8_migration_terms)

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

`$ drupal migrate:execute migration_term_tags migration_nodes`

![alt text][execute]

[execute]: ./images/drupal-migrate-execute.png "Drupal Console migrate execute prompt"

You will see confirmation messages like:

![alt text][result]

[result]: ./images/drupal-migrate-execute-result.png "Drupal Console migrate execute prompt"
