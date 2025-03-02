<p align="center"><img src="https://raw.githubusercontent.com/odb/official-bash-logo/master/assets/Logos/Icons/PNG/512x512.png" width="200px"></p>
<h1 align="center">pure bash bible</h1> <p
align="center">bash奇巧淫技.</p>

<p align="center"> 
<a href="./LICENSE.md"><img
src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
</p>

<br>
<a href="https://leanpub.com/bash/">
<img src="https://s3.amazonaws.com/titlepages.leanpub.com/bash/hero" width="40%" align="right">
</a>

本书原作者将书中的内容发布到了[github](https://github.com/dylanaraps/pure-bash-bible)上，我仅仅是将其翻译为中文，并解释了其中的部分语句语法，希望可以对今后的工作有所帮助。

# 以下是翻译后的原文 #

这本书的目的是汇总只使用内置`bash`的特性来实现总所周知和鲜为人知的各项任务。 使用此参考书中的代码段可以帮助你从脚本中删除不需要的依赖项，并且在大多数情况下可以使它们运行的更快。 我偶然碰到了这些技巧并在开发[neofetch](https://github.com/dylanaraps/neofetch), [pxltrm](https://github.com/dylanaraps/pxltrm) 和一些其他小的项目的时候发现了一些别的技巧。

下面的片段使用`shellcheck`进行了检查，并将测试写在了适用的地方。 想要贡献自己的代码? 阅读 [CONTRIBUTING-Zh_CN.md](https://github.com/A-BenMao/pure-bash-bible-zh_CN/blob/master/CONTRIBUTING-Zh_CN.md). 它概述了向参考书中增加片段时，单元测试的工作方式以及其他所需的内容。

看到了一些东西描述是不准确的、有缺陷的更或者是完全错误的？那么请新建一个issue或者发送一个pull request.如果参考书中缺少某些你想要的事物，也请新建一个issue并给出你能找到的解决方法。



<br>

# 目 录

<!-- vim-markdown-toc GFM -->

* [前言](#前言)
* [字符串](#字符串)
    * [删除字符串前后空格](#删除字符串前后空格)
    * [删除字符串中的所有的空白并用空格分割单词](#删除字符串中的所有的空白并用空格分割单词)
    * [在字符串上匹配正则表达式](#在字符串上匹配正则表达式)
    * [指定分隔符拆分字符串](#指定分隔符拆分字符串)
    * [将字符串转换为小写](#将字符串转换为小写)
    * [将字符串转换为大写](#将字符串转换为大写)
    * [反转字符串大小写](#反转字符串大小写)
    * [删除字符串中的引号](#删除字符串中的引号)
    * [从字符串中删除所有正则实例](#从字符串中删除所有正则实例)
    * [从字符串中删除第一次出现的正则实例](#从字符串中删除第一次出现的正则实例)
    * [在字符串开头匹配正则并删除](#在字符串开头匹配正则并删除)
    * [在字符串末尾匹配正则并删除](#在字符串末尾匹配正则并删除)
    * [百分号编码字符串](#百分号编码字符串)
    * [解码用百分比编码的字符串](#解码用百分比编码的字符串)
    * [检查字符串是否包含子字符串](#检查字符串是否包含子字符串)
    * [检查字符串是否以子字符串开头](#检查字符串是否以子字符串开头)
    * [检查字符串是否以子字符串结尾](#检查字符串是否以子字符串结尾)
* [数组](#数组)
    * [反转数组](#反转数组)
    * [删除重复的数组元素](#删除重复的数组元素)
    * [随机返回一个数组元素](#随机返回一个数组元素)
    * [循环迭代一个数组](#循环迭代一个数组)
    * [在两个值之间转换](#在两个值之间转换)
* [循环](#循环)
    * [循环生成范围内的数字](#循环生成范围内的数字)
    * [循环遍历可变数字范围](#循环遍历可变数字范围)
    * [循环数组](#循环数组)
    * [循环输出带索引的数组](#循环输出带索引的数组)
    * [循环遍历文件的内容](#循环遍历文件的内容)
    * [循环遍历文件和目录](#循环遍历文件和目录)
* [文本处理](#文本处理)
    * [读取文件到一个字符串中](#读取文件到一个字符串中)
    * [读取文件到一个数组中 (*按行读取*)](#读取文件到一个数组中)
    * [获取文件的前N行](#获取文件的前N行)
    * [获取文件的最后N行](#获取文件的最后N行)
    * [获取文件中的行数](#获取文件中的行数)
    * [计算目录中的文件或目录](#计算目录中的文件或目录)
    * [创建一个空文件](#创建一个空文件)
    * [提取两个标记之间的行](#提取两个标记之间的行)
* [文件路径](#文件路径)
    * [获取文件路径的目录名](#获取文件路径的目录名)
    * [获取文件路径的基本名称](#获取文件路径的基本名称)
* [变量](#变量)
    * [分配和访问一个变量](#分配和访问一个变量)
    * [根据另一个变量命名变量](#根据另一个变量命名变量)
* [转义字符](#转义字符)
    * [文本颜色](#文本颜色)
    * [文本属性](#文本属性)
    * [移动光标](#移动光标)
    * [删除文本](#删除文本)
* [参数拓展](#参数拓展)
    * [间接](#间接)
    * [替换](#替换)
    * [长度](#长度)
    * [扩展](#扩展)
    * [改变大小写](#改变大小写)
    * [默认值](#默认值)
* [花括号展开](#花括号展开)
    * [范围](#范围)
    * [字符串列表](#字符串列表)
* [条件表达式](#条件表达式)
    * [文件判断](#文件判断)
    * [文件比较](#文件比较)
    * [条件变量](#条件变量)
    * [比较变量](#比较变量)
* [算术运算符](#算术运算符)
    * [指派](#指派)
    * [四则运算](#四则运算)
    * [位运算](#位运算)
    * [逻辑运算](#逻辑运算)
    * [复杂运算](#复杂运算)
* [算术运算符-1](#算术运算符-1)
    * [用更简单语法设置变量](#用更简单语法设置变量)
    * [三元测试](#三元测试)
* [trap命令](#trap命令)
    * [在脚本退出时执行操作](#在脚本退出时执行操作)
    * [忽略终端中断（CTRL+C，SIGINT）](#忽略终端中断)
    * [对窗口调整大小时做出反应](#对窗口调整大小时做出反应)
    * [在命令之前执行某些操作](#在命令之前执行某些操作)
    * [在shell函数或源文件完成执行时执行某些操作](#在shell函数或源文件完成执行时执行某些操作)
* [性能](#性能)
    * [禁用Unicode码](#禁用Unicode码)
* [已过时的语法](#已过时的语法)
    * [释伴声明](#释伴声明)
    * [命令替换](#命令替换)
    * [声明函数](#声明函数)
* [内部变量](#内部变量)
    * [获取`bash`二进制文件的位置](#获取`bash`二进制文件的位置)
    * [获取当前运行`bash`命令的版本](#获取当前运行`bash`命令的版本)
    * [打开用户默认的文本编辑器](#打开用户默认的文本编辑器)
    * [获取当前函数的名称](#获取当前函数的名称)
    * [获取系统的主机名](#获取系统的主机名)
    * [获取操作系统的架构（32位或64位）](#获取操作系统的架构)
    * [获取操作系统/内核的名称](#获取操作系统/内核的名称)
    * [获取当前的工作目录](#获取当前的工作目录)
    * [获取脚本运行的秒数](#获取脚本运行的秒数)
    * [获取伪随机整数](#获取伪随机整数)
* [有关终端的信息](#有关终端的信息)
    * [获取终端的总行列数（*来自脚本*）](#获取终端的总行列数)
    * [获取终端的像素大小](#获取终端的像素大小)
    * [获取当前光标位置](#获取当前光标位置)
* [转换](#转换)
    * [将十六进制颜色转换为RGB](#将十六进制颜色转换为RGB)
    * [将RGB颜色转换为十六进制](#将RGB颜色转换为十六进制)
* [代码高尔夫](#代码高尔夫)
    * [更短的`for`循环语法](#更短的`for`循环语法)
    * [更短的无限循环](#更短的无限循环)
    * [更短的函数声明](#更短的函数声明)
    * [更短的`if`语法](#更短的`if`语法)
    * [用`case`语句来更简单的设置变量](#用`case`语句来更简单的设置变量)
* [其他](#其他)
    * [使用`read`作为`sleep`命令的替代品](#使用`read`作为`sleep`命令的替代品)
    * [检查一个命令是否在用户的PATH中](#检查一个命令是否在用户的PATH中)
    * [使用`strftime`获取当前日期](#使用`strftime`获取当前日期)
    * [获取当前用户的用户名](#获取当前用户的用户名)
    * [生成一个V4版本的UUID](#生成一个V4版本的UUID)
    * [进度条](#进度条)
    * [获取脚本中的函数列表](#获取脚本中的函数列表)
    * [绕过shell别名](#绕过shell别名)
    * [绕过shell函数](#绕过shell函数)
    * [在后台运行命令](#在后台运行命令)
* [后记](#后记)

<!-- vim-markdown-toc -->

<br>

<!-- CHAPTER START -->
# 前言

纯`bash`脚本替代外部流程和程序的集合。 `bash`脚本语言远比大部分人了解到的更强大，大多数任务都可以在不依赖外部程序的情况下由`bash`独立完成。

在`bash`中调用外部进程是昂贵的，过度使用会导致效率明显的下降。 使用内置方法编写的脚本和程序（*在适合的地方*）将更快，依赖性更小，并能对脚本本身有更好的理解。

本书的目的是为大家用`bash`编写程序和脚本过程中遇到问题时提供了一种思路。 示例展示了将这些解决方案合并到代码中的函数格式。

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 字符串

## 删除字符串前后空格

这是`sed`，`awk`，`perl`和其他工具的替代品。下面的函数通过查找所有头尾空格并在字符串的开头和结尾删除它来实现这一功能。

 `：`内置用于代替临时变量。

**示例函数:**

```sh
trim_string() {
    # Usage: trim_string "   example   string    "
    : "${1#"${1%%[![:space:]]*}"}"
    : "${_%"${_##*[![:space:]]}"}"
    printf '%s\n' "$_"
}
```

**用法示例:**

```shell
$ trim_string "    Hello,  World    "
Hello,  World

$ name="   John Black  "
$ trim_string "$name"
John Black
```


## 删除字符串中的所有的空白并用空格分割单词

这是`sed`，`awk`，`perl`和其他工具的替代品。
下面的函数通过重复使用单词拆分来创建一个没有前导/尾随空格的新字符串，并用空格分割字符串中的单词。

**示例函数:**

```sh
# shellcheck disable=SC2086,SC2048
trim_all() {
    # Usage: trim_all "   example   string    "
    set -f
    set -- $*
    printf '%s\n' "$*"
    set +f
}
```

**用法示例:**

```shell
$ trim_all "    Hello,    World    "
Hello, World

$ name="   John   Black  is     my    name.    "
$ trim_all "$name"
John Black is my name.
```

## 在字符串上匹配正则表达式

 对于使用`sed`的大部分情况，`bash`的正则表达式匹配结果完全可以替代。

**警告**: 这是少数平台相关的“bash”功能之一。
`bash`将使用用户系统上安装的任何正则表达式引擎。
如果要兼容，请坚持使用符合POSIX规范的正则表达式引擎。
绝大部分发行版Linux中的bash均实现了POSIX规范。

**警告**: 此示例仅打印第一个匹配组。 使用时多个匹配组需要进行一些修改。

**示例函数:**

```sh
regex() {
    # Usage: regex "string" "regex"
    [[ $1 =~ $2 ]] && printf '%s\n' "${BASH_REMATCH[1]}"
}
```

**用法示例:**

```shell
$ # 删除开头的空白字符.
$ regex '    hello' '^\s*(.*)'
hello

$ # 验证十六进制颜色.
$ regex "#FFFFFF" '^(#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3}))$'
#FFFFFF

$ # 验证十六进制颜色（无效）.
$ regex "red" '^(#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3}))$'
# no output (invalid)
```

**在脚本中的示例:**

```shell
is_hex_color() {
    if [[ $1 =~ ^(#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3}))$ ]]; then
        printf '%s\n' "${BASH_REMATCH[1]}"
    else
        printf '%s\n' "error: $1 is an invalid color."
        return 1
    fi
}

read -r color
is_hex_color "$color" || color="#FFFFFF"

# Do stuff.
```


## 指定分隔符拆分字符串

**警告:** 需要`bash` 4+以上的版本

这是`cut`，`awk`和其他工具的替代品。

**示例函数:**

```sh
split() {
   # Usage: split "string" "delimiter"
   IFS=$'\n' read -d "" -ra arr <<< "${1//$2/$'\n'}"
   printf '%s\n' "${arr[@]}"
}
```

**示例用法:**

```shell
$ split "apples,oranges,pears,grapes" ","
apples
oranges
pears
grapes

$ split "1, 2, 3, 4, 5" ", "
1
2
3
4
5

# 多字符分隔符也可以工作！
$ split "hello---world---my---name---is---john" "---"
hello
world
my
name
is
john
```

## 将字符串转换为小写

**警告:** 需要`bash` 4+以上的版本

**示例函数:**

```sh
lower() {
    # Usage: lower "string"
    printf '%s\n' "${1,,}"
}
```

**示例用法:**

```shell
$ lower "HELLO"
hello

$ lower "HeLlO"
hello

$ lower "hello"
hello
```

## 将字符串转换为大写

**警告:** 需要`bash` 4+以上的版本

**示例函数:**

```sh
upper() {
    # Usage: upper "string"
    printf '%s\n' "${1^^}"
}
```

**示例用法:**

```shell
$ upper "hello"
HELLO

$ upper "HeLlO"
HELLO

$ upper "HELLO"
HELLO
```

## 反转字符串大小写

**警告:** 需要`bash` 4+以上的版本

**示例函数:**

```sh
reverse_case() {
    # Usage: reverse_case "string"
    printf '%s\n' "${1~~}"
}
```

**示例用法:**

```shell
$ reverse_case "hello"
HELLO

$ reverse_case "HeLlO"
hElLo

$ reverse_case "HELLO"
hello
```

## 删除字符串中的引号

**示例函数:**

```sh
trim_quotes() {
    # Usage: trim_quotes "string"
    : "${1//\'}"
    printf '%s\n' "${_//\"}"
}
```

**示例用法:**

```shell
$ var="'Hello', \"World\""
$ trim_quotes "$var"
Hello, World
```

## 从字符串中删除所有正则实例

**示例函数:**

```sh
strip_all() {
    # Usage: strip_all "string" "pattern"
    printf '%s\n' "${1//$2}"
}
```

**示例用法:**

```shell
$ strip_all "The Quick Brown Fox" "[aeiou]"
Th Qck Brwn Fx

$ strip_all "The Quick Brown Fox" "[[:space:]]"
TheQuickBrownFox

$ strip_all "The Quick Brown Fox" "Quick "
The Brown Fox
```

## 从字符串中删除第一次出现的正则实例

**示例函数:**

```sh
strip() {
    # Usage: strip "string" "pattern"
    printf '%s\n' "${1/$2}"
}
```

**示例用法:**

```shell
$ strip "The Quick Brown Fox" "[aeiou]"
Th Quick Brown Fox

$ strip "The Quick Brown Fox" "[[:space:]]"
TheQuick Brown Fox
```

## 在字符串开头匹配正则并删除

**示例函数:**

```sh
lstrip() {
    # Usage: lstrip "string" "pattern"
    printf '%s\n' "${1##$2}"
}
```

**示例用法:**

```shell
$ lstrip "The Quick Brown Fox" "The "
Quick Brown Fox
```

## 在字符串末尾匹配正则并删除

**示例函数:**

```sh
rstrip() {
    # Usage: rstrip "string" "pattern"
    printf '%s\n' "${1%%$2}"
}
```

**示例用法:**

```shell
$ rstrip "The Quick Brown Fox" " Fox"
The Quick Brown
```

## 百分号编码字符串

**示例函数:**

```sh
urlencode() {
    # Usage: urlencode "string"
    local LC_ALL=C
    for (( i = 0; i < ${#1}; i++ )); do
        : "${1:i:1}"
        case "$_" in
            [a-zA-Z0-9.~_-])
                printf '%s' "$_"
            ;;

            *)
                printf '%%%02X' "'$_"
            ;;
        esac
    done
    printf '\n'
}
```

**示例用法:**

```shell
$ urlencode "https://github.com/dylanaraps/pure-bash-bible"
https%3A%2F%2Fgithub.com%2Fdylanaraps%2Fpure-bash-bible
```

## 解码用百分比编码的字符串

**示例函数:**

```sh
urldecode() {
    # Usage: urldecode "string"
    : "${1//+/ }"
    printf '%b\n' "${_//%/\\x}"
}
```

**示例用法:**

```shell
$ urldecode "https%3A%2F%2Fgithub.com%2Fdylanaraps%2Fpure-bash-bible"
https://github.com/dylanaraps/pure-bash-bible
```

## 检查字符串是否包含子字符串

**用于测试:**

```shell
if [[ $var == *sub_string* ]]; then
    printf '%s\n' "sub_string is in var."
fi

# 反转 (子串不在字符串中).
if [[ $var != *sub_string* ]]; then
    printf '%s\n' "sub_string is not in var."
fi

# 也可以在数组中运行
if [[ ${arr[*]} == *sub_string* ]]; then
    printf '%s\n' "sub_string is in array."
fi
```

**使用case语句:**

```shell
case "$var" in
    *sub_string*)
        # Do stuff
    ;;

    *sub_string2*)
        # Do more stuff
    ;;

    *)
        # Else
    ;;
esac
```

## 检查字符串是否以子字符串开头

```shell
if [[ $var == sub_string* ]]; then
    printf '%s\n' "var starts with sub_string."
fi

# 反转 (变量不是以子串开头).
if [[ $var != sub_string* ]]; then
    printf '%s\n' "var does not start with sub_string."
fi
```

## 检查字符串是否以子字符串结尾

```shell
if [[ $var == *sub_string ]]; then
    printf '%s\n' "var ends with sub_string."
fi

# Inverse (var does not end with sub_string).
if [[ $var != *sub_string ]]; then
    printf '%s\n' "var does not end with sub_string."
fi
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 数组

## 反转数组

启用`extdebug`允许访问`BASH_ARGV`数组，该数组反向存储当前函数的参数

**示例函数:**

```sh
reverse_array() {
    # Usage: reverse_array "array"
    shopt -s extdebug
    f()(printf '%s\n' "${BASH_ARGV[@]}"); f "$@"
    shopt -u extdebug
}
```

**示例用法:**

```shell
$ reverse_array 1 2 3 4 5
5
4
3
2
1

$ arr=(red blue green)
$ reverse_array "${arr[@]}"
green
blue
red
```

## 删除重复的数组元素

创建临时关联数组。设置关联数组值并发生重复赋值时，bash会覆盖该键。这允许我们有效地删除数组重复。

**警告:** 版本要求 `bash` 4+

**示例函数:**

```sh
remove_array_dups() {
    # Usage: remove_array_dups "array"
    declare -A tmp_array

    for i in "$@"; do
        [[ $i ]] && IFS=" " tmp_array["${i:- }"]=1
    done

    printf '%s\n' "${!tmp_array[@]}"
}
```

**示例用法:**

```shell
$ remove_array_dups 1 1 2 2 3 3 3 3 3 4 4 4 4 4 5 5 5 5 5 5
1
2
3
4
5

$ arr=(red red green blue blue)
$ remove_array_dups "${arr[@]}"
red
green
blue
```

## 随机返回一个数组元素

**示例函数:**

```sh
random_array_element() {
    # Usage: random_array_element "array"
    local arr=("$@")
    printf '%s\n' "${arr[RANDOM % $#]}"
}
```
bash的SHELL参数RANDOM可以生成0-32767的随机数
想设定从1到N的随机数范围的话，可以使用：
$ ( ( (RANDOM % n) + 1 ))

**示例用法:**

```shell
$ array=(red green blue yellow brown)
$ random_array_element "${array[@]}"
yellow

# Multiple arguments can also be passed.
$ random_array_element 1 2 3 4 5 6 7
3
```

## 循环迭代一个数组

每次`printf`调用时，都会打印下一个数组元素。当打印到达最后一个数组元素时，它再次从第一个元素开始。

```sh
arr=(a b c d)

cycle() {
    printf '%s ' "${arr[${i:=0}]}"
    ((i=i>=${#arr[@]}-1?0:++i))
}
```


## 在两个值之间转换

这与上面的工作方式相同，这只是一个不同的用例。


```sh
arr=(true false)

cycle() {
    printf '%s ' "${arr[${i:=0}]}"
    ((i=i>=${#arr[@]}-1?0:++i))
}
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 循环

## 循环生成范围内的数字

替代`seq`.

```shell
# Loop from 0-100 (no variable support).
for i in {0..100}; do
    printf '%s\n' "$i"
done
```

## 循环遍历可变数字范围

替代 `seq`.

```shell
# Loop from 0-VAR.
VAR=50
for ((i=0;i<=VAR;i++)); do
    printf '%s\n' "$i"
done
```

## 循环数组

```shell
arr=(apples oranges tomatoes)

# Just elements.
for element in "${arr[@]}"; do
    printf '%s\n' "$element"
done
```

## 循环输出带索引的数组

```shell
arr=(apples oranges tomatoes)

# 元素和索引.
for i in "${!arr[@]}"; do
	printf '%s %s\n' "$i ${arr[i]}"
done

# 替代方法.
for ((i=0;i<${#arr[@]};i++)); do
    printf '%s %s\n' "$i ${arr[i]}"
done
```

## 循环遍历文件的内容

```shell
while read -r line; do
    printf '%s\n' "$line"
done < "file"
```

## 循环遍历文件和目录


不要 `ls`.

```shell
# 遍历当前目录下的文件和目录.
for file in *; do
    printf '%s\n' "$file"
done

# 遍历目录中的png图片.
for file in ~/Pictures/*.png; do
    printf '%s\n' "$file"
done

# 迭代输出目录.
for dir in ~/Downloads/*/; do
    printf '%s\n' "$dir"
done

# 支持扩展.
for file in /path/to/parentdir/{file1,file2,subdir/file3}; do
    printf '%s\n' "$file"
done

# 递归迭代，输出子目录下的所有文件.
# 
shopt -s globstar
for file in ~/Pictures/**/*; do
    printf '%s\n' "$file"
done
shopt -u globstar
```
globstar是Bash 4.0才引入的选项，当设置启用globstar(shopt -s globstar)时，两个星号意为对通配符进行展开就可以匹配任何当前目录(包括子目录)以及其的文件；若不启用globstar(shopt -u globstar)，两个星号通配符的作用和一个星号通配符是相同的。
<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 文本处理

**警告:** `bash`在小于`<4.4`的版本中不能正确处理二进制数据.

## 读取文件到一个字符串中

替代 `cat` 命令.

```shell
file_data="$(<"file")"
```

## 读取文件到一个数组中 (*按行读取*)

替代 `cat` 命令.

```shell
# Bash <4
IFS=$'\n' read -d "" -ra file_data < "file"

# Bash 4+
mapfile -t file_data < "file"
```

## 获取文件的前N行

替代 `head` 命令.

**警告:** 版本要求 `bash` 4+

**示例函数:**

```sh
head() {
    # Usage: head "n" "file"
    mapfile -tn "$1" line < "$2"
    printf '%s\n' "${line[@]}"
}
```

**示例用法:**

```shell
$ head 2 ~/.bashrc
# Prompt
PS1='➜ '

$ head 1 ~/.bashrc
# Prompt
```

## 获取文件的最后N行

替代 `tail` 命令.

**警告:** 版本要求 `bash` 4+

**示例函数:**

```sh
tail() {
    # Usage: tail "n" "file"
    mapfile -tn 0 line < "$2"
    printf '%s\n' "${line[@]: -$1}"
}
```

**示例用法:**

```shell
$ tail 2 ~/.bashrc
# Enable tmux.
# [[ -z "$TMUX"  ]] && exec tmux

$ tail 1 ~/.bashrc
# [[ -z "$TMUX"  ]] && exec tmux
```

## 获取文件中的行数


替代 `wc -l`.

**示例函数 (bash 4):**

```sh
lines() {
    # Usage: lines "file"
    mapfile -tn 0 lines < "$1"
    printf '%s\n' "${#lines[@]}"
}
```

**示例函数 (bash 3):**

这个方法比`mapfile`方法使用更少的内存，并且在`bash` 3中工作，但对于更大的文件来说它更慢。

```sh
lines_loop() {
    # Usage: lines_loop "file"
    count=0
    while IFS= read -r _; do
        ((count++))
    done < "$1"
    printf '%s\n' "$count"
}
```

**示例用法:**

```shell
$ lines ~/.bashrc
48

$ lines_loop ~/.bashrc
48
```

## 计算目录中的文件或目录


这是通过将glob的输出传递给函数然后计算参数的数量来实现的。



**示例函数:**

```sh
count() {
    # Usage: count /path/to/dir/*
    #        count /path/to/dir/*/
    printf '%s\n' "$#"
}
```

**示例用法:**

```shell
# Count all files in dir.
$ count ~/Downloads/*
232

# Count all dirs in dir.
$ count ~/Downloads/*/
45

# Count all jpg files in dir.
$ count ~/Pictures/*.jpg
64
```

## 创建一个空文件

替代 `touch`.

```shell
# 简短的方式.
>file

# 更长的替代品:
:>file
echo -n >file
printf '' >file
```

## 提取两个标记之间的行

**示例函数:**

```sh
extract() {
    # 用法: extract file "opening marker" "closing marker"
    while IFS=$'\n' read -r line; do
        [[ $extract && $line != "$3" ]] &&
            printf '%s\n' "$line"

        [[ $line == "$2" ]] && extract=1
        [[ $line == "$3" ]] && extract=
    done < "$1"
}
```

**示例用法:**

```shell
# 从MarkDown文件中提取代码块.
$ extract ~/projects/pure-bash/README.md '```sh' '```'
# Output here...
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 文件路径

## 获取文件路径的目录名

替代 `dirname` 命令.

**示例函数:**

```sh
dirname() {
    # 用法: dirname "path"
    printf '%s\n' "${1%/*}/"
}
```

**示例用法:**

```shell
$ dirname ~/Pictures/Wallpapers/1.jpg
/home/black/Pictures/Wallpapers/

$ dirname ~/Pictures/Downloads/
/home/black/Pictures/
```

## 获取文件路径的基本名称


替代 `basename` 命令.

**示例函数:**

```sh
basename() {
    # Usage: basename "path"
    : "${1%/}"
    printf '%s\n' "${_##*/}"
}
```

**示例用法:**

```shell
$ basename ~/Pictures/Wallpapers/1.jpg
1.jpg

$ basename ~/Pictures/Downloads/
Downloads
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 变量

## 分配和访问一个变量

```shell
$ hello_world="value"

# 创建一个变量名.
$ var="world"
$ ref="hello_$var"

# 打印存储为 'hello_$var' 变量名称的值.
$ printf '%s\n' "${!ref}"
value
```

或者, 在 `bash` 4.3+以上版本:

```shell
$ hello_world="value"
$ var="world"

# 声明一个名称引用.
$ declare -n ref=hello_$var

$ printf '%s\n' "$ref"
value
```

## 根据另一个变量命名变量

```shell
$ var="world"
$ declare "hello_$var=value"
$ printf '%s\n' "$hello_world"
value
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 转义字符

与流行的看法相反, 使用原始的转义字符并不会出现问题. 使用`tput`抽象相同的ANSI序列，就像手动打印一样. 更糟糕的是，`tput`实际上并不是便携式的. 有许多`tput`变体，每个变体都有不同的命令和语法 (*尝试运行 `tput setaf 3` 在 FreeBSD 系统里*). 

## 文本颜色

**NOTE:** 需要RGB值的序列仅适用于真彩色终端仿真器.

| 序列 | 它将做什么？ | 值 |
| -------- | ---------------- | ----- |
| `\e[38;5;<NUM>m` | 设置文本前景色. | `0-255`
| `\e[48;5;<NUM>m` | 设置文本背景颜色. | `0-255`
| `\e[38;2;<R>;<G>;<B>m` | 将文本前景色设置为RGB颜色. | `R`, `G`, `B`
| `\e[48;2;<R>;<G>;<B>m` | 将文本背景颜色设置为RGB颜色. | `R`, `G`, `B`

## 文本属性

| 序列 | 它将做什么？ |
| -------- | ---------------- |
| `\e[m`  | 重置文本格式和颜色.
| `\e[1m` | 粗体. |
| `\e[2m` | 微弱的文字. |
| `\e[3m` | 斜体文字. |
| `\e[4m` | 下划线文字. |
| `\e[5m` | 慢速闪烁. |
| `\e[7m` | 交换前景色和背景色. |


## 移动光标

| 序列 | 它将做什么？ | 值 |
| -------- | ---------------- | ----- |
| `\e[<LINE>;<COLUMN>H` | 将光标移动到绝对位置. | `line`, `column`
| `\e[H` | 将光标移动到原位 (`0,0`). |
| `\e[<NUM>A` | 将光标向上移动N行. | `num`
| `\e[<NUM>B` | 将光标向下移动N行. | `num`
| `\e[<NUM>C` | 将光标向右移动N列. | `num`
| `\e[<NUM>D` | 将光标向左移动N列. | `num`
| `\e[s` | 保存光标位置. |
| `\e[u` | 恢复光标位置. |


## 删除文本

| 序列 | 它将做什么？ |
| -------- | ---------------- |
| `\e[K` | 从光标位置删除到行尾.
| `\e[1K` | 从光标位置删除到行首.
| `\e[2K` | 擦除整个当前行.
| `\e[J` | 从当前行删除到屏幕底部.
| `\e[1J` | 从当前行删除到屏幕顶部.
| `\e[2J` | 清除屏幕.
| `\e[2J\e[H` | 清除屏幕并将光标移动到 `0,0`.


<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 参数拓展

## 间接

| 参数 | 它将做什么？ |
| --------- | ---------------- |
| `${!VAR}` | 根据`VAR`的值访问一个变量.
| `${!VAR*}` | 扩展为以`VAR`开头的变量名列表，并用`IFS`分隔. |
| `${!VAR@}` | 扩展为以`VAR`开头的变量名列表，并用`IFS`分隔. 如果是双引号，则每个变量名称都会扩展为单独的单词. |


## 替换

| 参数 | 它将做什么？ |
| --------- | ---------------- |
| `${VAR#PATTERN}` | 删除第一次匹配的模式及其左边的字符. |
| `${VAR##PATTERN}` | 删除最后一次匹配的模式及其左边的字符. |
| `${VAR%PATTERN}` | 删除最后一次匹配的模式及其右边的字符. |
| `${VAR%%PATTERN}` | 删除第一次匹配的模式及其右边的字符. |
| `${VAR/PATTERN/REPLACE}` | 替换第一次匹配的字符.
| `${VAR//PATTERN/REPLACE}` | 替换所有匹配的字符.
| `${VAR/PATTERN}` | 删除第一次匹配的字符.
| `${VAR//PATTERN}` | 删除所有匹配的字符.

## 长度

| 参数 | 它将做什么？ |
| --------- | ---------------- |
| `${#VAR}` | 字符变量的长度.
| `${#ARR[@]}` | 数组的长度.

## 扩展

| 参数 | 它将做什么？ | 版本要求 |
| --------- | ---------------- |
| `${VAR:OFFSET}` | 从变量中删除第OFFSET个字符及之前的字符.
| `${VAR:OFFSET:LENGTH}` | 获得从`OFFSET`字符之后`LENGTH`个字符的字符串. <br> (`${VAR:10:10}`: 获得从第10个字符到第20个字符的字符串)
| `${VAR:: OFFSET}` | 从变量中获取前`OFFSET`个字符.
| `${VAR:: -OFFSET}` | 从变量中移除前`OFFSET`个字符.
| `${VAR: -OFFSET}` | 从变量中获取最后`OFFSET`个字符.
| `${VAR:OFFSET:-OFFSET}` | 删除前`OFFSET`个字符以及最后`OFFSET`个字符. | `bash 4.2+` |

## 改变大小写

| 参数 | 它将做什么？ | 版本要求 |
| --------- | ---------------- | ------ |
| `${VAR^}` | 大写第一个字符. | `bash 4+` |
| `${VAR^^}` | 大写所有字符. | `bash 4+` |
| `${VAR,}` | 小写第一个字符. | `bash 4+` |
| `${VAR,,}` | 小写所有字符. | `bash 4+` |
| `${VAR~}` | 反转第一个字符. | `bash 4+` |
| `${VAR~~}` | 反转所有字符. | `bash 4+` |


## 默认值

| 参数 | 它将做什么？ |
| --------- | ---------------- |
| `${VAR:-STRING}` | 如果 `VAR` 为空或未设置，使用 `STRING` 作为它的值.
| `${VAR-STRING}` | 如果 `VAR` 未设置, 使用 `STRING` 作为它的值.
| `${VAR:=STRING}` | 如果 `VAR` 为空或未设置, 设置 `VAR` 的值为 `STRING`.
| `${VAR=STRING}` | 如果 `VAR` 未设置, 设置 `VAR` 的值为 `STRING`.
| `${VAR:+STRING}` | 如果 `VAR` 不为空, 使用 `STRING` 作为它的值.
| `${VAR+STRING}` | 如果 `VAR` 已设置, 使用 `STRING` 作为它的值.
| `${VAR:?STRING}` | 如果为空或未设置，则显示一个错误.
| `${VAR?STRING}` | 如果未设置则显示一个错误.


<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 花括号展开

## 范围

```shell
# 符号: {<START>..<END>}

# 打印 1-100 之间的数字.
echo {1..100}

# 打印一个范围内的浮点数.
echo 1.{1..9}

# 打印a-z间的字符.
echo {a..z}
echo {A..Z}

# 嵌套.
echo {A..Z}{0..9}

# 打印用零填充的数字.
# 警告: bash 4+
echo {01..100}

# 更改步长.
# 符号: {<START>..<END>..<INCREMENT>}
# 警告: bash 4+
echo {1..10..2} # 每次增加2.
```

## 字符串列表

```shell
echo {apples,oranges,pears,grapes}

# 示例用法:
# 删除~/Downloads/目录下的 Movies, Music 和 ISOS 文件夹 .
rm -rf ~/Downloads/{Movies,Music,ISOS}
```

<!-- CHAPTER END -->


<!-- CHAPTER START -->

# 条件表达式

## 文件判断

| 表达式 | 值  | 它有什么作用？ |
| ---------- | ------ | ---------------- |
| `-a`       | `file` | 文件存在
| `-b`       | `file` | 文件存在并且是块特殊文件.
| `-c`       | `file` | 文件存在并且是字符特殊文件.
| `-d`       | `file` | 文件存在且是目录.
| `-e`       | `file` | 文件存在.
| `-f`       | `file` | 文件存在且是常规文件.
| `-g`       | `file` | 文件存在且其set-group-id位已设置.
| `-h`       | `file` | 文件存在并且是符号链接.
| `-k`       | `file` | 文件存在且其sticky-bit已设置
| `-p`       | `file` | 文件存在并且是命名管道 (*FIFO*).
| `-r`       | `file` | 文件存在且可读.
| `-s`       | `file` | 文件存在且其大小大于零.
| `-t`       | `fd`   | 文件描述符是打开的并且引用到一个终端.
| `-u`       | `file` | 文件存在且其set-user-id位已设置.
| `-w`       | `file` | 文件存在且可写.
| `-x`       | `file` | 文件存在且可执行.
| `-G`       | `file` | 文件存在且拥有者是一个有效组ID.
| `-L`       | `file` | 文件存在并且是符号链接.
| `-N`       | `file` | 文件存在且自上次读取后已被修改.
| `-O`       | `file` | 文件存在并且拥有者是一个有效用户ID.
| `-S`       | `file` | 文件存在且是套接字.

## 文件比较

| 表达式 | 它有什么作用？ |
| ---------- | ---------------- |
| `file -ef file2` | 是否两个文件都引用相同的inode和设备编号.
| `file -nt file2` | 是否 `file` 比 `file2`更新 (*使用修改时间*) 或者 `file` 存在而 `file2` 不存在.
| `file -ot file2` | 是否 `file` 比 `file2`更老 (*使用修改时间*) 或者 `file2` 存在而 `file` 不存在.

## 条件变量

| 表达式 | 值 | 它有什么作用？ |
| ---------- | ----- | ---------------- |
| `-o`       | `opt` | 是否启用了shell选项.
| `-v`       | `var` | 是否变量具有指定的值.
| `-R`       | `var` | 是否变量是一个名称引用.
| `-z`       | `var` | 是否字符串的长度为零.
| `-n`       | `var` | 是否字符串的长度不为零.

## 比较变量

| 表达式 | 它有什么作用？ |
| ---------- | ---------------- |
| `var = var2` | 等于.
| `var == var2` | 等于 (*同义词 `=`*).
| `var != var2` | 不等于.
| `var < var2` | 小于 (*以ASCII字母顺序排列.*)
| `var > var2` | 大于 (*以ASCII字母顺序排列.*)

<!-- CHAPTER END -->

<!-- CHAPTER START -->

# 算术运算符

## 指派

| 操作符 | 它有什么作用？ |
| --------- | ---------------- |
| `=`       | 初始化或更改变量的值。

## 四则运算

| 操作符 | 它有什么作用？ |
| --------- | ---------------- |
| `+` | 加
| `-` | 减
| `*` | 乘
| `/` | 除
| `**` | 幂运算
| `%` | 求模
| `+=` | 先加后赋值 (*`x += y`等同于`x = x + y`*)
| `-=` | 先减后赋值 (*`x -= y`等同于`x = x - y`*)
| `*=` | 先乘后赋值 (*`x *= y`等同于`x = x * y`*)
| `/=` | 先除后赋值 (*`x /= y`等同于`x = x / y`*)
| `%=` | 先取模后赋值 (*`x %= y`等同于`x = x % y`*)

## 位运算

| 操作符 | 它有什么作用？ |
| --------- | ---------------- |
| `<<` | 按位左移
| `<<=` | 按位左移后赋值
| `>>` | 按位右移
| `>>=` | 按位右移后赋值
| `&` | 按位与操作
| `&=` | 按位与操作后赋值
| `\|` | 按位或操作
| `\|=` | 按位或操作赋值
| `~` | 按位非操作
| `^` | 按位异或操作
| `^=` | 按位异或操作后赋值

## 逻辑运算

| 操作符 | 它有什么作用？ |
| --------- | ---------------- |
| `!` | NOT
| `&&` | AND
| `\|\|` | OR

## 复杂运算

| 操作符 | 它有什么作用？ | 例子 |
| --------- | ---------------- | ------- |
| `,` | 逗号分隔符 | `((a=1,b=2,c=3))`


<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 算术运算符-1

## 用更简单语法设置变量

```shell
# 简单的数学运算
((var=1+2))

# 递减/递增变量
((var++))
((var--))
((var+=1))
((var-=1))

# 使用变量
((var=var2*arr[2]))
```

## 三元测试

```shell
# 如果var2大于var，则将var的值设置为var2，否则设置为var.
# var: 要设置的变量.
# var2>var: 条件测试.
# ?var2: 如果条件测试成功时生效.
# :var: 条件测试失败时生效.
((var=var2>var?var2:var))
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# trap命令

Traps允许脚本在各种信号上执行代码。在 [pxltrm](https://github.com/dylanaraps/pxltrm) (*用bash编写的像素艺术编辑器*)  traps 用于在窗口大小调整时重绘用户界面。另一个用例是在脚本退出时清理临时文件。

Traps应该在脚本开头附近添加，以便捕获任何早期错误.

**NOTE:** 有关信号的完整列表，请参阅 `trap -l`.


## 在脚本退出时执行操作

```shell
# 脚本退出时清除屏幕。
trap 'printf \\e[2J\\e[H\\e[m' EXIT
```

## 忽略终端中断（CTRL+C，SIGINT）

```shell
trap '' INT
```

## 对窗口调整大小时做出反应

```shell
# 在窗口调整大小时调用函数.
trap 'code_here' SIGWINCH
```

## 在命令之前执行某些操作

```shell
trap 'code_here' DEBUG
```

## 在shell函数或源文件完成执行时执行某些操作

```shell
trap 'code_here' RETURN
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 性能

## 禁用Unicode码

如果不需要unicode，则可以禁用它以提高性能。结果可能会有所不同，但是[neofetch](https://github.com/dylanaraps/neofetch) 和其他程序有明显改善。

```shell
# 禁用 unicode.
LC_ALL=C
LANG=C
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 已过时的语法

## 释伴声明

使用 `#!/usr/bin/env bash` 而不是 `#!/bin/bash`.

- 前者搜索用户的 `PATH` 以查找 `bash` 二进制文件.
- 后者假设它始终安装在 `/bin/` 目录，可能导致问题.

```shell
# 正确的方式:

    #!/usr/bin/env bash

# 错误的方式:

    #!/bin/bash
```

## 命令替换

使用 `$()`而不是 `` ` ` ``.

```shell
# 正确的方式.
var="$(command)"

# 错误的方式.
var=`command`

# $() 很容易嵌套，而``不能.
var="$(command "$(command)")"
```

## 声明函数

不要使用`function`关键字，它会降低与旧版本`bash`的兼容性.

```shell
# 正确的方式.
do_something() {
    # ...
}

# 错误的方式.
function do_something() {
    # ...
}
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 内部变量

## 获取`bash`二进制文件的位置

```shell
"$BASH"
```

## 获取当前运行`bash`命令的版本

```shell
# 作为字符串.
"$BASH_VERSION"

# 作为数组.
"${BASH_VERSINFO[@]}"
```

## 打开用户默认的文本编辑器

```shell
"$EDITOR" "$file"

# NOTE: 这个变量可能是空的，设置一个失败调用值.
"${EDITOR:-vi}" "$file"
```

## 获取当前函数的名称

```shell
# 当前函数.
"${FUNCNAME[0]}"

# 父函数.
"${FUNCNAME[1]}"

# 等等.
"${FUNCNAME[2]}"
"${FUNCNAME[3]}"

# 包括父类的所有函数
"${FUNCNAME[@]}"
```

## 获取系统的主机名

```shell
"$HOSTNAME"

# NOTE: 这个变量可能是空的.
# (可选):将失败调用设置为hostname命令
"${HOSTNAME:-$(hostname)}"
```

## 获取操作系统的架构（32位或64位）

```shell
"$HOSTTYPE"
```

## 获取操作系统/内核的名称

这可用于条件判断不同的操作系统，而无需调用`uname`。

```shell
"$OSTYPE"
```

## 获取当前的工作目录

这是内置`pwd`的替代方案。

```shell
"$PWD"
```

## 获取脚本运行的秒数

```shell
"$SECONDS"
```

## 获取伪随机整数

每次使用`$RANDOM`时, 返回`0` and `32767`之间的不同整数。 此变量不应用于与安全性相关的任何内容（包括加密密钥等）。


```shell
"$RANDOM"
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 有关终端的信息

## 获取终端的总行列数（*来自脚本*）

在纯bash中编写脚本和`stty`/`tput`无法调用时，这很方便。

**示例函数:**

```sh
get_term_size() {
    # 用法: get_term_size

    # (:;:) 是一个短暂暂停，以确保变量立即导出
    shopt -s checkwinsize; (:;:)
    printf '%s\n' "$LINES $COLUMNS"
}
```

**示例用法:**

```shell
# 输出: 行数 列数
$ get_term_size
15 55
```

## 获取终端的像素大小

**警告**: 这在某些终端仿真器中不起作用。

**示例函数:**

```sh
get_window_size() {
    # 用法: get_window_size
    printf '%b' "${TMUX:+\\ePtmux;\\e}\\e[14t${TMUX:+\\e\\\\}"
    IFS=';t' read -d t -t 0.05 -sra term_size
    printf '%s\n' "${term_size[1]}x${term_size[2]}"
}
```

**示例用法:**

```shell
# 输出: 长度x高度
$ get_window_size
1200x800

# 输出 (失败):
$ get_window_size
x
```

## 获取当前光标位置

用纯bash创建TUI时，是很有用的。
TUI是指文本用户界面(Text-based User Interface)，通过文本实现交互窗口展示内容，定位光标和鼠标实现用户交互。

**示例函数:**

```sh
get_cursor_pos() {
    # 用法: get_cursor_pos
    IFS='[;' read -p $'\e[6n' -d R -rs _ y x _
    printf '%s\n' "$x $y"
}
```

**示例用法:**

```shell
# Output: X Y
$ get_cursor_pos
1 8
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 转换

## 将十六进制颜色转换为RGB

**示例函数:**

```sh
hex_to_rgb() {
    # Usage: hex_to_rgb "#FFFFFF"
    #        hex_to_rgb "000000"
    : "${1/\#}"
    ((r=16#${_:0:2},g=16#${_:2:2},b=16#${_:4:2}))
    printf '%s\n' "$r $g $b"
}
```

**示例用法:**

```shell
$ hex_to_rgb "#FFFFFF"
255 255 255
```


## 将RGB颜色转换为十六进制

**示例函数:**

```sh
rgb_to_hex() {
    # Usage: rgb_to_hex "r" "g" "b"
    printf '#%02x%02x%02x\n' "$1" "$2" "$3"
}
```

**示例用法:**

```shell
$ rgb_to_hex "255" "255" "255"
#FFFFFF
```


# 代码高尔夫

[CODE GOLF](https://en.wikipedia.org/wiki/Code_golf)，看看谁写的代码最短！


## 更短的`for`循环语法

```shell
# Tiny C风格.
for((;i++<10;)){ echo "$i";}

# 未记载的方法.
for i in {1..10};{ echo "$i";}

# 扩展.
for i in {1..10}; do echo "$i"; done

# C语言风格.
for((i=0;i<=10;i++)); do echo "$i"; done
```

## 更短的无限循环

```shell
# 普通方法
while :; do echo hi; done

# 更短的方式
for((;;)){ echo hi;}
```

## 更短的函数声明

```shell
# 普通方法
f(){ echo hi;}

# 用于子shell
f()(echo hi)

# 用于四则运算
# 这可以被用来分配整数值。
# Example: f a=1
#          f a++
f()(($1))

# 用作测试，循环等
# NOTE: ‘while’, ‘until’, ‘case’, ‘(())’, ‘[[]]’ 也可以使用.
f()if true; then echo "$1"; fi
f()for i in "$@"; do echo "$i"; done
```

## 更短的`if`语法

```shell
# 一行
# Note: 当第一段是正确时执行第三段
# Note: 此处利用了逻辑运算符的短路规则
[[ $var == hello ]] && echo hi || echo bye
[[ $var == hello ]] && { echo hi; echo there; } || echo bye

# 多行（没有else，单条语句）
# Note: 退出状态可能与if语句不同
[[ $var == hello ]] &&
    echo hi

# 多行 (没有 else)
[[ $var == hello ]] && {
    echo hi
    # ...
}
```

## 用`case`语句来更简单的设置变量

内置的`：`可以用来避免在case语句中重复的实用`variable =`。 
`$ _`变量存储最后一个命令的最后一个参数。
 `：`总会成功，所以它可以用来存储变量值。

```shell
case "$OSTYPE" in
    "darwin"*)
        : "MacOS"
    ;;

    "linux"*)
        : "Linux"
    ;;

    *"bsd"* | "dragonfly" | "bitrig")
        : "BSD"
    ;;

    "cygwin" | "msys" | "win32")
        : "Windows"
    ;;

    *)
        printf '%s\n' "Unknown OS detected, aborting..." >&2
        exit 1
    ;;
esac

# 最后，获取变量值.
os="$_"
```

<!-- CHAPTER END -->

<!-- CHAPTER START -->
# 其他

## 使用`read`作为`sleep`命令的替代品

令人惊讶的是，`sleep`是一个外部命令而不是`bash`内置的。

**警告:** 要求`bash`版本 4+

**示例函数:**

```sh
read_sleep() {
    # 用法: sleep 1
    #        sleep 0.2
    read -rt "$1" <> <(:) || :
}
```

**示例用法:**

```shell
read_sleep 1
read_sleep 0.1
read_sleep 30
```

对于性能要求较高的情况下，打开和关闭过多的文件描述符是不实用的，对于`read`的所有调用，文件描述符的分配只能进行一次：:

(请参阅最原始的功能实现 https://blog.dhampir.no/content/sleeping-without-a-subprocess-in-bash-and-how-to-sleep-forever)

```shell
exec {sleep_fd}<> <(:)
while some_quick_test; do
    # equivalent of sleep 0.001
    read -t 0.001 -u $sleep_fd
done
```

## 检查一个命令是否在用户的PATH中

```shell
# 有3种方法可以使用，任何一种都正确。
type -p executable_name &>/dev/null
hash executable_name &>/dev/null
command -v executable_name &>/dev/null

# 用作检测.
if type -p executable_name &>/dev/null; then
    # Program is in PATH.
fi

# 反向检测.
if ! type -p executable_name &>/dev/null; then
    # Program is not in PATH.
fi

# 示例（如果未安装程序，则提前退出）.
if ! type -p convert &>/dev/null; then
    printf '%s\n' "error: convert is not installed, exiting..."
    exit 1
fi
```

## 使用`strftime`获取当前日期

Bash的`printf`有一个内置的获取日期的方法，可用来代替`date`命令。

**警告:** 要求`bash`版本 4+

**示例函数:**

```sh
date() {
    # 用法: date "format"
    printf "%($1)T\\n" "-1"
}
```
- 了解时间格式: ['man strftime'](http://www.man7.org/linux/man-pages/man3/strftime.3.html) .

**示例用法:**

```shell
# 使用上述函数.
$ date "%a %d %b  - %l:%M %p"
Fri 15 Jun  - 10:00 AM

# 直接使用printf.
$ printf '%(%a %d %b  - %l:%M %p)T\n' "-1"
Fri 15 Jun  - 10:00 AM

# 使用printf分配变量.
$ printf -v date '%(%a %d %b  - %l:%M %p)T\n' '-1'
$ printf '%s\n' "$date"
Fri 15 Jun  - 10:00 AM
```

## 获取当前用户的用户名

**警告:** 要求`bash`版本 4.4+

```shell
$ : \\u
# Expand the parameter as if it were a prompt string.
$ printf '%s\n' "${_@P}"
black
```

## 生成一个V4版本的UUID

**警告**: 生成的值不具有加密安全性。

**示例函数:**

```sh
uuid() {
    # 用法: uuid
    C="89ab"

    for ((N=0;N<16;++N)); do
        B="$((RANDOM%256))"

        case "$N" in
            6)  printf '4%x' "$((B%16))" ;;
            8)  printf '%c%x' "${C:$RANDOM%${#C}:1}" "$((B%16))" ;;

            3|5|7|9)
                printf '%02x-' "$B"
            ;;

            *)
                printf '%02x' "$B"
            ;;
        esac
    done

    printf '\n'
}
```

**示例用法:**

```shell
$ uuid
d5b6c731-1310-4c24-9fe3-55d556d44374
```

## 进度条

这是一种绘制进度条的简单方法，无需在函数本身中使用for循环。

**示例函数:**

```sh
bar() {
    # 用法: bar 1 10
    #           ^----- 已经完成的百分比 (0-100).
    #             ^--- 字符总长度.
    ((elapsed=$1*$2/100))

    # 创建空格表示的进度条
    printf -v prog  "%${elapsed}s"
    printf -v total "%$(($2-elapsed))s"

    printf '%s\r' "[${prog// /-}${total}]"
}
```

**示例用法:**

```shell
for ((i=0;i<=100;i++)); do
    # 纯粹的暂停动作 (为了本例可以更好的演示).
    (:;:) && (:;:) && (:;:) && (:;:) && (:;:)

    # Print the bar.
    bar "$i" "10"
done

printf '\n'
```

## 获取脚本中的函数列表

```sh
get_functions() {
    # Usage: get_functions
    IFS=$'\n' read -d "" -ra functions < <(declare -F)
    printf '%s\n' "${functions[@]//declare -f }"
}
```

## 绕过shell别名

```shell
# alias
ls

# command
# shellcheck disable=SC1001
\ls
```

## 绕过shell函数

```shell
# function
ls

# command
command ls
```

- command命令  调用指定的指令并执行，命令执行时不查询shell函数。command命令只能够执行shell内部的命令。

## 在后台运行命令

这将运行给定命令并使其保持后台运行，即使终端或SSH连接中断后也是如此。但是会忽略所有输出。


```sh
bkr() {
    (nohup "$@" &>/dev/null &)
}

bkr ./some_script.sh
```

<!-- CHAPTER END -->

# 后记

感谢各位的阅读，如果对语法有啥疑问或者文章中有错误的地方，请及时告知，谢谢！


Rock on. 🤘
