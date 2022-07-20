# CSS 文本和字体属性、列表属性

## 常用文本样式属性

> color英文单词表示法
> color十六进制表示法
> colorrgb() 表示法
> color rgba() 表示法
> font-size字体大小
> font-weight 字体粗细程度
> font-style字体倾斜
> text-decoration文本修饰线

### font-size 属性，字体大小

> font-size 属性用来设置文字的字体字号大小，单位通常为 px（像素）、%百分比
> 
> 移动端还会学习 em、rem、vw、vh 单位
> 
> 网页文字正文字号通常是 16px
> 
> 浏览器最小支持 12px 字号，当字体小于 12px，默认都会以 12px 大小显示
> 
> 百分比相对于父元素的 font-size 大小而言

### font-weight 属性

> font-weight 属性设置字体的粗细程度
> 
> 通常用 normal 和 bold 两个值，或其对应数字 400 与 700 来表示
> 
> normal	正常粗细，与 400 等值
> 
> bold	加粗，与 700 等值
> 
> lighter	更细，大多数中文字体不支持。比从父元素继承来的值更细 
> 
> bolder	更粗，大多数中文字体不支持。比从父元素继承来的值更粗

### font-style 属性

> font-style 属性设置字体的倾斜
> normal	取消倾斜，如：把天生倾斜的 i、em 等标签设置为 不倾斜
> italic	设置为倾斜字体（常用）
> oblique 设置为倾斜字体 (不常用)

### @font-face 自定义字体

> 设置用户电脑中没有的字体,用户在浏览网页时就会下载相关字体，然后显示字体效果。
> 
> 字体文件根据操作系统和浏览器不同，有 eot、woff2、woff、ttf、svg 文件格式，需要同时有这 5 种文件
> 用 @font-face 定义字体
> 免费商用字体网站： [https://www.iconfont.cn/webfont](https://www.iconfont.cn/webfont)

```html
 <style>
      /* 第一步：使用font-face声明字体 */
      @font-face {
        font-family: "webfont";
        font-display: swap;
        src: url("./fontweb/webfont.eot"); /* IE9 */
        src: url("./fontweb/webfont.eot?#iefix") format("embedded-opentype"),
          /* IE6-IE8 */ url("./fontweb/webfont.woff2") format("woff2"),
          url("./fontweb/webfont.woff") format("woff"),
          /* chrome、firefox */ url("./fontweb/webfont.ttf") format("truetype"),
          /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
            url("./fontweb/webfont.svg#webfont") format("svg"); /* iOS 4.1- */
      }
      /* 第二步：定义使用 webfont 的样式  */
      .web-font {
        font-family: "webfont" !important;
        font-size: 16px;
        font-style: normal;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
      }
    </style>
  </head>
  <body>
    <!-- 第三步：为文字加上对应的样式 -->
    <p class="web-font">今天也是快乐的一天</p>
  </body>
```

## CSS 文本属性

> 修饰线，首行缩进，行高，font 属性复合写法，内容水平居中，字间距，字符间距

### text-decoration 属性 - 修饰线

> 修饰线
>用于设置文本的修饰线外观的（下划线、上划线、贯穿线/删除线 或 闪烁）
> 常用的属性值有以下三种
> > none	没有修饰线
> > underline	下划线
> line-through	删除线

### text-indent 属性 - 首行缩进

> 常用单位是em

### line-height 属性 - 行高

> line-height 属性定义行高
> 测量行高:
> > 从一行文字的最顶部到下一行文字的最顶部之间的距离，就是行高。
> 
> line-height 属性的单位可以是 px 
> 
> line-height 属性也可以是没有单位的数值，表示字号的倍数，这是最推荐的写法
> 实际工作中行高：1.25 , 1.5 , 1.75 都是常用的倍数设置
> > line-height:2;	行高为 font-size 的倍数，如果font-size:20px;则line-height:2;表示行高为 40px
> 
> line-height 属性也可以是百分数，表示字号的倍数
> > line-height:200%;	行高为 font-size 的百分比，如果font-size:20px，则line-height:40px;
> 
> line-height:normal;	取决于用户端。桌面浏览器（包括 Firefox）使用默认值，约为1.2，这取决于元素的 font-family。

### 行文本垂直、水平居中

> 行文本垂直居中
> 1、设置 行高 = 盒子高度 ，即可实现单行文本垂直居中
> 2、text-align 属性
> > 定义 行内内容（例如文字、图片、行内块级元素） 相对它的块父元素的对齐方式
> left 水平居左
> right 水平居右
> center 水平居中

### font 复合写法

> font 属性可以用来作为   font-style，font-weight ，font-size ，line-height 和 font-family 属性的合写
> font 属性连写时，必须设置 font-size 和 font-family 才能生效
> font-style和font-weight 必须在 font-size 之前

### 继承性

> 文字属性的继承性和就近原则
> 继承性:祖先元素设置，后代元素即生效
> 在继承的情况下，选择器权重计算失效，而不是就近原则
> 继承的选择器，权重可以看做是0，权重绝对没有选中的大
> 在继承的情况下，选择器权重计算失效，而是就近原则
> 
### word-spacing 字间距

> word-spacing 表示字间距，只对英文字单词起作用
> normal	正常的单词间距，由当前字体和/或浏览器定义。
> 长度	通过指定具体的额外间距来增加字体的单词间距

### letter-spacing 字符间距

> letter-spacing 属性用于设置文本字符的间距表现。
> normal	此间距是按照当前字体的正常间距确定的
> 长度	指定文字间的间距以替代默认间距。可以是负值 如-10px

## 列表样式

### list-style-type
> list-style-type 属性设置列表项标记的类型,只需要掌握如何去掉标记就好，去掉标记代码 list-style-type:none;