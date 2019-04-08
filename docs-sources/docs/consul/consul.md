# Consul usage

Consul it's application that can store\update your application configuration.

## Create environment file for consul
In case when you can have more than one consul cluster and you need to help connection to them, it's better to create different `*.env` file to them.

`consul` cli tool required to set ENV variables list: 

* **CONSUL_HTTP_SSL** - is used to enable or disable ssl verification
* **CONSUL_HTTP_ADDR** - https address to your consul cluster
* **CONSUL_HTTP_TOKEN** - access token to your consul

`*.env` file example:
```shell
export CONSUL_HTTP_SSL=false

export CONSUL_HTTP_ADDR='http://you-server-address'

export CONSUL_HTTP_TOKEN='you-access-token'
```

## Export consul kv to json

To work with consul kv storage we have command `consul kv`. 

Before start you should be sure that you have setted correct values to you env variables

Consul export example:
```shell
$ consul kv export your/consul/key >> export.json
```

## Import consul kv from json

When you already export kv from consul and ready to import it to another place you have `consul kv import` command.

Consul import examle:
```shell
$ consul kv import @import.json
```
