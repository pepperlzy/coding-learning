# markdown基础语法学习<br>
## 一、标题描述方式(以#个数代表标题级别注意#后面要有空格)

# 标题基本1
## 标题级别2
### 标题级别3
#### 标题级别4
##### 标题级别5
###### 标题级别6

一级标题替代语法

Heading level 1
==

二级标题替代语法

Heading level 2
--

## 二、段落

创建段落时，用空行分隔一行或所行的文本

&nbsp;&nbsp;&nbsp;&nbsp;今天天气十分炎热，今天天气十分炎热，今天天气十分炎热

使用Markdown的第一天，了解了许多有关软件的使用方法及使用场景。()

## 三、换行符

通过`（<br>）`或者以两个或多个空格结束一行
This is the first line.<br>And this is the second line.

## 四、强调（文本加粗或者斜体）

我只是喜欢 **粗体** 字。<br>
我只是喜欢 __粗体__ 字。

*斜体*字<br>
_斜体_ 字

## 五、块引用

>在段落前添加一个大于符号

带有多个段落的大引号如：
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood

## 六、嵌套块引用

块引用可以嵌套。>>在要嵌套的段落前面添加一个。

> 多萝西跟着她穿过了她城堡里许多漂亮的房间。
>
>> 多萝西跟着她穿过了她城堡里许多漂亮的房间。

## 七、带有其他元素的块引用

> ## 季度业绩看起来很棒！
> 
> - 收入不在图表之列。
> - 利润比以往任何时候都高。
> 
> *一切* 都在按 **计划** 进行。

## 八、列表

### （一）有序列表
要创建有序列表，请添加带有数字后跟句点的行项目。数字不必按数字顺序排列，但列表应以数字一开头。

#### 方式1
1. 有序列表1
2. 有序列表2
3. 有序列表3
4. 有序列表4  

#### 方式2：
1. 有序列表1
2. 有序列表2
   1. 缩进有序列表1
   2. 缩进有序列表2
3. 有序列表3

### （二）、无序列表

 - 无线列表1
 - 无线列表1
   - 无线列表1
      - 无线列表1
      - 无线列表2
   - 无线列表2
 - 无线列表3
  
## 八、代码块

通常缩进四个空格或一个置位符，在列表项中缩进八个空格或两个制表符

1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website. 
         
        <html>
            <head>
               <title>Test</title>
            </head>
        </html>

## 九、图片

`![picture](相对路径)`

![picture](./src/01-Markdown-learning/image/pic.jpg)

## 十、代码

要将单词或短语表示为代码时，将其括在反引号 ( `)中

在命令提示符处，输入(`img`)

## 十一、水平规则

（一）用`***`表示水平线

***

（二）、破折号 `---`

---

（三）、下划线`___`

___

## 十二、链接

`[aaa](网址)`<br>
进入百度搜索 [go to baidu](http://www.baidu.com)

## 十三、URL 和电子邮件地址

要将 URL 或电子邮件地址快速转换为链接，请将其括在尖括号中。

<https://www.markdownguide.org> <br>
<fake@example.com>>

## 十四、格式化链接

要强调链接，请在方括号和圆括号前后添加星号。要将链接表示为code，请在括号中添加反引号。

I love supporting the **[EFF](https://eff.org)**.

This is the *[Markdown Guide](https://www.markdownguide.org)*.

See the section on [`code`](#code).

## 十五、转义字符

要显示原本用于在 Markdown 文档中格式化文本的文字字符，\在字符前面添加反斜杠。

\* 要显示原本用于在 Markdown 文档中格式化文本的文字字符。

## 十六、表格

| 语法      | 描述 |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

对齐方式

| 语法      | 描述 | 文本     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

### 十七、围栏代码块

使用三个反引号 ( ```) 或三个波浪号 ( )

```
{
    "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

~~~
{
    "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
~~~

## 十八、语法高亮

```html
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

```python
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

## 十九、脚注

这是一个简单的脚注 [^1]

## 删除线

~~ 世界是平的 ~~。我们现在知道世界是圆的。(`~~ ~~`)

## 二十、任务列表


`- [x] Write the press release` <br>
`- [ ] Update the website` <br>
`- [ ] Contact the media `<br>

输出渲染：

- [x] Write the press release
- [x] Update the website
- [ ] Contact the media

## 二十一、Emoji

通过输入表情符号短代码来插入表情符号。这些以冒号开头和结尾，并包含表情符号的名称。

Gone camping! :tent: Be back soon.

## 二十二、强调

在单词前后使用两个等号 `==aaa==`

我需要 ==强调== 这些很重要的话.

