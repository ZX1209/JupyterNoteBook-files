[TOC]





# python3 字符串 笔记

## 创建,初始化

### '单引号创建,无转义'

### "双引号创建,可以有单引号,可以转义"

#### 转义参考

在需要在字符中使用特殊字符时，python用反斜杠(\)转义字符。如下表：

| 转义字符    | 描述                                         |
| ----------- | -------------------------------------------- |
| \(在行尾时) | 续行符                                       |
| \\          | 反斜杠符号                                   |
| \'          | 单引号                                       |
| \"          | 双引号                                       |
| \a          | 响铃                                         |
| \b          | 退格(Backspace)                              |
| \e          | 转义                                         |
| \000        | 空                                           |
| \n          | 换行                                         |
| \v          | 纵向制表符                                   |
| \t          | 横向制表符                                   |
| \r          | 回车                                         |
| \f          | 换页                                         |
| \oyy        | 八进制数，yy代表的字符，例如：\o12代表换行   |
| \xyy        | 十六进制数，yy代表的字符，例如：\x0a代表换行 |
| \other      | 其它的字符以普通格式输出                     |

#### 终端控制符

**书写格式：**     **开头部分**：\033[显示方式;前景色;背景色m + **结尾部分：**\033[0m

​     注意：开头部分的三个参数：显示方式，前景色，背景色是可选参数，可以只写其中的某一个；另外由于表示三个参数不同含义的数值都是唯一的没有重复的，所以三个参数的书写先后顺序没有固定要求，系统都能识别；但是，建议按照默认的格式规范书写。

​     对于结尾部分，其实也可以省略，但是为了书写规范，建议\033[***开头，\033[0m结尾。

 

**数值表示的参数含义：**

**显示方式:** 0（默认\）、1（高亮）、22（非粗体）、4（下划线）、24（非下划线）、 5（闪烁）、25（非闪烁）、7（反显）、27（非反显）



**前景色:**   30（黑色）、31（红色）、32（绿色）、 33（黄色）、34（蓝色）、35（洋 红）、36（青色）、37（白色）



**背景色:**  40（黑色）、41（红色）、42（绿色）、 43（黄色）、44（蓝色）、45（洋 红）、46（青色）、47（白色）



### 三引号 多行字符串

### r 前缀 原始字符串 忽略所有转义字符



## 访问

### 下标

str[1]

### 切片

str[3:4]

## 更新

赋值

或

切片连接..

## in 和 not in 运算

'cats' in 'cats and dogs'

true



## 字符串运算符

下表实例变量a值为字符串 "Hello"，b变量值为 "Python"：

| 操作符 | 描述                                                         | 实例                           |
| ------ | ------------------------------------------------------------ | ------------------------------ |
| +      | 字符串连接                                                   | a + b 输出结果： HelloPython   |
| *      | 重复输出字符串                                               | a*2 输出结果：HelloHello       |
| []     | 通过索引获取字符串中字符                                     | a[1] 输出结果 **e**            |
| [ : ]  | 截取字符串中的一部分                                         | a[1:4] 输出结果 **ell**        |
| in     | 成员运算符 - 如果字符串中包含给定的字符返回 True             | **'H' in a** 输出结果 1        |
| not in | 成员运算符 - 如果字符串中不包含给定的字符返回 True           | **'M' not in a** 输出结果 1    |
| r/R    | 原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母 r（可以大小写）以外，与普通字符串有着几乎完全相同的语法。 | `print( r'\n' )print( R'\n' )` |
| %      | 格式字符串                                                   | 与C语言中的printf系类相似      |



## 格式化字符串

```python
tmp_str = 'string'
print("this is a test for %d and %s" %(1,tmp_str))
```



## 字符串方法

### 常用方法

#### replace()

#### upper(),lower() 返回一个相应变化的字符串(isupper(),islower())

#### join() 

join(seq)  以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串

#### split()

#### rjust(),ljust(),center()  对齐本

第一个参数是一个整数长度..用于对齐字符串

第二个参数可以指定填充字符 默认是空格

#### strip(),lstrip(),rstrip() 删除空白字符(左右,left,right)

#### startswith(),endswith()

### 符串方法参考

Python 的字符串常用内建函数如下：

| 序号 | 方法及描述                                                   |
| ---- | ------------------------------------------------------------ |
| 1    | [capitalize()](http://www.runoob.com/python3/python3-string-capitalize.html)将字符串的第一个字符转换为大写 |
| 2    | [center(width, fillchar)](http://www.runoob.com/python3/python3-string-center.html)返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。 |
| 3    | [count(str, beg= 0,end=len(string))](http://www.runoob.com/python3/python3-string-count.html)返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数 |
| 4    | [bytes.decode(encoding="utf-8", errors="strict")](http://www.runoob.com/python3/python3-string-decode.html)Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。 |
| 5    | [encode(encoding='UTF-8',errors='strict')](http://www.runoob.com/python3/python3-string-encode.html)以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace' |
| 6    | [endswith(suffix, beg=0, end=len(string))](http://www.runoob.com/python3/python3-string-endswith.html)检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False. |
| 7    | [expandtabs(tabsize=8)](http://www.runoob.com/python3/python3-string-expandtabs.html)把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。 |
| 8    | [find(str, beg=0 end=len(string))](http://www.runoob.com/python3/python3-string-find.html)检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1 |
| 9    | [index(str, beg=0, end=len(string))](http://www.runoob.com/python3/python3-string-index.html)跟find()方法一样，只不过如果str不在字符串中会报一个异常. |
| 10   | [isalnum()](http://www.runoob.com/python3/python3-string-isalnum.html)如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True,否则返回 False |
| 11   | [isalpha()](http://www.runoob.com/python3/python3-string-isalpha.html)如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False |
| 12   | [isdigit()](http://www.runoob.com/python3/python3-string-isdigit.html)如果字符串只包含数字则返回 True 否则返回 False.. |
| 13   | [islower()](http://www.runoob.com/python3/python3-string-islower.html)如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False |
| 14   | [isnumeric()](http://www.runoob.com/python3/python3-string-isnumeric.html)如果字符串中只包含数字字符，则返回 True，否则返回 False |
| 15   | [isspace()](http://www.runoob.com/python3/python3-string-isspace.html)如果字符串中只包含空白，则返回 True，否则返回 False. |
| 16   | [istitle()](http://www.runoob.com/python3/python3-string-istitle.html)如果字符串是标题化的(见 title())则返回 True，否则返回 False |
| 17   | [isupper()](http://www.runoob.com/python3/python3-string-isupper.html)如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False |
| 18   | [join(seq)](http://www.runoob.com/python3/python3-string-join.html)以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串 |
| 19   | [len(string)](http://www.runoob.com/python3/python3-string-len.html)返回字符串长度 |
| 20   | [ljust(width[, fillchar\])](http://www.runoob.com/python3/python3-string-ljust.html)返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。 |
| 21   | [lower()](http://www.runoob.com/python3/python3-string-lower.html)转换字符串中所有大写字符为小写. |
| 22   | [lstrip()](http://www.runoob.com/python3/python3-string-lstrip.html)截掉字符串左边的空格或指定字符。 |
| 23   | [maketrans()](http://www.runoob.com/python3/python3-string-maketrans.html)创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。 |
| 24   | [max(str)](http://www.runoob.com/python3/python3-string-max.html)返回字符串 str 中最大的字母。 |
| 25   | [min(str)](http://www.runoob.com/python3/python3-string-min.html)返回字符串 str 中最小的字母。 |
| 26   | [replace(old, new [, max\])](http://www.runoob.com/python3/python3-string-replace.html)把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。 |
| 27   | [rfind(str, beg=0,end=len(string))](http://www.runoob.com/python3/python3-string-rfind.html)类似于 find()函数，不过是从右边开始查找. |
| 28   | [rindex( str, beg=0, end=len(string))](http://www.runoob.com/python3/python3-string-rindex.html)类似于 index()，不过是从右边开始. |
| 29   | [rjust(width,[, fillchar\])](http://www.runoob.com/python3/python3-string-rjust.html)返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串 |
| 30   | [rstrip()](http://www.runoob.com/python3/python3-string-rstrip.html)删除字符串字符串末尾的空格. |
| 31   | [split(str="", num=string.count(str))](http://www.runoob.com/python3/python3-string-split.html)num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num 个子字符串 |
| 32   | [splitlines([keepends\])](http://www.runoob.com/python3/python3-string-splitlines.html)按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。 |
| 33   | [startswith(str, beg=0,end=len(string))](http://www.runoob.com/python3/python3-string-startswith.html)检查字符串是否是以 obj 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。 |
| 34   | [strip([chars\])](http://www.runoob.com/python3/python3-string-strip.html)在字符串上执行 lstrip()和 rstrip() |
| 35   | [swapcase()](http://www.runoob.com/python3/python3-string-swapcase.html)将字符串中大写转换为小写，小写转换为大写 |
| 36   | [title()](http://www.runoob.com/python3/python3-string-title.html)返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle()) |
| 37   | [translate(table, deletechars="")](http://www.runoob.com/python3/python3-string-translate.html)根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中 |
| 38   | [upper()](http://www.runoob.com/python3/python3-string-upper.html)转换字符串中的小写字母为大写 |
| 39   | [zfill (width)](http://www.runoob.com/python3/python3-string-zfill.html)返回长度为 width 的字符串，原字符串右对齐，前面填充0 |
| 40   | [isdecimal()](http://www.runoob.com/python3/python3-string-isdecimal.html)检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。 |



## pyperclip 模块拷贝粘贴字符串

### 常用方法

#### copy() 将文本复制到系统粘贴板

#### paste() 每次调用,返回系统粘贴板数据(仅文本)



