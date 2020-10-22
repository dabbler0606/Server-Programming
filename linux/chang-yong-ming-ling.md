# 常用命令

## 命令是如何执行的

命令后通常跟有一个或多个选项，选项后可携带参数。所以大部分命令格式如下

```text
command -options arguments
```

除了单连字符 **-** 外，大部分命令也支持双连字符 **--。**一般来说，单 - 为缩写，双 - 为全拼。

大部分命令支持使用 **-h** 或 **--help** 来查看帮助信息。包括命令介绍，所支持的参数和用法。

如 ls 命令

```text
dabbler0606@dabbler:~$ ls --help
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..

...
```

所以，当我们忘记参数时，记得 --help。

> man 命令，Linux 下帮助指令，显示 Linux 手册内容，可提供更为详细的信息。

在帮助信息中，我们常常能看到命令使用格式，如上述 ls 的 **Usage**，其中方括号 **\[ \]** 代表可选参数，竖线 **｜** 代表互斥选项。 

## 文件系统

### ls

> ls 可能是最常用的命令。它可以列出文件目录内容。

列出当前目录

```text
dabbler0606@dabbler:~$ ls
code  dabbler.sql  project
```

列出指定目录

```text
dabbler0606@dabbler:~$ ls code/
test.py
```

下列为 **ls** 常用参数

| 选项 |  |  |
| :--- | :--- | :--- |
| -a | --all | 列出所有文件，包括 . 开头隐藏文件 |
| -l |  | 列出详细信息，包括权限、所有者/组、大小、修改日期、文件名等 |
| -i |  | 列出 inode 节点编号 |
| -d | --directory | 列出目录信息，而不是目录下文件 |
| -h | --human-readable | 以人类可读格式列出，主要是文件大小 |
| -F |  | 标示文件类型 |
| -S |  | 按大小排序 |
| -t |  | 按修改时间排序 |
| -r | --reverse | 逆序显示 |

按文件大小逆序，列出文件信息。

```text
dabbler0606@dabbler:~$ ls -lSrh
total 8.0K
-rw-r--r-- 1 dabbler0606 dabbler0606    0 Sep 13 23:22 dabbler.sql
drwxr-xr-x 2 dabbler0606 dabbler0606 4.0K Sep 13 23:22 project
drwxr-xr-x 2 dabbler0606 dabbler0606 4.0K Sep 13 23:22 code
```

### cd

> 改变当前 shell 的工作目录。

```text
dabbler0606@dabbler:~$ cd code/
dabbler0606@dabbler:~/code$ cd .
dabbler0606@dabbler:~/code$ cd ..
dabbler0606@dabbler:~$ 
```

**.** 和 **..** 是两个特殊文件，**.** 标示当前目录，**..** 表示上一层目录。

### touch

> 修改文件时间，也常常被用来创建文件。

### mkdir

> 创建目录。

### cp

> 拷贝文件或目录。

### mv

> 移动或重命名文件。

### rm

> 删除文件或目录。

### ln

> 给文件创建链接。

## 用户系统

### adduser

```text
adduser <username>
```

### passwd

```text
passwd <username>
```

## 权限

### chmod

> 修改文件权限。

### chown

> 更改文件所有者

### chgrp

> 更改文件所属群组

### su

> 切换用户身份

### sudo

> 以另一个身份执行命令

## 进程

有时我们会需要查看进程信息，终止异常进程等。

### ps

> 查看进程信息

### top

> 查看进程占用资源情况。包括内存、CPU、执行时间等。

### kill

> 发送信号给某个进程。通常用来杀死进程。

## 输入输出

### xargs

> 将标准输入转为命令行参数

```text
$ echo "hello world" | xargs echo
```

