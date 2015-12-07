# 通配符

通配符的作用是用于模糊查询时通配文件名中某些不确定的字符。

Bash中的通配符只有3个: ``*``, ``?``, ``[]``

通配符|作用  
-----|-----------------
``?``|匹配任意单个字符  
``*``|匹配任意长度任意字符
``[]``|匹配一个单字符范围,如[a-z],[0-9]

``[]``的特殊用例:

```
[]：匹配范围
[^]：排除匹配范围
[:alnum:]：所有字母和数字
[:alpha:]：所有字母
[:digit:]：所有数字
[:lower:]：所有小写字母
[:upper:]：所有大写字母
[:blank:]：空白字符和TAB制表符
[:space:]：包括空白字符、TAB制表符(\t)、换页(\f)
[:cntrl:]：所有控制字符
[:graph:]：可打印并可看到的字符。空格是可打印的，但是不是可看到的。  
[:print:]：所有可打印字符
[:punct:]：所有标点符号，非字母、数字、控制字符和space字符。  
[:xdigit:]：十六进制数的字符。
```

通配符范例:

```
*.txt               # 匹配全部后缀为.txt的文件
file?.log           # 匹配file1.log, file2.log, ...
[a-z]*.log          # 匹配a-z开头的.log文件
[^a-z]*.log         # 上面的反向匹配
```

**NOTE**: 转义字符(``\``)或引号(``'``, ``"``)都会使通配符失效。

如: ``\*``, ``"*"``, ``'*'``都表示``*``本身，不通配任何文件。

## 通配符与正则表达式的区别

1. 用途不同

        通配符用于通配文件名，正则表达式用于匹配文本内容

2. 使用地点不同

        通配符通常只能用于shell，被shell自解释。
        正则表达式需要被正则引擎解析，需要用于支持正则表达式的代码或命令中。

3. 元字符不同

        通配符只有三个元字符，正则表达式根据正则引擎不同会多种多样。
        并且相同元字符表示的含义也可能不同。如通配符中*表示匹配任意字符，正则中*表示前面的字符重复0或任意次。