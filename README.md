<!--
#                                 __                 __
#    __  ______  ____ ___  ____ _/ /____  ____  ____/ /
#   / / / / __ \/ __ `__ \/ __ `/ __/ _ \/ __ \/ __  /
#  / /_/ / /_/ / / / / / / /_/ / /_/  __/ /_/ / /_/ /
#  \__, /\____/_/ /_/ /_/\__,_/\__/\___/\____/\__,_/
# /____                     matthewdavis.io, holla!
#
#-->

[![Clickity click](https://img.shields.io/badge/k8s%20by%20example%20yo-limit%20time-ff69b4.svg?style=flat-square)](https://k8.matthewdavis.io)
[![Twitter Follow](https://img.shields.io/twitter/follow/yomateod.svg?label=Follow&style=flat-square)](https://twitter.com/yomateod) [![Skype Contact](https://img.shields.io/badge/skype%20id-appsoa-blue.svg?style=flat-square)](skype:appsoa?chat)

# JIRA on Kubernetes backed by PersistentVolumeClaim

> k8 by example -- straight to the point, simple execution.

Like to helm? Check out https://github.com/mateothegreat/helm-chart-atlassian-jira

## Usage

```sh
$ make help

```

## Install

```sh
$ make install
mysql -h mysql -uroot -pmysql -e "CREATE DATABASE IF NOT EXISTS \`jira\`"
mysql -h mysql -uroot -pmysql -e "GRANT ALL PRIVILEGES ON \`jira\`.* TO 'jira'@'10.%' IDENTIFIED BY 'jira'"

[ DEPLOYING manifests/deployment.yaml ]: deployment "atlassian-jira" created
[ DEPLOYING manifests/persistentvolumeclaim.yaml ]: persistentvolumeclaim "atlassian-jira-persistent-storage" created
[ DEPLOYING manifests/service.yaml ]: service "atlassian-jira" created

```

## Logs

```sh
$ make logs
...
2018-02-09 18:10:04 1 [Note] InnoDB: 5.6.39 started; log sequence number 1625997
2018-02-09 18:10:04 1 [Note] Server hostname (bind-address): '*'; port: 3306
2018-02-09 18:10:04 1 [Note] IPv6 is available.
2018-02-09 18:10:04 1 [Note]   - '::' resolves to '::';
2018-02-09 18:10:04 1 [Note] Server socket created on IP: '::'.
2018-02-09 18:10:04 1 [Warning] 'proxies_priv' entry '@ root@mysql-5966fc6745-6mst8' ignored in --skip-name-resolve mode.
2018-02-09 18:10:04 1 [Note] Event Scheduler: Loaded 0 events
2018-02-09 18:10:04 1 [Note] mysqld: ready for connections.
...
```


## Delete

```sh
$ make delete
```
