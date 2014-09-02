Solr plugin for Dokku
------------------------------

Project: https://github.com/progrium/dokku

Installation
------------
```
cd /var/lib/dokku/plugins
git clone https://github.com/MichaelSp/dokku-solr-plugin solr
dokku plugins-install
```

This plugin also requires the dokku-link plugin to be installed:
https://github.com/rlaneve/dokku-link

It uses the excellent solr docker image by makuk66
https://github.com/makuk66/docker-solr

Commands
--------
```
$ dokku help
     solr:create <app>            Create a Solr container
     solr:delete <app>            Delete specified Solr container
     solr:info <app>              Display container informations
     solr:link <app> <container>  Link an app to a Solr container
     solr:logs <app>              Display last logs from Solr container
```

Simple usage
------------

Create a new Container:
```
$ dokku solr:create foo            # Server side
$ ssh dokku@server solr:create foo # Client side

-----> Solr container created: solr/foo

       Host: 172.16.0.104
       Private ports: 9200, 9300
```

Advanced usage
--------------

Deleting containers:
```
dokku solr:delete foo
```

Linking an app to a specific container:
```
dokku solr:link foo bar
```

Solr logs (per container):
```
dokku solr:logs foo
```

Solr information:
```
dokku solr:info foo
```
