PHP dinghy environment
===================

Start up
_______________

Build environment with 
```shell
docker-compose build
```
and run local server with
```shell
docker-compose up -d
```

Requirements:
* [dinghy](https://github.com/codekitchen/dinghy)
* local dns pointing preffered dns zone to docker ip (if you want to use zone [different from .docker](https://github.com/codekitchen/dinghy/issues/121), like .dev for example)

If you want to change php version just change image version in phpfpm/Dockerfile


Features
_______________

Xdebug
* xdebug configured to make snapshots to profiler_data folder if url loaded with ?XDEBUG_PROFILE

Mailcatcher
* v0.5.12 due to [utf-8 encoding bug](https://github.com/sj26/mailcatcher/issues/201)
* can be accessed at mail.dev

Cron
* to set up job look for sample jobs in job.sh

Do not forget to run 
```shell
docker-compose build
```
after any config changes (new virtual host, nginx settings, cron, etc)
