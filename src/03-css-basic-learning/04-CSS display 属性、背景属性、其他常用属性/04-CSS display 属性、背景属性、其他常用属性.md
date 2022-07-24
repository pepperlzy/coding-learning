# CSS display 属性、背景属性、其他常用属性

## 一、display 属性

> display 属性的作用:块级元素、行内元素、行内块级元素互相转换。
> 
> display：block 块级元素
> display：inline-block 行内块元素
> display：inline 内联（行内）元素
> >  行内元素特点：
> >   1、并排显示，默认从左至右布局
> >   2、不可以设置宽高
>  >  3、其宽高随其内容大小而撑开  
> 

### 三种元素类型对比

|元素类型 |排列方式 | 盒模型属性|内容|
| :---: | :---: | :---: | :---: |
|块级(block)|独占一行|可设置width、height|任意元素|
|行内块(inline-block)|一行可显示多个|可设置width、height|行内或行内块元素|
|内联（inline）|	一行可显示多个|	width、height 无效	|行内或文本元素|

### 隐藏元素方法

> display:none; 隐藏元素 可以将元素隐藏，子孙元素全部隐藏不可见。并且只要父元素隐藏，子孙没有任何办法可见。元素隐藏后**不会占空间**。就像页面当中就没有这个元素一样。
> 
> visibility:hidden; 隐藏元素 将元素隐藏，子孙元素全部不可见，但是给子孙加上 visibility: visible;时，子孙可见。隐藏后仍占其位置，会留下空白的一块区域。基本不用。

### display:none; 与 visibility:hidden; 两者的区别 ？

|区别|display: none|visibility: hidden|
|:---:|:---:|:---:|
| 空间占据性 |不占据空间| 占据原空间|
| 回流与渲染性| 会产生回流与重绘| 不会产生回流，只会产生重绘|
|子元素影响|子孙元素全部隐藏不可见。并且只要父元素隐藏，子孙没有任何办法可见|子孙元素全部不可见，但是给子孙加上 visibility: visible;时，子孙可见。|

### 去掉行内块元素默认的空白间隙三种方法

> 给父元素添加 font-size: 0px; 同时子元素重写 font-size
> 
> 给元素添加 float
> 
> 图片间空隙，给图片添加 display:block;

## background 背景属性

#### background-color 背景颜色
```html
background-color: rgb(87, 126, 255);
```
#### background-image 图片

```html
 background-image: url(./images/pic2.jpg);
 ```

#### background-repeat 重复

> 用来设置背景图片的重复模式，在默认情况下，背景是会在 x 和 y 轴方向进行平铺。
> background-repeat 属性值
> > repeat;	x，y 均平铺 （默认）
> > repeat-x;	x 平铺
> > repeat-y;	y 平铺
> > no-repeat;	不平铺

#### background-position 背景图片位置

> 控制背景图片在盒子中显示的开始位置
> 背景图片位置默认是从 padding 区开始计算
> 数值表达法
> 
> > 1 固定值写法
```html
/* x与盒子左边距离  Y与盒子上边距离 */
      /* 数值表达法 */
 background-position: 20px 30px;
```

> >  单个值写法

```html
/* 表时背景图与盒子左边间距为宽的10px，垂方向居中显示 */
background-position: 50px;
```
> > 2 百分比写法
> >百分比写法 x% y% ，则最后的偏移量是
> > 左偏移量 =（容器width + 左右padding - 背景图width）* 百分比
> > 上偏移量 =（容器height +上下padding - 背景图height）* 百分比
> > 单个值写法
```html
 background-position: 10%;
      /* 左边距离为 : (200+50*2-100)*10=20
        上边距离为居中*/
```
> > 3 关键词表达法
> > （top、bottom）、（center）、（left、right） 三组中的任意两个组中的一个值组合来确定位置

#### background 复合属性

> 背景相关小属性，可以合写到一条 background 属性中
> background 是的 background-color、background-image、background-repeat、background-position 的简写

### CSS 精灵图

> 精灵图十将多个 小图标 合并制作到一张图片上,再使用background-position显示其中的图标
> 作用是：减少 HTTP 请求数，加快网页显示速度，但是不方便测量，后期改动麻烦

### background-attachment 背景固定

> 决定背景图像的位置是在 视口 内固定，或者随着包含它的区块滚动
> scroll	默认值。背景图片随着页面的滚动而滚动，相对于元素本身固定，而不是随着它的内容滚动
> fixed	表示背景相对于视口固定。即使一个元素拥有滚动机制，背景也不会随着元素的内容滚动
> local	背景相对于元素的内容固定。如果一个元素拥有滚动机制，背景将会随着元素的内容滚动，同时背景图图片随着页面的滚动而滚动

### background-size 背景尺寸

> x y	x y 数值，分别表示背景图片宽高大小
> x% y%	百分比是相对于盒子的宽高而言
> x auto	auto 是相对于第一个值宽来自动缩放且第一个值可以是数值，也可以是百分形式
> contain	背景图片智能改变尺寸以容纳到盒子里
> cover	背景图片撑满盒子

```html
.box {
      width: 400px;
      height: 300px;
      margin-top: 10px;
      border: 1px solid rgb(163, 51, 255);
    }
    .b1 {
      background: url(./images/pic4.png) no-repeat;
      background-size: 100px 70px;
    }
    .b2 {
      background: url(./images/pic4.png) no-repeat;
      background-size: 80% 70%;
    }
    .b3 {
      background: url(./images/pic4.png) no-repeat;
      background-size: 50% auto;
    }
    .b4 {
      background: url(./images/pic4.png) no-repeat;
      background-size: contain;
    }
    /* 铺满整个盒子 */
    .b5 {
      background: url(./images/pic4.png) no-repeat;
      background-size: cover;
    }
```

### 线性渐变

> 转换中点
>
> 从一个颜色的终止点平滑的过渡到另一个颜色的终止点，颜色之间的中点是两个颜色转换的中点

```html
background-image: linear-gradient(direction, color-stop1, color-stop2, ...);
```

> direction 通过角度值指定渐变的方向（或角度）。默认为 180deg（从上到下）设置了角度，则 0deg 为竖直向上，然后顺时针旋转指定关键词 to right、to top、to bottom 、to bottom right 等
> color-stop1, color-stop2,...	用于指定渐变的起止颜色。

```html
<style>
      .box {
        width: 400px;
        height: 300px;
        margin-top: 10px;
        border: 1px solid rgb(163, 51, 255);
      }
      /* 未设置角度，则默认从上向下渐变 */
      .b1 {
        background-image: linear-gradient(
          rgba(255, 0, 0, 0.718),
          rgba(255, 255, 0, 0.68),
          rgba(0, 128, 0, 0.777)
        );
      }
      /* 关键字来指定渐变的方向 */
      .b2 {
        background-image: linear-gradient(
          to right,
          rgba(255, 0, 0, 0.718),
          rgba(255, 255, 0, 0.68),
          rgba(0, 128, 0, 0.777)
        );
      }
      .b3 {
        background-image: linear-gradient(
          to top,
          rgba(255, 0, 0, 0.718),
          rgba(255, 255, 0, 0.68),
          rgba(0, 128, 0, 0.777)
        );
      }
      .b4 {
        background-image: linear-gradient(
          /* to top right, */ to top left,
          rgba(255, 0, 0, 0.718),
          rgba(255, 255, 0, 0.68),
          rgba(0, 128, 0, 0.777)
        );
      }
      /* 用度数来指定渐变方向 */
      .b5 {
        background-image: linear-gradient(
          /* 45deg, */ 85deg,
          rgba(255, 0, 0, 0.718),
          rgba(255, 255, 0, 0.68),
          rgba(0, 225, 255, 0.777)
        );
      }
      /* 多个颜色值，并且可以用百分数定义它出现的位置 */
      .b6 {
        background-image: linear-gradient(
          to right,
          rgba(0, 251, 255, 0.563) 10%,
          rgba(140, 0, 255, 0.68) 40%,
          rgba(0, 89, 255, 0.777) 100%
        );
      }
    </style>
```

> 渐变颜色工具[https://c.runoob.com/more/gradients/#Kashmir](https://c.runoob.com/more/gradients/#Kashmir)

### 径向渐变

>background-image:radial-gradient() 创建径向渐变背景图
> 径向渐变:由其**中心点*、*边缘形状轮廓、两个或多个色值结束点（color stops）**定义而成。
```html
background-image: radial-gradient(
  shape size at position,
  start-color,
  ...,
  last-color
);
```

> shape 确定圆的类型 ellipse(默认),椭圆形渐变。
> 
> circle ：圆形的径向渐变
> > farthest-corner :指定径向渐变的半径长度为从圆心到离圆心**最远的角**
> > closest-side ：指定径向渐变的半径长度为从圆心到离圆心**最近**的边
> > closest-corner ：指定径向渐变的半径长度为从圆心到离圆心**最近的角**
> > farthest-side ：指定径向渐变的半径长度为从圆心到离圆心**最远的边**
> 
> position 定义渐变的位置
> > center（默认）未定义位置时，默认以元素中心位置为起点
> > top：设置顶部为径向渐变圆心的纵坐标值。
> > bottom：设置底部为径向渐变圆心的纵坐标值。
> > start-color, ..., last-color	用于指定渐变的起止颜色

```html
<style>
    .box {
      width: 400px;
      height: 300px;
      margin-top: 10px;
      border: 1px solid rgb(163, 51, 255);
    }
    .b1 {
      /* 未定义位置时，默认以元素中心位置为起点
        未定义渐变类型，默认是以椭圆形的径向渐变 */
      background-image: radial-gradient(red, rgb(255, 187, 0), rgb(31, 205, 0));
    }
    .b2 {
      background-image: radial-gradient(
        /* 10%代表红色起始点 */ red 10%,
        rgb(255, 187, 0) 80%,
        rgba(0, 0, 255, 0.551)
      );
    }
    .b3 {
      background-image: radial-gradient(
        /* 10%代表红色起始点
        第二个10%代表红色与黄色的转换中点   */ red
          10%,
        10%,
        rgb(255, 187, 0) 80%,
        rgba(0, 0, 255, 0.551)
      );
    }
    /* 设置径向渐变的形状shape为圆形 */
    .b4 {
      background-image: radial-gradient(
        /* 10%代表红色起始点
        第二个10%代表红色与黄色的转换中点   */
          circle,
        red 10%,
        rgb(255, 187, 0) 80%,
        rgba(0, 0, 255, 0.551)
      );
    }

    .b5 {
      background-image: radial-gradient(
        /* at 100px 100px代表径向渐变的中心点 */ at 50px 50px,
        red 10%,
        10%,
        rgb(255, 187, 0) 80%,
        rgba(0, 0, 255, 0.551)
      );
    }
    /* closest-side 最近的边 50px 20px为径向椭圆的中心点*/
    .b6 {
      background-image: radial-gradient(
        closest-side at 50px 20px,
        red 10%,
        10%,
        rgb(255, 187, 0),
        rgba(0, 0, 255, 0.551)
      );
    }

    .b7 {
      background-image: radial-gradient(
        farthest-side at 50px 20px,
        red 5%,
        5%,
        rgb(255, 187, 0),
        rgba(0, 0, 255, 0.551)
      );
    }
    /* closest-corner 最近的一个角相交 */
    .b8 {
      background-image: radial-gradient(
        closest-corner at 50px 20px,
        red 5%,
        5%,
        rgb(255, 187, 0),
        rgba(0, 0, 255, 0.551)
      );
    }
    /* farthest-corner 最远的一个角相交 */
    .b9 {
      background-image: radial-gradient(
        farthest-corner at 50px 20px,
        red 5%,
        5%,
        rgb(255, 187, 0),
        rgba(0, 0, 255, 0.551)
      );
    }
  </style>
  ```

## 其它常用属性

### cursor 鼠标样式

> 设置光标的类型，在鼠标指针悬停在元素上时显示相应样式

```html
html {
        cursor: url("http://127.0.0.1:5500/src/03-css-basic-learning/04-CSS%20display%20%E5%B1%9E%E6%80%A7%E3%80%81%E8%83%8C%E6%99%AF%E5%B1%9E%E6%80%A7%E3%80%81%E5%85%B6%E4%BB%96%E5%B8%B8%E7%94%A8%E5%B1%9E%E6%80%A7/images/click1.png"),
          pointer;
      }
      a {
        text-decoration: none;
        cursor: crosshair;
        cursor: help;
      }
```
### overflow 超出部分隐藏

> overflow 属性规定当内容溢出元素框时该 做什么。
> visible	默认值。内容溢出，会呈现在元素框之外。
> hidden	内容溢出，溢出部分隐藏。
> scroll	不管内容是否溢出，都会显示滚动条。
> auto	内容溢出，则显示滚动条以便查看其余的内容。如果不溢出，则不显示滚动条
> inherit	规定应该从父元素继承 overflow 属性的值。

> overflow-x 和 overfow-y
> overflow-x 水平方溢出设置
> overflow-y 垂直方向溢出设置

### vertical-align 属性

> 指定行内元素 、行内块级元素 、表格单元格元素 的垂直对齐方式但对块级元素无效。

```html
<style>
      .box {
        height: 50px;
        float: left;
        color: white;
        margin: 10px 10px 10px 0px;
        background-color: rgb(162, 135, 235);
        /* 行高 50px */
        line-height: 50px;
      }
      .box span {
        /* 行内块 */
        display: inline-block;
        line-height: 1;
        background-color: rgb(0, 140, 255);
      }
      .baseline {
        /* 元素的基线与父元素的 基线对齐 */
        vertical-align: baseline;
      }
      .sub {
        /* 元素的基线与父元素的 下标基线对齐 */
        vertical-align: sub;
      }
      .super {
        /* 元素的基线与父元素的 上标基线对齐 */
        vertical-align: super;
      }
      .text-top {
        /* 元素的顶部与父元素的字体顶部对齐。 */
        vertical-align: text-top;
      }
      .text-bottom {
        /* 元素的底部与父元素的字体底部对齐。 */
        vertical-align: text-bottom;
      }
      .middle {
        /* 元素的中部与父元素的基线加上父元素 x-height(x 高度) 的一半对齐。 */
        vertical-align: middle;
      }
      .top10px {
        /* 元素的基线对齐到父元素的基线 之上的给定长度
可以是负数 */
        vertical-align: 10px;
      }
      .top10 {
        /* 元素的基线对齐到父元素的基线之上的给定百分比，该百分比是line-height (opens new window)属性的百分比 */
        vertical-align: 10%;
      }
      .top {
        /* 元素及其后代元素的顶部与整行的顶部对齐 */
        vertical-align: top;
      }
      .bottom {
        /* 元素及其后代元素的底部与整行的底部对齐 */
        vertical-align: bottom;
      }
    </style>
```

##### vertical-align 的应用场景

> 用于控制文字与行内块元素或图片在垂直方向上的对齐方式

```html
<style>
      h3 {
        height: 50px;
        background-color: #ddd;
        line-height: 50px;
      }
      .img {
        /* 元素的中线与x的中心对齐 */
        vertical-align: middle;
      }

      table {
        height: 100px;
      }
      table tr td {
        border: 1px solid #000;
      }
      .baseline {
        vertical-align: baseline;
      }
      .top {
        vertical-align: top;
      }
      .middle {
        vertical-align: middle;
      }
      .bottom {
        vertical-align: bottom;
      }
    </style>
  </head>
  <body>
    <h2>用于控制文字与行内块元素或图片在垂直方向上的对齐方式</h2>
    <h3><img src="images/click1.png" class="img" /> x今天天气十分晴朗</h3>
    <h2>用于设置表格单元中内容的垂直对齐方式</h2>
    <table>
      <tr>
        <td class="baseline">baseline</td>
        <td class="top">top</td>
        <td class="middle">middle</td>
        <td class="bottom">bottom</td>
      </tr>
    </table>
  </body>
  ```