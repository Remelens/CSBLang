# CSBLang
A runtme program for https://github.com/Hiyoteam/SBLang

# Docs

>A little different from [https://github.com/Hiyoteam/SBLang](https://github.com/Hiyoteam/SBLang)

----------

>能够摧毁脑细胞制造脑内BUG的“高”智商编程语言，如果您非常闲，强烈建议您试试。


## 注释
### 简介
注释只能在新的一行，由#开始。
### 用法
`#<注释内容>`
### 示例
```sblang
#这是一句注释

#这也是一句注释
#对，这还是注释
```
## new
### 简介
新建单个/多个变量。
### 用法
`new <单个变量名或用英文逗号分隔的变量名列表>`
### 示例
以下代码用来创建fo,foo,bar,buf四个变量。
```sblang
new fo
new foo,bar,buf
```
## string*
### 简介
将一个字符串赋值到变量。
### 用法
`string <变量名> <字符串>`
### 示例
以下代码用来给a赋值"Hello world",给b赋值"SBLang is awesome".
```sblang
new a,b
string a "Hello world"
string b "SBLang is awesome"
```
## addkeep
### 简介
向变量添加保留字符串。  
目前支持的保留字符串有:
 - newline(\n)

### 用法
`addkeep <保留字符串名> <变量名>`
### 示例
以下代码用于给变量a赋值"hello world"并换行。
```sblang
new a
string a Hello world!
addkeep newline a
```

## appendvar
### 简介
将第二个变量的字符串与第一个变量拼接。
### 用法
`appendvar <变量1> <变量2>`
### 示例
```sblang
new a,b
string a foo
string b bar
appendvar a b
```
内存断点:`{"a":"foobar","b":"bar"}`

## out*
### 简介
将变量的内容输入到stdout.
### 用法
`out <变量名/字符串>`
### 示例
```sblang
new a
string a "Hello,world!"
addkeep newline a
out a
```
或
```sblang
out "Hello,world!"
```
输出:`Hello,world!`

## getchar
### 简介
从stdin获得输入，直到用户按下Enter，并将获得的内容写入变量。
### 用法
`getchar <变量名>`
### 示例
```sblang
new a,b,c,d
string a "What's your name?"
out a
getchar b
string c Hello,
string d !
appendvar c b
appendvar c d
addkeep newline c
out c
```
输出:`What's your name?`  
输入:`小明`  
输出:`Hello,小明!`  

## define/d
### 简介
定义函数。
### 用法
`define 函数名`
`d 函数单行内容`
`d end`
### 示例
```sblang
define get
d new data
d out content
d getchar data
d end
new content,a
string content 你叫什么名字：
call get
string a 你好，
out a
out data
string a !
addkeep newline a
out a
```
输出：`你叫什么名字：`
输入：`John Doe`
输出：`你好，John Doe!`
