# 文件类型

使用``ls -l FILENAME``即可看到文件类型。

如:

```bash
$ ls -l /bin/ls
-rwxr-xr-x 1 root root 110080 Dec  4 01:14 /bin/ls
|
文件类型
```

``ls -l``会粗略的列出文件类型。

Linux的文件类型有以下几种:

文件类型 | ``ls -l``显示
------- | ------------
普通文件 | ``-``
目录    |  ``d``
符号链接 | ``l``
字符设备 | ``c``
块设备  | ``b``
套接字  | ``s``
命名管道 | ``p``

但是并非所有的普通文件都可以``cat``，就跟不能用word去看ppt一样。

列出文件内容类型可以用``file``:

    file /bin/ls
