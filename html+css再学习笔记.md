---
title: html+css再学习
date: 2022-8-19 13:26:00
tab: 
---

先html5再css3

- [1.html文件的基本元素结构](#1html文件的基本元素结构)
- [2.标签介绍](#2标签介绍)
  - [块级元素](#块级元素)
  - [行级元素](#行级元素)
  - [2.1.基础标签](#21基础标签)
    - [!DOCTYPE](#doctype)
    - [head](#head)
    - [body](#body)
    - [注释](#注释)
    - [title](#title)
    - [meta](#meta)
    - [base](#base)
    - [style](#style)
    - [script](#script)
    - [h1-h6](#h1-h6)
    - [hr](#hr)
    - [br](#br)
    - [p](#p)
  - [2.2.链接](#22链接)
    - [a](#a)
    - [link](#link)
  - [2.3.列表](#23列表)
    - [ul、ol、li](#ulolli)
    - [dl、dt、dd](#dldtdd)
  - [2.4.图片](#24图片)
    - [img](#img)
    - [picture](#picture)
    - [figure、figcaption](#figurefigcaption)
    - [map、area](#maparea)
  - [2.5.多媒体](#25多媒体)
    - [audio](#audio)
    - [vedio](#vedio)
  - [2.6.绘图](#26绘图)
    - [svg](#svg)
    - [canvas](#canvas)
  - [2.7.时间](#27时间)
    - [time](#time)
  - [2.8.表格](#28表格)
    - [table、tr、th、td](#tabletrthtd)
    - [caption](#caption)
    - [thead、tbody、tfoot](#theadtbodytfoot)
    - [colgroup、rolgroup](#colgrouprolgroup)
  - [2.9.表单](#29表单)
    - [form](#form)
    - [button](#button)
    - [input](#input)
      - [type属性：](#type属性)
    - [label](#label)
    - [fieldset](#fieldset)
    - [legend](#legend)
    - [select、option、optgroup](#selectoptionoptgroup)
    - [output](#output)
    - [textarea](#textarea)
  - [2.10.内联框架](#210内联框架)
    - [iframe](#iframe)
  - [2.11.格式](#211格式)
    - [strong与b](#strong与b)
    - [small](#small)
    - [em与i](#em与i)
    - [del与ins、s、u](#del与inssu)
    - [mark](#mark)
    - [wbr](#wbr)
    - [sup与sub](#sup与sub)
    - [abbr](#abbr)
    - [address](#address)
    - [q](#q)
    - [blockquote与cite](#blockquote与cite)
    - [dfn](#dfn)
    - [pre](#pre)
    - [code](#code)
    - [var](#var)
    - [kbd](#kbd)
    - [samp](#samp)
    - [ruby(非ruby语言)、rt、rp](#ruby非ruby语言rtrp)
    - [bdi](#bdi)
    - [bdo](#bdo)
    - [meter](#meter)
    - [progress](#progress)
  - [2.12.网页架构](#212网页架构)
    - [div](#div)
    - [span](#span)
    - [html5开始的布局用元素](#html5开始的布局用元素)
    - [header](#header)
    - [nav](#nav)
    - [main](#main)
    - [article](#article)
    - [section](#section)
    - [aside](#aside)
    - [footer](#footer)
    - [details、summary](#detailssummary)
    - [data](#data)
    - [dialog](#dialog)
  - [2.13.程序设计](#213程序设计)
    - [embed](#embed)
    - [noscript](#noscript)
    - [object](#object)
    - [param](#param)
    - [template](#template)
- [3.css简述](#3css简述)
- [4.选择器](#4选择器)
  - [4.1.基本选择器](#41基本选择器)
    - [*通用选择器](#通用选择器)
    - [元素选择器](#元素选择器)
    - [类选择器](#类选择器)
    - [id选择器](#id选择器)
  - [4.2.复合选择器](#42复合选择器)
    - [交集选择器](#交集选择器)
    - [并集选择器](#并集选择器)
    - [后代选择器](#后代选择器)
    - [子元素选择器](#子元素选择器)
    - [相邻兄弟选择器（同级元素）](#相邻兄弟选择器同级元素)
    - [通用兄弟选择器](#通用兄弟选择器)
  - [4.3.伪选择器](#43伪选择器)
    - [伪元素选择器](#伪元素选择器)
    - [伪类选择器](#伪类选择器)
      - [动态伪类选择器](#动态伪类选择器)
      - [UI伪类选择器](#ui伪类选择器)
      - [结构伪类选择器](#结构伪类选择器)
      - [其它伪类选择器](#其它伪类选择器)
  - [4.4.属性选择器](#44属性选择器)
- [5.属性](#5属性)
  - [5.1.颜色](#51颜色)
    - [color前景色](#color前景色)
    - [background背景](#background背景)
  - [5.2.border边框](#52border边框)
    - [boder-radius](#boder-radius)
    - [border-image图像边框](#border-image图像边框)
  - [5.3.组件外观](#53组件外观)
    - [margin/padding内外边距](#marginpadding内外边距)
    - [元素尺寸设置](#元素尺寸设置)
    - [outline轮廓](#outline轮廓)
    - [box-shadow阴影](#box-shadow阴影)
    - [display显示属性](#display显示属性)
    - [visibility](#visibility)
  - [5.4.文本样式](#54文本样式)
    - [文本对齐text-align](#文本对齐text-align)
    - [保留空白字符whitespace](#保留空白字符whitespace)
    - [文本方向](#文本方向)
    - [缩进text-indent](#缩进text-indent)
    - [间距](#间距)
    - [文本纵向对齐方式vertical-align](#文本纵向对齐方式vertical-align)
    - [文本阴影text-shadow](#文本阴影text-shadow)
    - [控制断词word-break](#控制断词word-break)
    - [控制文本溢出text-overflow](#控制文本溢出text-overflow)
    - [装饰文本text-decoration](#装饰文本text-decoration)
    - [转换大小写text-transform](#转换大小写text-transform)
    - [字体font](#字体font)
  - [5.5.特别效果](#55特别效果)
    - [过渡transition](#过渡transition)
    - [旋转](#旋转)
    - [移动](#移动)
    - [缩放](#缩放)
    - [倾斜](#倾斜)
    - [变形原点](#变形原点)
    - [3D变形方式](#3d变形方式)
    - [修改视域](#修改视域)
    - [背面处理](#背面处理)
    - [动画](#动画)
    - [滤镜](#滤镜)
    - [混合模式](#混合模式)
  - [5.6.布局](#56布局)
    - [float浮动](#float浮动)
    - [clear浮动清除](#clear浮动清除)
    - [position定位](#position定位)
    - [z-index绝对高度](#z-index绝对高度)
    - [BFC](#bfc)
    - [多列布局](#多列布局)
  - [5.7.经典布局](#57经典布局)
    - [居中](#居中)
    - [单列布局](#单列布局)
    - [两列布局](#两列布局)
    - [三列布局](#三列布局)
    - [margin负值法](#margin负值法)
    - [弹性盒布局](#弹性盒布局)
    - [栅格布局](#栅格布局)
- [6.补充](#6补充)
- [参考资料](#参考资料)

# 1.html文件的基本元素结构

html为一种标记语言，用标签（多数成对出现）来标记

```html
<!DOCTYPE html>
<html>
    <head>
        
    </head>
    <body>
        
    </body>
</html>
```



# 2.标签介绍

标签的常见格式

```
<标签名 属性1="值1" 属性2="值2" ......>(内容</标签名>可能没有)
```

标签没有结束标签——空标签



## 块级元素

自成一行，独占剩余

![image-20220819150333181](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220819150333181.png)

可包含其它块级和行内元素



## 行级元素

只在行内占用必要宽度

![image-20220819150407259](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220819150407259.png)

只能包含数据和其它行内元素



## 2.1.基础标签

### !DOCTYPE

文件声明，用于说明文件内容类型

```html
<!DOCTYPE html>
```



### head

html文件头部文件，title标签是head中唯一必要标签



### body

包含网页的内容



### 注释

```html
<!-- 这里面的就是注释了 -->
```



### title

定义网页的标题，标签间内容即为内容，在游览器中显示在标签页上



### meta

放于head标签之间用于告知游览器一些设置，设置编码的例子：

```html
<meta charset="UTF-8">
```

自适应：

```html
<meta name-"viewport" content="width=device-width,initial-scale=1.0">
```

网页描述：

```html
<meta name="keywords" content="关键词1，关键词2...">
<meta name="description" content="描述文本">
<meta name="author" content="RUINA">
```

自跳转

```html
<meta http-equiv="refresh" content="5(停留时间后跳转); http://...">
```



### base

设置一个基本的路径、url，为空元素

```html
<base href="./">
```



### style

给html制定样式，有media（指定样式试用媒体）、scoped（指定样式作用范围、仅火狐游览器支持）、type（text/css，指定样式类型，目前仅css）

```html
<style type="text/css"></style>
```



### script

script 元素既可以直接定义内嵌脚本语句，也可以通过 src 属性引用外部脚本文件。

script 元素可以出现在 HTML 文档中的各个部分，一个文档可以包含多个 script 元素。

给网页添加脚本，当脚本不支持脚本如JavaScript时，用noscript显示提示性内容

```html
<script type="text/javascript" src="*.js"></script>
```



### h1-h6

定义大小标题

```html
<h1>h1</h1>
<h2>h2</h2>
<h3>h3</h3>
<h4>h4</h4>
<h5>h5</h5>
<h6>h6</h6>
```



### hr

水平线

```html
<hr>
```



### br

换行，换一行

```html
<br>
```



### p

定义一个段落，即在标签前后创建空白

```html
<p>
    这是一个段落
</p>
```



## 2.2.链接

### a

a标签用于超链接，href（链接）属性，target（跳转方式）

```html
<a href="https://www.baidu.com" target="_blank">百度一下</a>
```



### link

连接外部资源，rel指定（链接外部内容的样式），置于head标签内，为空元素

```html
<link rel="stylesheet" href="*.css">
```



## 2.3.列表

### ul、ol、li

```html
<ul>
    <li>coffee</li>
    <li>tea</li>
</ul>
<ol>
    <li>html5</li>
    <li>css3</li>
    <li>javascript</li>
</ol>
```

ol属性：reversed（降序）、start（起始值）、type（列表排序标记的类型）



### dl、dt、dd

定义列表dl、dt（列表中项目）、dd(项目描述)

```html
<dl>
    <dt>A</dt>
    <dd>a</dd>
    <dt>B</dt>
    <dd>b</dd>
</dl>
```



## 2.4.图片

### img

img标签用于插入图片，有src（图片链接）与alt（图片无法显示时的替代文本）属性

height、width调整图片大小

```html
<img src="" alt="替代文本">
```



### picture

picture与source、img搭配使用

```html
<picture>
	<source media="(min-width:1024px)" srcset="">
    <source meida="(min-width:1024px)" srcset="">
    <img src="" alt="">
</picture>
```



### figure、figcaption

figure定义为插图，figcaption定义为插图标题

```html
<figure>
	<img src="" alt="">
    <figcaption>插图标题</figcaption>
</figure>
```



### map、area

map建立映射、area来通过设置图片，coords属性定义可点击区域、href定义区域目标url

```html
<img src="img/test.png" alt="test" usemap="#_map">
<map name="_map" id="_map">
<!--中心x，中心y，半径-->
<area shape="circle"
	coords="109,63,10"
	href ="test1.html"
	target ="_blank"
	alt="F">
<!--左上角坐标x，左上角坐标y，横轴，纵轴-->
<area shape="rect"
	coords="0,0,66 ,77"
	href ="test2.html"
	target ="_blank"
	alt="Python">
</map>
```



## 2.5.多媒体

### audio

音频

```html
<audio controls>
    <source src="*.*">
    你的游览器不支持该媒体
</audio>
```



### vedio

视频

```html
<vedio src="" width="" height="">
	备胎内容
</vedio>
```

controls为控制组件，autoplay为自动播放



## 2.6.绘图

### svg

svg代码可以直接嵌入到HTML页面中，或可以直接链接到SVG文件。

```html
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
	<circle cx="66" cy="50" r="40" stroke="black" stroke-width="2" fill="green" />
</svg>
```

插入html外的svg文件

```html
<object data="fishc.svg" type="image/svg+xml"></object>
<iframe src="rect.svg" width="300" height="100"></iframe>
```



### canvas

标签只是图形容器，必须使用脚本来绘制图形。



## 2.7.时间

### time

用于定义日期或时间，在任何主要浏览器中，time元素都不会呈现任何特殊内容

```html
<time datetime="2000-01-01">测试用</time>
```



## 2.8.表格

### table、tr、th、td

tr表示行、th表示表头格、td表示每一格

```html
<table>
    <tr>
    	<th>1_0</th>
        <th>2_0</th>
        <th>3_0</th>
        <th>4_0</th>
    </tr>
    <tr>
    	<td>1_1</td>
        <td>2_1</td>
        <td>3_1</td>
        <td>4_1</td>
    </tr>
    <tr>
    	<td>1_2</td>
        <td>2_2</td>
        <td>3_2</td>
        <td>4_2</td>
    </tr>
</table>
```



### caption

给表格添加标题，要紧挨着table的开始位置

```html
<table>
    <caption>表格标题</caption>
    <tr>
    	<td>1</td>
        <td>2</td>
    </tr>
    <tr>
    	<td>3</td>
        <td>4</td>
    </tr>
</table>
```



### thead、tbody、tfoot

```html
<table>
    <thead><!--表格头部-->
    	<tr>
            <td></td>
        </tr>
    </thead>
    <tbody><!--表格主体-->
    	<tr>
        	<td></td>
        </tr>
    </tbody>
    <tfoot><!--表格底部、尾部-->
    </tfoot>
</table>
```



### colgroup、rolgroup

colgroup、rolgroup标签用于对表格中的列进行组合，以便对其进行格式化

col为表格中一个或多个列定义属性值

```html
<table
	<colgroup>
        <col style="background: red">
        <col spn="2" style="background: green">
    </colgroup>
    <tr>
        <td>1</td>
        <td rowspan="3">2</td>
        <td>3</td>
	</tr>
	<tr>
        <td>4</td>
        <td>6</td>
	</tr>
	<tr>
        <td>7</td>
        <td>9</td>
	</tr>
</table>
```



## 2.9.表单

### form

form为表单标签，action属性设定处理数据的方法或页面，method指定post、get方法，get方法会将数据合并到url中，post将数据放入http文件主体中。

autocomplete属性指定是否自动填充，默认为on，可在input元素单独设置其属性

target属性如a元素一样，指定目标显示位置



### button

type可以设定不同标单按钮



### input

form中最重要的组件元素，根据设定不同type属性有不同的表现形式。

value属性存放数据值

autofocus属性设置是否自动对焦

```html
<input autofocus>
```

disabled设置为不可使用，但会显示出来，数据也不会使用

readonly属性设置为只能读，不可修改，但数据可使用

```html
<input readyonly>
```

placeholder显示提示内容

```html
<input type="tel" placeholder="提示内容">
```

required判断是否为空，不填内容无法提交

size设置尺寸

maxlength设置最大输入长度



list属性，与datalist元素搭配使用

```html
<input type="" list="urllist">
<datalist id="urllist">
	<option value="A">a</option>
    <option value="B">b</option>
    <option value="C">c</option>
</datalist>
```



#### type属性：

text普通文本，password为密码框即输入会用*号显示



button（普通按钮）、submit（提交整个表单）、reset（重置清空表单）也是button元素的type值



radio单选框，同一组选项name值设定为一致

```html
<input type="radio" name="sex" value="男">
<input type="radio" name="sex" value="女">
```



checkbox为复选框，同一组选项name值设定为一致



time、date、mouth、week、datetime-local

```html
<from>
	<label>时间：<input typr="time" name="time"></label>
    <label>日期：<input typr="date" name="date"></label>
    <label>年月：<input typr="mouth" name="mouth"></label>
    <label>星期：<input typr="week" name="week"></label>
    <label>本地日期和时间：<input typr="datetime-local" name="datetime-local"></label>
</from>
```



search搜索框

```html
<input type="search">
```



color选择框，值用rgb模式表示

```html
<input type="color">
```



image图像按钮，返回值为点击的图像位置离图片左上即初始点的距离

```html
<input type="image">
```



hidden隐藏元素，但元素可用

```html
<input type="hidden">
```



file为文件提交框，form必须使用post方式上传，还有enctype由默认的"application/x-www-form-urlencoded"改为"multipart/form-data"

```html
<form>
    <label action="" method="post" entype="multipart/form-data"><input></label>
</form>
```

accept属性指定文件类型可用扩展名，也可指定类型文件，[MIME类型]([完整的 MIME 类型列表,《零基础入门学习Web开发》（HTML5 & CSS3）,Web开发,鱼C论坛 - Powered by Discuz! (fishc.com.cn)](https://fishc.com.cn/thread-127231-1-1.html))

```html
<input accept=".jpg,.html,.avi">
<input accept="audio/*">
<input accept="video/*">
<input accept="image/*">
```

可在input元素name属性设置为"MAX_FILE_SIZE"，value值设为需要设置的值，单位为字节

multiple属性可添加多个文件	



number限制输入内容为数字，min（最小值）、max（最大值）、step（步径）

```html
<input type="number">
```



range数值滚动条

```html
<input type="range">
```



email电子邮箱，需要由@

tel电话，pattern属性可自定义匹配，可放入正则表达式

url网址

```html
<input type="email">
<input type="tel">
<input type="url">
```



### label

可以提高使用体验，隐式关联

```html
<label>label</label>
```



### fieldset

元素分组

```html
<form>
    <fieldset>
        <label>1</label>
        <label>2</label>
    </fieldset>
    <fieldset>
        
    </fieldset>
</form>
```



### legend

为filedset添加说明文字，不可单独使用，只能作为fieldset的第一个子元素

```html
<fieldset>
    <legend>
        说明文字
    </legend>
    adsfasdf
</fieldset>
<fieldset>dfads</fieldset>
```



### select、option、optgroup

下拉框，option为select子元素，multiple为复选属性（效果不如input复选框好）

```html
<select>
    <option>1</option>
    <option>2</option>
    <option>3</option>
</select>
```

optgroup为选项分组

```html
<select>
    <optgroup label="A">
    	<option>1</option>
        <option>2</option>
        <option>3</option>
    </optgroup>
    <optgroup label="B">
    	<option>1</option>
        <option>1</option>
        <option>1</option>
    </optgroup>
</select>
```



### output

https://www.bilibili.com/video/BV1QW411N762?p=24

```html
<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">
    0<input type="range" id="a" value="50" min="0" max="100">100 +
    <input type="number" id="b" value="50"> = 
    <output name="x" for="a b">100</output>
</form>
```



### textarea

多行文本输入，rows、cols设置行数列数，单位为字符，wrap属性指定如何处理自动换行

```html
<textarea></textarea>
```



## 2.10.内联框架

### iframe

内联框架，可嵌套打开其它网页的内容

```html
<iframe src="">
    你的游览器可能不支持
</iframe>
```



## 2.11.格式

### strong与b

强调文本元素，加粗，strong有表示重要的语义，b没有

```html
<strong>strong</strong>
<b>b</b>
```



### small

指定文本变小

```html
<small>small</small>
```



### em与i

表示强调，斜体，em有强调语义，i没有

```html
<em>em</em>
<i>i</i>
```



### del与ins、s、u

del表示删除，文本上画横线，ins表示插入，下划线

s与del不同，表示错误的

```html
<del>del</del>
<s>s</s>
<ins>ins</ins>
<u>u</u>
```



### mark

标记文本，类似荧光笔

```html
<mark>mark.</mark>
```



### wbr

规定在文本中何处适合添加换行符，而不是将整个单词放到下一行

```html
<p>
   test<wbr>test 
</p>
```



### sup与sub

sup上标，sub下标

```html
E = MC<sup>2</sup>
Mg + ZnSO<sub>4</sub> = MgSO<sub>4</sub> + Zn
```



### abbr

定义简称、缩写，配合title属性使用，鼠标放于其上显示title属性的值

```html
<abbr title=”yyy“>XXX</abbr>就是xxx
```



### address

定义文档文章作者的信息

```html
<address>xxx</address>
```



### q

较短引用，在内容两侧添加引号

```html
<q>q为短引用</q>
```



### blockquote与cite

blockquote与段落式引用，用缩进区分，cite指定引用的来源

```html
<cite>定义引用的来源：书籍、歌曲、电影、电视节目、绘画、雕塑等</cite>
<blockquote>
    fadoivnqrbvourvmwoifhqwerboruinvqeoivn,qoipvnbnqeouvnqrovnqweruivnbqeui<br>
    fadsfqwbrmuiqbmeoizfgdvqbwteyucbqeurbvqrivqnevquibvrinvoivmqeoivnbqui
</blockquote>
```



### dfn

定义术语或名称

```html
<dfn>dfn</dfn>
```



### pre

所见即所得，与代码内的文本完全一致

**字符实体**为需要显示特别符号时所用的专用代码

**等宽字体**，各字符宽度相等

```html
<pre>pre
pre
</pre>
```



### code

标签用于定义计算机代码片段

```html
<code>Is this a code?</code>
```



### var

用于定义程序的变量

```html
<var>var</var>
```



### kbd

定义用户的输入

```html
<kbd>kbd</kbd>
```



### samp

定义程序输出



### ruby(非ruby语言)、rt、rp

rt标记注音符号，rp显示游览器不支持ruby元素时显示内容

```html
<ruby>魑<rp>(</rp><rt>chi</rt><rp>)</rp></ruby>
<ruby>魅<rp>(</rp><rt>mei</rt><rp>)</rp></ruby>
<ruby>魍<rp>(</rp><rt>wang</rt><rp>)</rp></ruby>
<ruby>魉<rp>(</rp><rt>liang</rt><rp>)</rp></ruby>
```



### bdi

允许设置一段文本，使其脱离其父元素的文本方向设置

```html
<p>alice
    <bdi>测试一下</bdi>
    ruina
</p>
```



### bdo

指定文字显示方向，dir属性（ltr左往右，rtl右往左）

```html
<bdo dir="rtl">123</bdo>
```



### meter

类似进度条的元素

```html
<meter value="20%" min="0" max="1"></meter>
```



### progress

进度条，max，value

```html
<progress max="1" value="0.4"></progress>
```



## 2.12.网页架构

### div

最常用的布局用元素，块级无语义元素



### span

最常用的布局用元素，行级无语义元素



### html5开始的布局用元素

![image-20220827124905425](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220827124905425.png)

### header

定义简介形式的内容

### nav

定义页面主导航功能

### main

定义主内容，主内容中可以有各种子内容区段（article、section、div等）

### article

定义独立的文章内容，与页面其它部分无关（一篇博文）

### section

定义文档中的节，与article类似，但其更适用于组织页面使其按功能分块，嵌套后游览器会进行缩进修改等等

### aside

定义侧边栏（术语条目、作者简介、相关链接等）

### footer

定义页脚部分

### details、summary

details定义额外细节，open属性确定是否默认展开，summary定义details元素的标题，

```html
<details open>
	<summary>XXXXX</summary>
    <P>
        asdfasdfadsgfgbqorvn
    </P>
    <p>
        asdgtnteymrumumuumvwrvwetnrynumyi,nocvivnwoinj,onrvueonvwounvoiwmoer,
    </p>
</details>
```

### data

将一个指定内容和机器可读的翻译联系在一起

### dialog

定义一个对话框、确认框或窗口。



## 2.13.程序设计

### embed

定义嵌入的内容，比如插件，已经被符合标准的object标签代替



### noscript

用来向不支持 JavaScript 的浏览器显示一些替代内容

```html
<script>
	document.write("鱼C工作室");
</script>
<noscript>
	<p>抱歉，鱼油的浏览器不支持 JavaScript!</p>
	<img src="http://bbs.fishc.com/template/damei_z14/image/logo.png" alt="FishC">
</noscript>
<p>不支持 JavaScript 的浏览器会使用 noscript标签中定义的内容来替代。</p>
```



### object

定义一个嵌入的对象，本用于替代img等元素

```html
<object width="666" height="375" data="http://fishc.oss-cn-hangzhou.aliyuncs.com/Web/video_tag.mp4" ></object>
```



### param

允许为插入 XHTML 文档的对象规定 run-time 设置



### template

是一种用于保存客户端内容的机制，该内容在页面加载时不被渲染，但可以在运行时使用JavaScript进行实例化



# 3.css简述

```css3
选择器 {属性1:值1;属性2:值2;...}
/* 注释 */
```

用于描述html中组件样式的语言，插入方法有三种：

```html5
<!--1.内联样式-->
<div style=""></div>
<!--2.内部样式表-->
<style>
	color: #ffffff;
    background: #000000;
</style>
<!--3.外部样式表-->
<link rel="stylesheet" type="text/css" href="*.css">
```

优先级依次降低



# 4.选择器

## 4.1.基本选择器

### *通用选择器

```css
*{ }
```



### 元素选择器

```css
标签名 { }
```



### 类选择器

```html
<style>
    .for_p { }
</style>
<p class="for_p">
    test
</p>
```



### id选择器

```html
<style>
    #for_id { }
</style>
<p id="for_id"><!--每个标签唯一-->
    test
</p>
```



## 4.2.复合选择器

### 交集选择器

```css
元素选择器.类选择器 | 元素选择器#id选择器 { }
```

```css
div.class | div#id { }
```



### 并集选择器

```css
选择器1, 选择器2, 选择器3... { }
```

```css
p, #id, span, div, .class { }
```



### 后代选择器

```css
选择器1 选择器2 选择器3 ... { }
```

```css
div p span { }
```



### 子元素选择器

```html
选择器1 > 选择器2 { }
```

```css
div > p { }
```



### 相邻兄弟选择器（同级元素）

```xss
选择器1 + 选择器2 { }
```

```css
.class + p { }
```



### 通用兄弟选择器

```css
选择器1 ~ 选择器2
```

```css
.class ~ p { }
```



## 4.3.伪选择器

### 伪元素选择器

**::first-line**选择器，匹配文本块第一行内容，对行内元素不起作用

```css
::first-line {
    background-color: red;
    color: green;
}
```

**::first-letter**选择器，匹配文本块第一个字符

```css
::first-letter{
    background-color: red;
    color: green;
}
```

**::before**、**::after**选择器

```css
::before{
    content: "前文";
}
::after{
    content: "后文";
}
```

**::selection**用于用户所选内容

```css
::selection{
    color: #ffffff;
    background: pink;
}
```



### 伪类选择器

#### 动态伪类选择器

**:link**链接未被访问

**:visited**链接呗访问过

**:hover**鼠标悬停在链接上

**:active**鼠标摁下链接时

**:focus**得到焦点时



#### UI伪类选择器

**:enabled**可用

**:disabled**不可用

```css
:enabled{
    outline: 1px solid black;
}
:disabled{
    outline: 1px solid red;
}
```

**:checked**被选择时



**:required**必选的内容

**:optional**可选的内容



**:default**默认元素



**:valid**合法内容输入

**:invalid**非法内容输入



**:in-range**输入内容在范围内

**:out-of-range**输入内容超出范围



**:read-only**只读

**:read-write**可读写

为兼容火狐游览器，要加入-moz-，如：:-moz-read-only



#### 结构伪类选择器

**:root**根元素匹配

**:empty**未定义内容的元素



**:first-child**第一个子元素

**:last-child**最后一个子元素



**:only-child**如果该元素为其父元素唯一子元素

**:only-of-type**属于父元素的唯一类型子元素

**:first-of-type**父元素第一类的子元素

**:last-of-type**父元素最后一类的子元素



**:nth-child(n)**第n个子元素

**:nth-last-child(n)**倒数第n个子元素

**:nth-of-type(n)**某类型的第n个元素

**:nth-last-of-type(n)**某类型的倒数第n个元素



#### 其它伪类选择器

**:target**页面内锚点，页面内跳转（位置变化），配合页面内元素的id

**:lang**匹配设置了lang属性的元素

```html
<style type="text/css">
    :lang(zh){
        background-color: red;
    }
    :lang(en){
        background-color: green;
    }
</style>
<p lang="zh">中文</p>
<p lang="en">English</p>
```



**:not(selector)**对任意选择器进行反向选择



## 4.4.属性选择器

![image-20220827162950844](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220827162950844.png)



# 5.属性

## 5.1.颜色

有多种表示形式，以白色为例：

```css
rgb(255, 255, 255) /*rgb 按红、绿、蓝来分*/
#ffffff /*hex 美两个如rgb一样转换为十六进制*/
hsl() /*hsl 色相(Hue 0-360 0为红，120为绿，240为蓝)、饱和度(Saturation 0-100%)、色相(Lightness 0-100%)*/
rgba、hsla/*a表示透明，0-1，0为全透，1为不透*/
```



### color前景色

```css
color: red;
```



### background背景

**background-color**背景色

```css
background-color: Dodgerblue;
```



**background-image**背景图

```css
background-image: url("")[, url("")];/*左盖右*/
```

背景图会覆盖背景色



**background-repeat**背景重复

![image-20220828113733455](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220828113733455.png)



**background-position**背景位置

![image-20220828113906241](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220828113906241.png)



**background-size**背景大小

![image-20220828114116578](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220828114116578.png)



**background-attachment**

背景的附着方式，固定还是随着页面动



**background-origin**

背景开始绘制位置

![image-20220828114412919](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220828114412919.png)



**background-clip**

背景的显示位置区域



以上背景用属性可合在一起写为background



## 5.2.border边框

border-style

![image-20220913101438746](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913101438746.png)



border-width

有thin、medium、thick三个值，也可用具体数值如1px来表示



border-color

边框颜色



分部分写边框时可以用border-left/right/top/bottom-style/color/width来写，也可整体写

```css
border-style: [top] [right] [bottom] [left]
border-style: [top、bottom] [right、left]
border-style: [top] [right、left] [bottom]
```



### boder-radius

圆角边框

```css
border-radius: 15px 15px;
```

![image-20220913102538874](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913102538874.png)

决定边框的水平与竖直半径，用/分开说明是一个角的水平与竖直的设置，而不是两对设置

```css
border-radius: 15px / 10px;
```



### border-image图像边框

```css
border-image-source: url();/*决定图像路径*/
border-image-slice: 30;/*单位是px，但不能写出来*/
border-image-repeat: ;/*图片填充方式*/
border-image-width: ;/*图片边框宽度*/
border-image-outset: ;/*图片边框绘制起始位置，是向外扩张的距离*/
```

![image-20220913103316060](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913103316060.png)



## 5.3.组件外观

### margin/padding内外边距

值为百分比时按其父元素的大小计算

当两元素设定外边距所指示区域相同时，会重叠，以值最大的为准



### 元素尺寸设置

![image-20220913105050209](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913105050209.png)

设置box-size的值，width、height将包含对应内外边距、边框、内容的大小



元素的最小最大值

```css
min-width: ;/*最小值*/
max-width: ;/*最大值*/
```



overflow溢出部分处理

scroll指滚动条，auto为超出加滚动条没有就不加，hidden隐藏



resize是否允许用户改变元素大小

![image-20220913110111444](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913110111444.png)



### outline轮廓

与border类似，不属于元素尺寸的一部分，不影响页面布局，不会撑大元素，轮廓边框与元素border不一致

```css
outline-style: ;/*轮廓样式*/
outline-color: ;/*颜色*/
outline-width: ;/*宽度*/
outline-offset: ;/*与元素的距离*/
```



### box-shadow阴影

![image-20220913110906999](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913110906999.png)

多个阴影效果可用都好分割，阴影边框与元素border一致



### display显示属性

定义元素的显示属性，块级可自由定义大小等属性，行级不可行

block值定义元素为块；inline值定义元素为行；inline-block值定义为行内块，行内块上下会视为块，可设置宽度；none值会在布局上隐藏元素；list-item显示为带点的列表。



### visibility

visible值可视；hidden值不可见，但布局上位置存在；从collpace在界面占据空间但不显示，不常用



## 5.4.文本样式

### 文本对齐text-align

取值为start、end、left、right、center、justify(两端对齐)



### 保留空白字符whitespace

默认压缩空格与换行，设为ji则保留格式



### 文本方向

direction属性，ltr（左至右）默认，rtl（右至左），但是是指文本整体放置位置

加unicode-bidi: bidi-override则文本顺序叶变换

writing-mode属性

![image-20221003180454015](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003180454015.png)



### 缩进text-indent

```css
text-indent: 2em;
```



### 间距

letter-spacing字母间距

```css
letter-spacing: 2em;//两字符
```

word-spacing单词间距

line-height行高

```css
line-height: 2;//不带单位为该元素字体尺寸的倍数
```



### 文本纵向对齐方式vertical-align

![image-20221003181414930](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003181414930.png)



### 文本阴影text-shadow

![image-20221003181658825](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003181658825.png)

```css
text-shadow: 2px 2px 5px red;
```



### 控制断词word-break

```css
word-break: break-all;
```



### 控制文本溢出text-overflow

```css
text-overflow: ellipsis;//超出部分会用省略号...表示
```

使用该属性必须设置以下属性：

```css
white-space: nowrap;
overflow: hidden;
```



### 装饰文本text-decoration

**text-decoration-line**指定为上划线(overline)、下划线(underline)、中划线(line-through)、无(none)

**text-decoration-thickness**指定线的厚度

**text-decoration-style**指定实线、双实线、点线、虚线、波浪线(wavy)

**text-decoration-color**颜色



### 转换大小写text-transform

![image-20221003183651435](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003183651435.png)



### 字体font

**font-family**指定字体，需要看用户电脑中字体，设置多个值来备选；后备字体衬线字体、无衬线字体、等宽字体、草书字体、奇幻字体；字体名中有特殊字符或空格需要用引号框住字体名

**font-size**指定字体大小，除数值与百分比可用：xx-small、x-small、small、medium、large、x-large、xx-large

**font-weight**字体粗细，属性可选：lighter、normal、bold、bolder、100、200、300、400、500、600、700、800、900

**font-style**指定是否倾斜

**font-variant**指定文本是否以小型大写字体显示(small-caps)

**@font-face**指定字体名称与字体下载位置让用户下载

```css
@font-face{
    font-family:"xxx";
    src: url("./xxx.ttf");//路径
}
```



## 5.5.特别效果

### 过渡transition

![image-20221003185855928](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003185855928.png)

不指定过渡属性名就全部适用，未被指定的就无过渡效果，若指定不同属性不同过渡用逗号分割

**transition-timing-function**速度函数，ease(慢快慢)、linear(线性速度、匀速)、ease-in(慢到快)、ease-out(快到慢)、ease-in-out(中间快，两端慢)，也可用贝塞尔曲线函数来自定义cubic-bezier( num1, num2, num3, num4)；steps()函数也可

transition为四属性合写



### 旋转

rotate()参数为正数向右旋转，负数为向左旋转，单位deg表示度数

```css
rotate(180deg);
```

rotateX()沿x轴旋转，上下翻转

rotateY()沿y轴旋转，左右翻转

rotateZ()沿z轴旋转，旋转

rotate3d()共四个参数，前三个指定xyz轴的分量，指定旋转的角度



### 移动

translateX()在x轴上移动

```css
translateX(200px);
```

translateY()在y轴上移动

translate()在两个轴上移动，两个参数



### 缩放

参数为缩放比例

scaleX()在x轴上缩放

```css
scaleX(1.5);
```

scaleY()在y轴上缩放

scale()在两轴上缩放，两个参数

scaleZ()在z轴上缩放

scale3d()在三个轴上缩放



### 倾斜

倾斜，参数单位deg角度

skewX()

skewY()

skew()



### 变形原点

旋转、移动、缩放等效果的变形起点transform-origin

用left、right、bottom、top、center关键字指定

```css
transform-origin: left top;//左上角为原点
transform-origin: 50px 150px;//距离元素左边和顶边的距离
transform-origin: 80% 80%;//相对于元素的长与宽来进行计算
transform-origin: 150px 150px 150px;//3d方向上只能用长度设置
```



### 3D变形方式

设置子元素依靠父元素变形还是自己有变形空间

```css
transform-style: preserve-3d;//子元素有自身3d空间
```



### 修改视域

perspective()可使3d空间产生透视效果，perspective属性与函数有差异

```css
perspective(2000px);
perspective: 2000px;
```



### 背面处理

元素在3d变形背面朝向用户时的处理，backface-visibility决定是否渲染背面，visible为渲染，hidden不渲染



### 动画

样式1变为样式2的加强过渡

![image-20221003194642667](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003194642667.png)

关键帧

![image-20221003194745844](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003194745844.png)

animetion-direction指定动画方向

![image-20221003195024307](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221003195024307.png)



### 滤镜

```css
element.style{
	filter:grayscale(1);
}
```

整个网页变灰



### 混合模式





## 5.6.布局

### float浮动

none不浮动，left浮动到父元素内部左侧，right浮动到父元素内部右侧

浮动会脱离文档流，会覆盖不浮动的元素，文字会主动避开浮动性质，显示为围绕样式

```css
.left {float: left;}
.right {float: right;}
/*两列布局*/

.left {float: left;}
.middle {float: left;}
.right {float:right;}
/*三列布局*/
```



### clear浮动清除

both停止该元素两侧的浮动，left仅停止该元素左侧的浮动，right仅停止该元素右侧的浮动



### position定位

![image-20220913141446753](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913141446753.png)

top、bottom、left、right指定元素对应方位的偏移量；当设为absolute且外部没有元素设定position则用最外层元素；sticky为粘滞定位，使用top等属性时可设定粘滞的位置。



### z-index绝对高度

默认值为0，可为负数，值越大元素就体现在上方。



### BFC

BLock Formatting contexts块级格式化上下文，建立一个容器，内部与外部互不干扰，以下条件均可建立一个BFC容器

![image-20220913145628958](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913145628958.png)

浮动包裹

子元素浮动，父元素要包裹也要添加浮动，也可以

```html
<html>
    <head>
        <style>
            .box {
                background-color: pink;
            }
            .clear {
                clear: both;
            }
            
            p { 
            	float: left;
                background: blue;
            }
        </style>
    </head>
    <body>
        <div class="box">
            <p>this is an e.g.</p>
            <p>this is an e.g.</p>
            <div class="clear"></div>
        </div>
    </body>
</html>
```

也可创造一个新的BFC

阻止文本环绕



### 多列布局

![image-20220913145526695](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913145526695.png)

column-rule的值与border相似

column-width指定每列**最小**宽度



## 5.7.经典布局

### 居中

```css
.class1{ 
    text-align:ceter;/*父级元素设置子元素水平居中*/
	/*位置对上一设置position的元素绝对居中*/
    margin: auto;/*父级元素水平居中*/
    position: absolute;
    top: 0;
    bottom 0;
    left: 0;
    right: 0;
}
.class2{ line-height: ;/*子元素垂直居中，值要与父级元素的height相等*/}
```



### 单列布局

```css
.header {}
.main {}
.footer {}
```



### 两列布局

```css
.left { float: left;}
.right { float: right;}
```

```css
.aside { 
    width: 200px;
    float: left;
}
.main {
    margin-left: 200px;
    width: auto;/*可不写*/
}
```



### 三列布局

```css
.left {
	width: 200px;
    float: left;
}
.right {
    width: 200px;
    float: right;
}
.center{
    margin: 0 200px;
}
```



### margin负值法

```html
<!-- css部分 -->
.container{
	width: 100%;
	float: left;
}
.center{
	height: 500px;
	margin: 0 auto;
	background-color: ;
}
.left{
	height: 500px;
	width: 200px;
	float: left;
	margin-left: -100%;
}
.right{
	height: 500px;
	width: 200px;
	float: left;
	margin-left: -200px;
}
<!-- html部分 -->
<div class="container">
    <div class="center"></div>
</div>
<div class="left"></div>
<div class="right"></div>
```

双飞翼是在以上方法的部件放入main中，再加上header与footer

圣杯布局

```html
<header></header>
<main>
	<div id="center" class="column"></div>
    <div id="left" class="column"></div>
    <div id="right" class="column"></div>
</main>
<footer></footer>
```

```css
body{
    min-widht: 600px;
}
main{
    padding: 0 200px;
}
.column {
    float: left;
}
#center {
    width: 100%;
    height: 500px;
    background-color: cornsilk;
}
#left {
    width: 200px;
    height: 500px;
    margin-left: -100%;
    position: relative;
    right: 200px;
    background-color: pink;
}
#right {
    width: 200px;
    height: 500px;
    margin-left: -200px;
    background-color: lightblue;
}
header {
    height: 30px;
    background-color: red;
}
footer {
    height: 30px;
    background-color: red;
    clear: both;
}
```



[瀑布流布局](https://www.bilibili.com/video/BV1QW411N762?p=61)

魔笔小说使用的布局



### 弹性盒布局

display属性设置为flex（块样式）；inline-flex为行内块，内容多少，就多宽。

子元素也会变为弹性元素

 

flex-wrap属性

![image-20220913193947554](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913193947554.png)



flex-direction属性

![image-20220913194147541](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913194147541.png)

flex-wrap与flex-direction可合并为flex-flow



弹性盒对齐

主轴：主轴规定了弹性元素排布的顺序

垂轴：垂轴决定了在换行，第二行元素的添加方向，与主轴垂直

![image-20220913195219654](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913195219654.png)

![image-20220913195533281](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220913195533281.png)



justify-content主轴的对齐方式

![image-20220921145516209](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921145516209.png)



align-items

![image-20220921150058426](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921150058426.png)

align-self只改变单独一个元素的对齐方式，在弹性元素中设置



align-content多行弹性布局的垂轴布局

![image-20220921150606682](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921150606682.png)



order

调整顺序



flex-shrink

设置弹性元素在需要压缩时的压缩比例，默认为1，0为不压缩



flex-grow

弹性盒容器有空余时可以填充的比例



flex-basis

设置弹性元素在**主轴**上的初始尺寸，即可能为高度也可为宽度，并且当与设置矛盾时以此属性为准



flex

flex-grow、flex-shrink、flex-basis的整合版，默认值为：0 1 auto



### 栅格布局

![image-20220921154004399](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921154004399.png)

要创建栅格容器要给display属性设置为：grid或者inline-grid

**grid-template-columns**定义纵向栅格轨道

**grid-template-rows**定义横向栅格轨道

多个值指定对应的格子的值，1fr指剩余全部占掉，1：2：3的设置为1fr 2fr 3fr

容器未指定高度宽度时用fr按内容尺寸来计算



**grid-template-areas**定义区域

![image-20220921155425854](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921155425854.png)

![image-20220921155433638](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921155433638.png)

字符串中的关键字不可合并，区域形状必须为矩形

需要留空的部分用英文的一个或多个句号代替，不可缺少

与grid-template-rows、grid-template-columns可组合使用，也可缩写

![image-20220921160142318](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921160142318.png)

![image-20220921160234522](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921160234522.png)



grid-gap定义栅格元素的间距，为grid-column-gap与grid-row-gap，缩写先行后列



**fr**份数关键字

**auto**游览器决定元素宽度

**min-content**尽可能显示内容所需空间

**max-content**尽可能占据空间

**repeat(times, value)**重复函数，times次数，value值

**auto-fill**自动调整数量

**minmax(min, max)**设置最小最大值

**auto-fit**用已有元素自动填充

**fit-content(arg)**在极限值间取得合适值



栅格布局的对齐方式

与弹性盒布局相似有以下属性

**justify-content**指定栅格元素在水平方向的对齐方式

**justify-items**内容相对于栅格元素的横向对齐

**justify-self**设置单个栅格元素的内容

**align-content**指定在垂直方向的对齐方式

**align-items**内容相对于栅格元素的纵向对齐

**align-self**设置单个栅格元素的内容



**place-content**为align-content、justify-content合写

**place-items**为align-items、justify-items合写

**place-self**为align-self、justify-self合写



栅格线

![image-20220921163411804](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921163411804.png)

可用 [ ] 框起来，多个名字用空格分开 

**grid-column-start**

**grid-column-end**

**grid-row-start**

**grid-row-end**

![image-20220921163828033](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921163828033.png)

省略结束的位置时用起始的下一条开始，不起名可用默认的数字；栅格可重叠，调整可用z-index或order来调整

**grid-column**、**grid-row**为以上四属性的简写，值用 / 分隔，值为：start / end

**grid-area**: grid-column-start / grid-row-start / grid-column-end / grid-row-end



grid-auto-flow![image-20220921164744478](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921164744478.png)



**grid**为grid-template-rows、grid-template-areas、grid-template-columns、grid-auto-rows、grid-auto-columns、grid-auto-flow简写

![image-20220921165613887](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921165613887.png)

![image-20220921165649268](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220921165649268.png)


# 6.补充

**数值单位说明**：css中有较多数值后的单位以下是一些说明，参考于：[px、em、rem、vw、vh、vmax、vmin的区别_一月清辉的博客-CSDN博客](https://blog.csdn.net/yiyueqinghui/article/details/107324083)

**px**：像素，对于不同大小的屏幕可能体现的大小不同；稳定但缩放时布局多半会乱

**em**：相对于父节点字体大小

**rem**：“root em”对于根节点html的字体大小来计算

**vw**：viewpoint width，视窗宽度，1vw等于游览器窗口宽度1%

**vh**：viewpoint height，视窗高度，1vh等于游览器窗口高度1%

**vmin、vmax**：vw、vh中最小最大的

**fr**：gird布局中的自适应单位，用于在一系列长度值中分配剩余空间，剩下的空间是按照各自的数字按比例分配。



# 参考资料

[教程](https://www.bilibili.com/video/BV1QW411N762)

[get、post方法区别]([99% 的人都理解错了 HTTP 中 GET 与 POST 的区别（转）,《零基础入门学习Web开发》（HTML5 & CSS3）,Web开发,鱼C论坛 - Powered by Discuz! (fishc.com.cn)](https://fishc.com.cn/forum.php?mod=viewthread&tid=122724&extra=page%3D1%26filter%3Dtypeid%26typeid%3D731))

[emmet语法](https://www.bilibili.com/video/BV1Az4y1k74f)

乱数假文Lorem
