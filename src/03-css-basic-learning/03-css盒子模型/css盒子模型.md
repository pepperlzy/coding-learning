# css盒子模型

## 网页的本质

> 网页的本质是由一个个矩形框拼凑成的，矩形里放置了相关的图片、文字等内容。
> 而这种矩形框就称为盒子模型。

## 盒子模型简介

> 所有 HTML 标签都可以看成矩形盒子，具有 （盒子模型） 结构。

### 盒子模型的4部分组成

>  content(width 和 height属性组成的矩形部分)、padding、border、margin

### 盒子模型5个属性

> width 宽 、height 高 、border 边框 、padding 内边距 、margin 外边距
>
> 且盒子总宽度不是width和height组成的。

####  width 属性

> 当块级元素（div、h 系列、li 系列）没有设置 width 属性时，它将自动撑满，但并不意味着 width 可以继承.

####  height 属性

> 当块级元素盒子的 height 属性如果不设置，它将自动被其内容撑开
如果没有内容，则 height 默认是 0

#### 内联元素宽高

> 内联元素（如：a，span，b，strong ......）的宽高是由其内容决定，如果内容为空，则宽高默认为 0
内联元素设置宽高属性无效

#### border 属性 - 边框

> 常用边框主要有solid	实线、dashed	虚线、dotted	点状线、double	双边框

##### 边框的三要素小属性

> border-width 线宽
> border-style	线型
> border-color	线颜色
> 作用： 为了层叠大属性用的

#### 四个方向的边框

> border-top	上边框
> border-right	右边框
> border-bottom	下边框
> border-left	左边框
> 单独去掉某一边框线 border-top、border-bottom、border-right、border-left 的属性值设为 none 

##### 四个方向的边框的三要素小属性

#### 圆角 border-radius 属性

> border-radius 属性的值通常为 px单位 ，表示圆角的半径
> 小属性
> > border-top-left-radius	左上角
> > border-top-right-radius	右上角
> > border-bottom-left-radius	左下角
> > border-bottom-right-radius	右下角

> border-radius 属性的值也可以用百分比做单位，表示圆角起始于每条边的哪里
> 正方形盒子 设置border-radius: 50%; 为正圆形
> 长方形盒子 设置 border-radius: 50%; 为椭圆形，不能用 px 为单位

#### padding 的四数值写法

##### 内边距

> padding: 上 右 下 左;

```html
 .b1 {
      padding: 10px 20px 30px 40px;
    }
```
> padding: 上 左右 下;
> 
```html
.b2 {
      padding: 10px 20px 30px;
    }
```

> padding: 上下 左右;

```html
.b3 {
      padding: 10px 20px;
    }
```

>上右下左内边距都是10px 

```html
 .b4 {
      padding: 10px;
    }
```

####  padding 属性应用场景

> 设置父子间间距，即给父元素添加内边距来实现
> padding 大小属性的最佳实践：小属性层叠大属性

#### margin 属性 - 外边距

> margin 是盒子的外边距，表示盒子和其他盒子之间的距离

> margin-top	上外边距
> margin-right	右外边距
> margin-bottom	下外边距
> margin-left	左外边距

> margin 的不同数值写法与padding相同

##### margin 的塌陷

> margin 塌陷也叫：外间距重叠 或 外边距合并 或 外边距穿透,但margin 在水平方向：不会塌陷
> 
>  兄弟元素之间 ，垂直方向：上下外边距出现塌陷
> > 垂直方向的 margin 有塌陷现象，第一个元素的下外边距与第二个元素的上外边距会发生合并
> 小的 margin 会塌陷到大的 margin 中，从而 margin 不叠加，只以大值为准

> 解决方法
> > 任何一个元素加上 display:inline-block;
> > 把外边距只加在其中一个元素上
> > 任意一个元素外边距换成对应的 padding

> 父子元素之间，垂直方向：上外边距塌陷
> 当一个元素包含在另一个元素中时，如果父元素没有设置内边距或边框把外边距分隔开，它们的上外边距也会发生塌陷（合并）
> 
> 穿透了父元素，并与父元素上外边距发生合并，合并后以最大的值为主。

#### 去掉元素的默认样式

> 网页中的元素为了展示元素本身的用途和结构，都会给元素添加默认的样式。而实际的网页开发中，要将这些默认的样式清除掉，也称之为 "CSS 样式的初始化"。
> `*` 通配符选择器，表示选择所有元素 （通配符有效率问题，实际工作中不使用）

#### 盒子的水平居中

```html
/* 方式一， margin: 上下0 ，左右自动 */
 margin: 0 auto;
```
### 盒子模型占位计算

>  盒模型的内容区大小
> > 在标准盒子模型中,就是盒子里面能留给子元素的宽度和高度大小.
> > 当只有一个子元素，子元素的宽度超过父元素，就会溢出
> > 如果有多个子元素，子元素（行内元素，行内块元素）的宽度加起来超过了父元素，超过的那些子元会换行显示

#### 盒模型可视宽高

> 可视区宽 = 宽度 + 左右内边距 + 左右边框宽
> 可视区高 = 高度 + 上下内边距 + 上下边框宽

#### 盒模型实际占位宽度

> 实际占位宽 = 宽度 + 左右内边距 + 左右边框宽 + 左右外边距
> 实际占位高 = 高度 + 上下内边距 + 上下边框宽 + 上下外边距

### box-sizing 怪异盒模型

> CSS3 中新增了怪异盒子模型（IE 盒子模型）
> 将盒子添加 box-sizing: border-box;属性， 盒子的 width、height表示盒子实际占有的宽度 ,padding、border 不再增加大小。
>  大量应用于移动网页制作中，属性兼容到 IE9。
> > width = border + padding + 内容的宽度
> > height = border + padding + 内容的高度
> 
> 盒模型转换 
> > 标准盒模型box-sizing：content-box 
> > 怪异盒模型 box-sizing: border-box

### div 和 button 按钮的大小区别

> button 按钮默认是 怪异盒模型
> div是标准盒模型