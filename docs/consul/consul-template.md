# Consul template usage

Consul template is an application that allow you to update your configuration in real-time. 

That's opensource project so you can find sources if you need via that [link](https://github.com/hashicorp/consul-template)

## Install consul-template

To install consul-template you need to download bundle with one executable file `consul-template`


You can find latest version that you need on [release notes](https://releases.hashicorp.com/consul-template/) page

For example we will use `consul-template_0.19.5`

```shell
$ wget https://releases.hashicorp.com/consul-template/0.19.5/consul-template_0.19.5_linux_amd64.tgz  -P /tmp
$ tar -zxvf /tmp/consul-template_0.19.5_linux_amd64.tgz -C /usr/local/bin
$ rm -fr /tmp/consul-template_0.19.5_linux_amd64.tgz 
```

After installation you can use `consul-template` command from anywhere

Let's verify if commands works:

```shell
$ consul-template --version
consul-template v0.19.5 (57b6c71)
```

## Create configuration file based on consul data

First of all we need to create `*.tpl` file, that will contains information about where find content that we need

```tpl
$ cat consul-key-example.tpl 
{{ "consul/key/example" | key }}
```

Now we can easily start consul template. That command we use your template to pull configuration from consul and put it to file `out.conf` and that command will do it only once. 

```bash
$ consul-template -template "consul-key-example.tpl:out.conf" -once
```


