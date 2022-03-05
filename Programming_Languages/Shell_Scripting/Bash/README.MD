# Bash Scripting

bash command hierarchy

Command type
- Alias
- Function
- Shell built-in
- Keyword
- File

e.g type ls

Command PATH



Setting Environment

```shell
$ export PATH=$PATH:.
$ test -d $HOME/bin || mkdir $HOME/bin

$ bash $HOME/bin/hello1.sh
$ chmod +x $HOME/bin/hello1.sh
```

Checking status code

```shell
$ command1 || command2
$ command1 && command2
```
to read 

```shell
$ hello1.sh
$ echo $?
```