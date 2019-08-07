# Bash tips

## Bash CLI

**Create monitoring loop in cli**
```shell
$ while true; do command; done;
```
Example:  
```shell
$ while true; do echo "Hello"; done;
Hello
Hello
Hello
Hello
...
```
**Create monitoring loop in cli with command execution timeout**
```shell
$ while true; do command; sleep 5; done;
```

Example:  
That command will print word **hello** each 5 seconds 
```shell
$ while true; do echo "Hello"; sleep 5; done;
Hello
Hello
...
```
