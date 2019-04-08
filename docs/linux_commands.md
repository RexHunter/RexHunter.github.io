# Linux commands
## Grep
Structure
- Find row in directory files[^1]

The quick brown fox[^1] jumped over the lazy dog[^2].

[^1]: Foxes are red
[^2]: Dogs are usually not red


###Search in file
**To find rows in file that apply to expression:**
`$ grep 'exprassion' file_name`

Example:
```
$ cat example.txt

Hello, world!
hello
Goodby, my friend

```

```
$ grep Hello example.txt

Hello, world!
hello

```

[^1]**To find rows that apply to expression in hole directory:**
`grep -r 'exprassion' /path/do/directory`

Example:

```shell
$ ls -l

-rw-r--r-- 1 user user 6 Dec 25 18:28 hello1.txt
-rw-r--r-- 1 user user 5 Dec 25 18:28 hello2.txt
```
```shell
$ grep -r hello ./

./hello1.txt:HelloMyFriend
./hello1.txt:Hello My Friend
```

**To print only rows without filename need to use additional parameter `-h`**

```shell
$ grep -hr hello ./

Hello

```

**To find specific word in file user paramater `-w`**
```shell
$ cat example.txt

HelloMyFriend
Hello My Friend
```
```
$ grep -w hello example.txt

Hello My Friend

```

To print number of line where expression was found use parameter `-rn`

```shell
$ cat example.txt

empty string
Hello My Friend
```
```shell
$ grep -rn hello example.txt

2:Hello My Friend
```
