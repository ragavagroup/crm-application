# OroCRM Enterprise Application

OroCRM Enterprise Application is a commercial version of OroCRM bundled with extended capabilities of
[OroPlatform Enterprise][1] and [OroCRM Enterprise][2]. This application allows to setup fully functional
and extandable CRM solution and can be used as a skeleton for custom CRM application.

## System Requirements

Before starting installation process, please prepare the infrastructure environment based on [system requirements][3]. 

## Installation

- Clone OroCRM Enterprise application repository:

```bash
    git clone -b x.y.z https://github.com/orocrm/crm-enterprise-application.git
```

where x.y.z is latest [release tag](https://github.com/orocrm/crm-enterprise-application/releases)

- Install [Composer][4] globally following the official Composer [installation documentation][5]
and install [fxpio/composer-asset-plugin][6] plugin for it:

```bash
    composer global require "fxp/composer-asset-plugin:~1.2"
```

- Install [Node.js][7].

- Install application dependencies running the following command from the application folder:

```bash
    composer install --prefer-dist --no-dev
```

**Note:** It is strongly recommended to use ElasticSearch as a search engine and RabbitMQ as a message queue broker
in production.

- Create the database with the name specified in the previous step (the default name is "oro_crm").

- Install the application and the admin user with the Installation Wizard by opening install.php in the browser or from CLI:

```bash  
php app/console oro:install --env prod
```

- Configure the Web Socket server process and the Message Queue consumer process in [Supervisor][8]:

```ini

[program:orocrm_enterprise_web_socket]
command=/path/to/app/console clank:server --env=prod
numprocs=1
autostart=true
startsecs=0
user=www-data
redirect_stderr=true

[program:orocrm_enterprise_message_consumer]
command=/path/to/app/console oro:message-queue:consume --env=prod
process_name=%(program_name)s_%(process_num)
numprocs=5
autostart=true
autorestart=true
startsecs=0
user=www-data
redirect_stderr=true
```

**Note:** the port used by Web Socket must be open in the firewall for outgoing/incoming connections.

- Configure crontab:

```bash
*/1 * * * * /path/to/app/console oro:cron --env prod
```

or scheduled tasks execution to run the command below every minute:

```bash
php /path/to/app/console oro:cron --env prod
```
 
**Note:** ``/path/to/app/console`` is a full path to `app/console` script in your application.

## Loading Demo Data using CLI

To load sample data you need to run console command

```bash
php app/console oro:migration:data:load --fixtures-type=demo --env=prod
```

[1]:    https://github.com/orocrm/platform-enterprise
[2]:    https://github.com/orocrm/crm-enterprise
[3]:    https://www.orocrm.com/documentation/index/current/system-requirements
[4]:    https://getcomposer.org/
[5]:    https://getcomposer.org/download/
[6]:    https://github.com/fxpio/composer-asset-plugin/blob/master/Resources/doc/index.md
[7]:    https://nodejs.org/en/download/package-manager/
[8]:    http://supervisord.org/
