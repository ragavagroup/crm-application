Oro Platform Empty Application
==============================

An example of an empty application using the Oro Platform.

This repository contains application configuration settings and depends on Oro Platform. It can be used as a starting point to build applications using the oro Platform.

## Requirements

Oro Platform is a Symfony 2 based application with the following requirements:

* PHP 5.5.9 or above with command line interface
* PHP Extensions
    * GD
    * Mcrypt
    * JSON
    * ctype
    * Tokenizer
    * SimpleXML
    * PCRE
    * ICU
* MySQL 5.1 or above
* PostgreSQL 9.1 or above

## Installation instructions

### Clone repo

git clone git@github.com:ragavagroup/crm-application.git -b bap/application

### Using Composer

curl -s https://getcomposer.org/installer | php

Next

php -d memory_limit=-1 composer.phar install --prefer-dist --no-dev

create a new database and ran

php app/console oro:install --force --env dev --timeout=0


