层叠样式表（CascadingStyleSheets,缩写为CSS）是一种样式表语言，用来描述HTML文档的呈现（美化内容）。<br>
书写位置：title标签下方添加style双标签，style标签里面书写CSS代码。

## CSS引入方式

* 内部样式表：学习使用。
	* CSS代码写在style标签里面
* 外部样式表：开发使用
	* CSS代码写在单独的CSS文件中(.css)
	* 在HTML使用link标签引入
```
<linkrel="stylesheet"href="./my.css">
```
* 行内样式：配合JavaScript使用
## 选择器
作用：查找标签，设置样式。

基础选择器
* 标签选择器
* 类选择器
* id选择器
* 通配符选择器

### 标签选择器
标签选择器：使用标签名作为选择器 → 选中同名标签设置相同的样式。
例如:p,h1,div,a,img…

### 类选择器
作用：查找标签，差异化设置标签的显示效果。
步骤：
* 定义类选择器 → `.类名`
* 使用类选择器 → 标签添加`class="类名'`

```
<style>
.red {
color: red;
}
</style>
<div class="red">这是 div 标签</div>
```

注意:
* 类名自定义，不要用纯数字或中文，尽量用英文命名。
* 一个类选择器可以供多个标签使用
* 一个标签可以使用多个类名，类名之间用空格隔开

开发习惯:类名见名知意，多个单词可以用-连接，例如：news-hd


### id选择器
作用：查找标签，差异化设置标签的显示效果。<br>
场景：id 选择器一般配合JavaScript使用，很少用来设置 CSS 样式<br>
步骤：
* 定义 id 选择器 → \#id名
* 使用 id 选择器 → 标签添加 `id="id名"`

```
<style>
#red f
color:red;
</style>
<div id="red">这是 div 标签</div>
```

规则：
* 同一个 id 选择器在一个页面只能使用一次

### 通配符选择器
作用：查找页面所有标签，设置相同样式。<br>
通配符选择器：\*，不需要调用，浏览器自动查找页面所有标签，设置相同的样式


## 画盒子
目标：使用合适的选择器画盒子

### 示例

#### 代码

```
<!DOCTYPE html>
<html lang="en">
<head>
  ……
  <style>
    .red{
      width: 100px;
      height: 100px;
      background-color: brown;
    }

    .orange {
      width: 200px;
      height: 200px;
      background-color: orange;
    }
  </style>
</head>
<body>
  <div class="red">div1</div>
  <div class="orange">div2</div>
</body>
</html>
```

#### 展示效果

<div style="width: 100px; height: 100px; background-color: brown;">div1</div>
<div style="width: 200px; height: 200px; background-color: orange;">div2</div>
### 属性

| 属性名              | 作用  |
| ---------------- | --- |
| width            | 宽度  |
| height           | 高度  |
| background-color | 背景色 |


## 字体修饰属性

| 描述     | 属性              | 效果                                                                                       |
| ------ | --------------- | ---------------------------------------------------------------------------------------- |
| 字体大小   | font-size       | 文字 &  <font size=5>文字                                                                    |
| 字体粗细   | font-weight     | 文字 & <b>文字</b>                                                                           |
| 字体倾斜   | font-style      | 文字 & * 文字 *                                                                              |
| 行高     | line-height     | <p style="line-height: 80px;">行高为80px的段落</p><p style="line-height: 80px;">行高为80px的段落</p> |
| 字体族    | font-family     | 文字 & 文字                                                                                  |
| 字体复合属性 | font            | 复合属性                                                                                     |
| 文本缩进   | text-indent     | <p style="text-indent: 2em;">玉兰颇受明清时期文人的欢迎，尤其在明代万历年间，玉兰被大量种植。</p>                        |
| 文本对齐   | text-align      | <p text-align>对齐方式</p>                                                                   |
| 修饰线    | text-decoration | 文字 & <u>文字</u> & ~~文字~~ & <p text-decoration文字                                           |
| 颜色     | color           | 文字 & <font color=red>文字                                                                  |


### 行高

作用：设置多行文本的间距<br>
属性名： line-height<br>
属性值数字+数字（当前标签font-size属性值的倍数）

#### 代码
```
<p style="line-height: 80px;">行高为80px的段落</p>
<p style="line-height: 80px;">行高为80px的段落</p>
```

#### 展示效果
<p style="line-height: 80px;">行高为80px的段落</p>
<p style="line-height: 80px;">行高为80px的段落</p>


### 字体族
属性名：font-family<br>
属性值：字体名

#### 代码
```
font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif;
```

拓展（了解）：font-family属性值可以书写多个字体名，各个字体名用逗号隔开，执行顺序是从左向右依次查找
* font-family属性最后设置一个字体族名，网页开发建议使用无衬线字体

![[{424E03F5-5FB2-4147-BFE0-6635E52174AA}.png]]


### font字体复合属性

复合属性：属性的简写方式，一个属性对应多个值的写法，各个属性值之间用空格隔开。<br>
font：是否倾斜，是否加粗，字号/行高，字体（必须按顺序书写）

原本的CSS：
```
div {
  font-style: italic;
  font-weight: 700;
  font-size: 30px;
  line-height: 2;
  font-family: 楷体;
}
```

使用font：
```
div {
  font: italic 700 30px/2 楷体;
}
```

#### 展示效果
<p style="font: italic 700 30px/2 楷体;">字体</p>

注意：字号和字体值必须书写/，否则 font 属性不生效


### 文本缩进
属性名： text-indent<br>
属性值：
	* 数字+ px
	* 数字 +em （推荐：1em = 当前标签的字号大小）

#### 代码
```
<p style="text-indent: 2em">今年受成本驱动、需求拉动以及全球粮价上涨等各种因素叠加影响，我国粮食价格整体上扬，小麦、玉米、大豆价格高位波动，水稻价格运行平稳，优质优价特征明显，农民择机择时售粮，实现种粮收益最大化。但种粮成本持续攀升成为影响农民增收的“拦路虎”。这是因为，在去年高粮价的刺激下，今年土地租金以及化肥、农药、柴油等农资价格大幅上涨，种粮成本随之增加。加之今年粮食生产遭遇去年北方罕见秋雨秋汛、今年“南旱北涝”等极端天气，虽然没有带来灾害性后果，但一些农户为抗灾付出更多生产成本，种粮农户收益空间进一步收窄。</P>
```

#### 展示效果
<p style="text-indent: 2em">今年受成本驱动、需求拉动以及全球粮价上涨等各种因素叠加影响，我国粮食价格整体上扬，小麦、玉米、大豆价格高位波动，水稻价格运行平稳，优质优价特征明显，农民择机择时售粮，实现种粮收益最大化。但种粮成本持续攀升成为影响农民增收的“拦路虎”。这是因为，在去年高粮价的刺激下，今年土地租金以及化肥、农药、柴油等农资价格大幅上涨，种粮成本随之增加。加之今年粮食生产遭遇去年北方罕见秋雨秋汛、今年“南旱北涝”等极端天气，虽然没有带来灾害性后果，但一些农户为抗灾付出更多生产成本，种粮农户收益空间进一步收窄。</P>


### 文本对齐方式
作用：控制内容水平对齐方式<br>
属性名： text-align

#### 属性

| 属性值    | 效果      |
| ------ | ------- |
| left   | 左对齐（默认） |
| center | 居中对齐    |
| right  | 右对齐     |

### 文本修饰线
属性名： text-decoration<br>
#### 属性

| 属性值          | 效果  |
| ------------ | --- |
| none         | 无   |
| underline    | 下划线 |
| line-through | 删除线 |
| overline     | 上划线 |


### 文字颜色
属性名：color<br>
#### 属性值

| 颜色表示方式  | 属性值           | 说明                               | 使用场景         |
| ------- | ------------- | -------------------------------- | ------------ |
| 颜色关键字   | 颜色英文单词        | red，green，blue……                 | 学习测试         |
| rgb表示法  | rgb（r,g,b）    | r,g,b 表示红绿蓝三原色，取值： 0-255         | 了解           |
| rgba表示法 | rgba（r,g,b,a） | a表示透明度，取值：0-1                    | 开发使用，实现透明色   |
| 十六进制表示法 | \#RRGGBB      | \#000000,\#ffcc00,简写：\#000，\#fc0 | 开发使用（从设计稿复制） |



## 复合选择器
定义：两个或多个基础选择器通过不同的方工组而成。<br>
作用：更准确、更高效的选择目标元素（标签）。

### 后代选择器
后代选择器：选中某元素的后代元素。<br>
选择器写法：父选择器 子选择器 {css属性}，父子选择器之间用空格隔开。

### 子代选择器
子代选择器：选中某元素的子代元素（最近的子级）。<br>
选择器写法：父选择器 > 子选择器{CSS属性}，父子选择器之间用 > 隔开。

### 并集选择器
并集选择器：选中多组标签，设相同的样式。<br>
选择器写法：选择器1,选择器2,……选择器N {CSS属性}，选择器之间用`,`隔开。

```
<style>
  div,
  span,
  p {
    color: red;
  }
</style>
<div>div标签</div>
<span>span标签</span>
<p>p标签</p>
```

### 交集选择器
交集选择器：选中同时满足多个条件的元素。<br>
选择器写法：选择器1 选择器2 {CSS属性}，选择器之间连写，没有任何符号。<br>
注意：如果交集选择器中有标签选择器，标签选择器必须写在最前面。

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
  <style>
    p.box {
    color: red;
  }
  </style>
</head>
<body>
  <p class="box">p标签，使用class选择器</p>
</body>
</html>
```

### 伪类选择器
伪类选择器：伪类表示元素状态，选中元素的某个状态设置样式。
鼠标悬停状态：选择器:hover {CSS属性}

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
  <style>
    a:hover {
      color: red;
    }
  </style>
</head>
<body>
  <a href="www.baidu,com">点击跳转百度</a>
</body>
</html>
```

### 伪类-超链接
超链接一共有四个状态<br>

| 选择器      | 作用      |
| -------- | ------- |
| :link    | 访问前     |
| :visited | 访问后     |
| :hover   | 鼠标悬停    |
| :active  | 点击时（激活） |
提示：如果要给超链接设置以上四个状态，需要LVHA的顺序书写。

## CSS三大特性
### 继承性
特点：
* 默认继承父级的文字控制属性。
* 如标签自己有样式，则生效自己的样式，不继承

```
body {
font: 12px/1.5 Microsoft YaHei,Heiti SC,tahoma,aria1,Hiragino Sans;
color: #666;
}
```

### 层叠性
特点：
* 相同的属性会覆盖：后面的 CSS 属性覆盖前面的 CSS 属性
* 不同的属性会叠加：不同的 CSS 属性都生效

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
  <style>
    div {
      color: red;
      font-weight: 700;
    }

    div {
      color: green;
      font-size: 30px;
    }
  </style>
</head>
<body>
  <div>标签</div>
</body>
</html>
```


### 优先级
优先级：也叫权重，当一个标签使用了多种选择器时，基于不同种类的选择器的匹配规则。<br>
规则：选择器优先级高的样式生效。<br>
公式：通配符选择器 < 标签选择器 < 类选择器 < id选择器 < 行内样式 < !important（选中标签的范围越大，优先级越低）<br>
#### 优先级-叠加计算规则
叠加计算：如果是复合选择器，则需要权重叠加计算。<br>
公式：（每一级之间不存在进位）
$（行内样式， id 选择器个数，类选择器个数，标签选择器个数）$

规则：
* 从左向右依次比较选个数，同一级个数多的优先级高，如果个数相同，则向后比较
* !important 权重最高
* 继承权重最低

## Emmet写法
Emmet 写法：代码的简写方式，输入缩写VSCode会自动生成对应的代码。<br>

### HTML

| 说明     | 标签结构                                         | Emmet        |
| ------ | -------------------------------------------- | ------------ |
| 类选择器   | `<div class="box"></div>`                    | `标签名`.`类名`   |
| id选择器  | `<div id="box"></div>`                       | `标签名`\#`id名` |
| 同级标签   | `<div><p></p></div>`                         | `div`>`p`    |
| 多个相同标签 | `<span>1</span><span>2</span><span>3</span>` | `span*3`     |
| 有内容的标签 | `<div>内容</div>`                              | `div{内容}`    |

### CSS
CSS的简写大多为首字母，如`w`，可以加上属性值，如`w500`。
也可以多个属性间用`+`链接，如`w500+h500+bgc`


## 背景属性
### 属性

| 描述      | 属性                    |
| ------- | --------------------- |
| 背景色     | background-color      |
| 背景图     | background-image      |
| 背景图平铺方式 | background-repeat     |
| 背景图位置   | background-position   |
| 背景图缩放   | backgrond-size        |
| 背景图固定   | background-attachment |
| 背景复合属性  | background            |

### 背景图
网页中，使用背景图实现装饰性的图片效果。<br>
属性名： background-image(bgi)<br>
属性值：url（背景图URL）

```
div {
width:400px;
height:400px;
background-image: url(./images/1.png);
}
```
背景图默认平铺效果，如果标签太大，会复制几分填充空白



### 背景图平铺方式
属性名：background-repeat（bgr）<br>
属性值：

| 属性值       | 效果       |
| --------- | -------- |
| no-repeat | 不平铺      |
| repeat    | 平铺（默认效果） |
| repeat-x  | 水平方向平铺   |
| repeat-y  | 垂直方向平铺   |

### 背景图位置
属性名： background-position (bgp）
属性值：水平方向位置 垂直方向位置
* 关键字：

| 关键字    | 位置  |
| ------ | --- |
| left   | 左侧  |
| right  | 右侧  |
| center | 居中  |
| top    | 顶部  |
| bottom | 底部  |
* 坐标（数字 + px，正负都可以）
	* 水平：正数向右；负数向左
	* 垂直：正数向下；负数向上

```
div {
width: 400px;
height: 400px;
background-color: pink;
background-image: url(./images/l.png);
background-repeat: no-repeat;
background-position: center bottom;
background-position: 50px -100px;
background-position: 50px center;
}
```

提示：
* 关键字取值方式写法，可以颠倒取值顺序。
* 可以只写一个关键字，另一个方向默认为居中；数字只写一个值表示水平方向，垂直方向为居中

### 背景图缩放
作用：设置背景图大小
属性名：background-size (bgz)
常用属性值：
* 关键字
	* cover：等比例缩放背景图片以完全覆盖背景区，可能背景图片部分看不见
	* contain：等比例缩放背景图片以完全装入背景区，可能背景区部分空白
* 百分比：根据盒子尺寸计算图片大小（100％图片的宽度跟盒子宽度一样，图片的高度按照图片比例等比缩放，可能超出盒子范畴）
* 数字+单位（例如： px ）

### 背景图固定
作用：背景不会随着元素的内容滚动。<br>
属性名：background-attachment（ bga ）<br>
属性值： fixed

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
  <style>
    body {
      background-attachment: fixed;
    }
  </style>
</head>
<body>
  <div>11111111111</div>
</body>
</html>
```

### 背景复合属性
属性名： background（ bg ）<br>
属性值：背景色 背景图 背景图平铺方式 背景图位置/背景图缩放 背景图固定（空格隔开各个属性值，不区分顺序）

```
div {
width: 400px;
height: 400px;
background: pink url(./images/1.png) no-repeat right center/cover;
```


## 显示模式
显示模式
块级元素：
* 独占一行
* 宽度默认是父级的 100 ％
* 添加宽高属性生效
行内元素
* 一行共存多个
* 由内容撑开
* 加宽高不生效
行内块元素
* 一行共存多个
* 由内容撑开
* 加宽高生效

### 转换显示模式
属性名：display
属性值：

| 属性值          | 效果  |
| ------------ | --- |
| block        | 块级  |
| inline-block | 行内块 |
| inline       | 行内  |

## 结构伪类选择器
作用：根据元素的结构关系查找元素。

| 选择器            | 说明                  |
| -------------- | ------------------- |
| E:first-child  | 找第一个E元素             |
| E:last-child   | 找最后一个E元素            |
| E:nth-child(N) | 查找第N个E元素（第一个元素N值为1） |
E是选择器

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Document</title>
  <style>
    li:first-child {
      background-color: yellow;
    }
    li:nth-child(7) {
      background-color: blue;
    }
    li:last-child {
      background-color: green;
    }
  </style>
</head>
<body>
  <ul>
    <li>li 1</li>
    <li>li 2</li>
    <li>li 3</li>
    <li>li 4</li>
    <li>li 5</li>
    <li>li 6</li>
    <li>li 7</li>
    <li>li 8</li>
    <li>li 9</li>
    <li>li 10</li>
  </ul>
</body>
</html>
```

### :nth-child(公式)

| 功能       | 公式        |
| -------- | --------- |
| 偶数标签     | 2n        |
| 奇数标签     | 2n+1；2n-1 |
| 5的倍数的标签  | 5n        |
| 第五个以后的标签 | n+5       |
| 第五个以前的标签 | -n+5      |

## 伪元素选择器
作用：创建虚拟元素（伪元素）用来摆放装饰性的内容。

| 选择器       | 说明                 |
| --------- | ------------------ |
| E::before | 在 E 元素里面最前面添加一个伪元素 |
| E::after  | 在 E 元素里面最后面添加一个伪元素 |
注意点：
* 必须设置 `content:" "`属性，用来设置伪元素的内容，如果没有内容，则引号留空即可
* 伪元素默认是行内显示模式
* 权重和标签选择器相同

## 盒子模型
### 盒子模型-组成
盒子模型重要组成部分：
* 内容区域- width & height
* 内边距 - padding （出现在内容与盒子边缘之间）
* 边框线 - border
* 外边距 - margin（出现在盒子外面）

### 盒子模型-边框线
属性名：border（bd）
属性值：边框线粗细 线条样式 颜色（不区分顺序）
常用线条样式

| 属性值    | 线条样式 |
| ------ | ---- |
| soild  | 实线   |
| dashed | 虚线   |
| dotted | 点线   |


#### 设置单方向边框线
属性名： border-方位名词（ bd + 方位名词首字母，例如，bdl）
属性值：边框线粗细线条样式颜色（不区分顺序）

```
div {
	border-top: 2px solid red;
	border-right: 3px dashed green;
	border-bottom: 4px dotted blue;
	border-left: 5px solid orange;
	
	width: 200px;
	height:200px;
	background-color: pink;
}
```


### 盒子模型-内边距
作用：设置内容与盒子边缘之间的距离。
属性名： padding/padding-方位名词

```
div {
padding: 3epx;

padding-top: 10px;
padding-right: 20px;
padding-bottom: 40px;
padding-left: 80px;
width: 200px;
height: 200px;
background-color: pink;
}
```

#### 盒子模型-内边距-多值写法

| 取值个数 | 示例                             | 含义                          |
| ---- | ------------------------------ | --------------------------- |
| 一个值  | `padding: 10px`                | 四个方向内边距均为 10p×              |
| 四个值  | `padding: 10px 20px 40px 80px` | 上:10px；右：20px；下：40px；左：80px |
| 三个值  | `padding: 10px 40px 80px`      | 上：10px；左右：40px；下：80px       |
| 两个值  | `padding: 10px 80px`           | 上下：10px；左右：80px             |

### 盒子模型-尺寸计算
* 默认情况
	盒子尺寸=内容尺寸 + border尺寸 + 内边距尺寸
* 结论：给盒子加 border / padding 会撑大盒子
* 解决
	* 手动做减法，减掉border / padding 的尺寸
	* 内减模式： box-sizing: border-box

~~代码实现先欠着~~
尽力了，鬼知道他为什么会扭成这样，明明VSCODE里面一切正常的

<div style="position: relative;">
    <div style="width: 400px;height: 400px;border: 1px dashed #000000;background-color: #ffcc80;display: inline-block;position: relative;box-sizing: border-box;">
      <!-- margin 标签和虚线 -->
      <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 1.25%;left: 1.25%;">margin</div>
      <div style="left: 50%; transform: translateX(-50%);position: absolute;font-size: 0.875em;font-weight: bold;color: #333;">|</div>
      <div style="top: 50%; left: 0; transform: translateY(-50%);position: absolute;font-size: 0.875em;font-weight: bold;color: #333;">——</div>
      <div style="top: 50%; right: 0; transform: translateY(-50%);position: absolute;font-size: 0.875em;font-weight: bold;color: #333;">——</div>
      <div style="bottom: 0; left: 50%; transform: translateX(-50%);position: absolute;font-size: 0.875em;font-weight: bold;color: #333;">|</div>
      <div style="width: 250px;height: 250px;background-color: #fff176;position: absolute;top: 50%;left: 50%;transform: translate(-50%, -50%);display: flex;align-items: center;justify-content: center;box-sizing: border-box;">
        <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 2%;left: 2%;color: #f57c00;">border</div>
        <!-- border 数值 -->
        <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 0; left: 50%; transform: translateX(-50%);">|</div>
        <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;bottom: 0; left: 50%; transform: translateX(-50%);">|</div>
        <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 50%; left: 0; transform: translateY(-50%);">—</div>
        <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 50%; right: 0; transform: translateY(-50%);">—</div>
        <div style="width: 200px;height: 200px;border: 0.8% dashed #4caf50;background-color: #c8e6c9;padding: 4%;position: relative;margin: 16% auto;display: flex;align-items: center;justify-content: center;box-sizing: border-box;position: relative;">
          <div style="top: 2.5%;left: 2.5%;color: #388e3c;position: absolute;font-size: 0.875em;font-weight: bold;color: #333;">padding</div>
          <!-- padding 数值 -->
          <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 0; left: 50%; transform: translateX(-50%);">|</div>
          <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;bottom: 0; left: 50%; transform: translateX(-50%);">|</div>
          <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 50%; left: 0; transform: translateY(-50%);">—</div>
          <div style="position: absolute;font-size: 0.875em;font-weight: bold;color: #333;top: 50%; right: 0; transform: translateY(-50%);">—</div>
          <div style="width: 100px;height: 100px;background-color: #81c784;border: 2% solid #2e7d32;display: flex;align-items: center;justify-content: center;font-size: 1.125em;font-weight: bold;color: #1b5e20;position: relative;margin: 45% auto;box-sizing: border-box;">
            <div style="font-size: 1em;font-weight: bold;color: #1b5e20;">200×200</div>
          </div>
        </div>
      </div>
    </div>
  </div>


![[屏幕截图 2025-07-18 204203.png]]

### 盒子模型-外边距
作用：拉开两个盒子之间的距离
属性名：margin
提示：与padding属性值写法、含义相同

margin 设置为auto时，能让元素在父容器中水平居中


### 盒子模型-元素溢出
作用：控制溢出元素的内容的显示方式。
属性名： overflow
属性值：

| 属性值    | 效果                    |
| ------ | --------------------- |
| hidden | 溢出隐藏                  |
| scroll | 溢出滚动（无论是否溢出，都显示滚动条位置） |
| auto   | 溢出滚动（溢出才显示滚动条位置）      |

### 外边距问题-合并现象
场景：垂直排列的兄弟元素，上下margin会合并
现象：取两个margin中的较大值生效

```
.one {
margin-bottom: 50px;
}
.two {
margin-top: 20px;
}
```

### 外边距问题-塌陷问题
场景：父子级的标签，子级的添加上外边距会产生塌陷问题
现象：导致父级一起向下移动
现象如图（灰色为背景板方便观察）：

<div style="background-color: gray;overflow:hidden">
  <div style="background-color: pink; width: 200px; height: 200px; ">
    <div style="background-color: orange; width: 100px; height: 100px; margin-top: 20px;">
      子级div标签
    </div>
    父级div标签
  </div>
</div>

解决方法：
* 取消子级 margin，父级设置 `padding`
* 父级设置 `overflow:hidden`
* 父级设置 `border-top`

效果如图：
<div style="background-color: gray; overflow:hidden">
  <div style="background-color: pink; width: 200px; height: 200px; overflow:hidden">
    <div style="background-color: orange; width: 100px; height: 100px; margin-top: 20px;">
      子级div标签
    </div>
    父级div标签
  </div>
</div>
## 清除默认样式

清除标签默认的样式，比如：默认的内外边距。
方法：
```
* {
  margin: 0;
  padding: 0;
}
```

```
blockquot body, button, dd, dl, dt, fieldset, h4, h5, h6, hr, input, legend, li, text area, th, ul {
      margin: 0;
      padding: O;
    }
```


### 行内元素-内外边距问题
场景：行内元素添加 margin 和 padding, 无法改变元素垂直位置
解决方法：给行内元素添加 line-height 可以改变垂直位置


### 盒子模型-圆角
作用：设置元素的外边框为圆角。
属性名： border-radius
属性值：数字+ p×/百分比

常见应用
* 正圆形状：给正方形盒子设置圆角属性值为 宽高的一半/ 50 ％（最大值是50％。超过50％没有效果）
* 胶囊形状：给长方形盒子设置圆角属性值为 盒子高度的一半


### 盒子模型-阴影（拓展）
作用：给元素设置阴影效果。
属性名：box-shadow
属性值： x 轴偏移量  Y轴偏移量  模糊半径  扩散半径  颜色  内外阴影

注意：
* X轴偏移量和Y轴偏移量必须书写
* 默认是外阴影，内阴影需要添加 inset

## 标准流
标准流也叫文档流，指的是标签在页面中默认排布规则，例如：块元素独占一行/行内元素可以一行显示多个。

## 浮动
作用：让块元素水平排列。
属性名：float
属性值
* 左对齐
* 右对齐

### 清除浮动

场景：浮动元素会脱标，如果父级没有高度，子级无法撑开父级高度（可能导致页面布局错乱）
解决方法：清除浮动（清除浮动带来的影响）

#### 方法一：额外标签法
* 在父元素内容的最后添加一个块级元素设置 CSS 属性` clear: both`

#### 方法二：单伪元素法
```
.clearfix::after {
	content:"";
	display: block;
	clear: both;
}
```
注：一般清除浮动使用`clearfix`类名

#### 方法三：双伪元素法（推荐）
```
.clearfix::before,
.clearfix::after {
	content: "";
	display:table;
}

.clearfix::after {
	clear: both;
}
```

#### 方法四：overflow
* 父元素添加 CSS 属性 `overflow:hidden`

### 总结
* 浮动属性 float ， left 表示左浮动， right 表示右浮动
* 特点：
	1. 浮动后的盒子顶对齐
	2. 浮动后的盒子具备行内块特点
	3. 父级宽度不够，浮动的子级会换行
	4. 浮动后的盒子脱标
* 清除浮动：子级浮动，父级没有高度，子级无法撑开父级高度，影响布局效果
* 拓展：浮动本质作用是实图文混排效果

## Flex浮动
### 认识
Flex布局也叫弹性布局，是浏览器提倡的布局模型，非常适合结构化布局，提供了强大的空间分布和对齐能力。
Flex 模型不会产生浮动布局中脱标现象布局网页更简单、更灵活。


### 组成
设置方式：给父元素设置 display: flex，子元素可以自动挤压或拉伸
组成部分：
* 弹性容器
* 弹性盒子
* 主轴：默认在水平方向
* 侧轴/交叉轴：默认在垂直方向

### 浮动-总结
* 浮动属性 float ，left表示左浮动， right 表示右浮动
* 特点
	1. 浮动后的盒子顶对齐
	2. 浮动后的盒子具备行内块特点
	3. 父级宽度不够浮啲子级会换行
	4. 浮动后的盒子脱标
* 清除浮动：子级浮动，父级没有高度，子级无法撑开父级高度，影响布局效果
		1.  双伪元素法
		 拓展：浮动本质作用是实图文混排效果

### 属性

#### 属性名

| 描述           | 属性                |
| ------------ | ----------------- |
| 创建 flex 容器   | `display: flex`   |
| 主轴对齐方式       | `justify-content` |
| 侧轴对齐方式       | `align-items`     |
| 某个弹性盒子侧轴对齐方式 | `align-self`      |
| 修改主轴方向       | `flex-direction`  |
| 弹性伸缩比        | `flex`            |
| 弹性盒子换行       | `flex-wrap`       |
| 行对齐方式        | `align-content`   |

#### 主轴对齐方式
属性名： `justfy-content`

| 属性值             | 效果                        |
| --------------- | ------------------------- |
| `flex-start`    | 默认值，弹性盒子从起点开始依次排列         |
| `flex-end`      | 弹性盒子从终点开始依次排列             |
| `center`        | 弹性盒子沿主轴居中排列               |
| `space-between` | 弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子之间 |
| `space-around`  | 弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子两侧 |
| `space-evenly`  | 弹性盒子沿主轴均匀排列，弹性盒子与容器之间间距相等 |

#### 侧轴对齐方式
属性名
* `align-items`：当前弹性容器内所有弹性盒子的侧轴对齐方式（给弹性容器设置）
* `align-self`：单独控制某个弹性盒子的侧轴对齐方式（给弹性盒子设置）

| 属性值          | 效果                                     |
| ------------ | -------------------------------------- |
| `stretch`    | 弹性盒子沿着侧轴线被拉伸至铺满容器（弹性盒子没有设置侧轴方向尺寸则默认拉伸） |
| `center`     | 弹性昷子沿侧轴居排列                             |
| `flex-start` | 弹性盒子从起点开始依次排列                          |
| `flex-end`   | 弹性盒子从终点开始依次排列                          |

#### 修改主轴方向
主轴默认在水平方向，侧轴默认在垂直方向
属性名：`flex-direction`
属性值：

| 属性值              | 效果            |
| ---------------- | ------------- |
| `row`            | 水平方向，从左向右（默认） |
| `column`         | 垂直方向，从上向下     |
| `row-reverse`    | 水平方向，从右向左     |
| `colimn-reverse` | 垂直方向，从下向上     |

#### 弹性伸缩比
作用：控制弹性盒子的主轴方向的尺寸
属性名：`flex`
属性值：整数数字，表示占用父级剩余尺寸的份数。

#### 弹性盒子换行
弹性盒子可以自动挤压或拉伸，默认情况下，所有弹性盒子都在一行显示。
属性名： `flex-wrap`
属性值：
* `wrap`：换行
* `nowrap`：不换行（默认）

#### 行对齐方式
属性名：`align-content`
注意：该属性对单行的弹性盒子不生效


## 网页制作
### 项目目录
网站根目录是指存放网站的第一层文件夹，内部包含当前网站的所有素材，包含 HTML 、 CSS 、图片、 JavaScript 等等。

* study
	* image文件夹：存放固定使用的图片素材，例如：logo，样式修饰图等等
	* uploads 文件夹：存放非固定使用的图片素材，例如：商品图、宣传图需要上传的图片
	* css 文件夹：存放 CSS 文件（ link 标签引入）
		* base.css ：基础公共样式，例如：清除默认样式．设萏网页基本样式
		* index.css ：首页 CSS 样式
	* index.html：首页HTML文件

### 网页制作思路
1. 布局思路：先整体再局部，从内到外，从上到下，从左到右
2. CSS实现思路
	1. 画盒子，调整盒子范围 → 宽高背景色
	2. 调整盒子位置 → flex布局，内外边距
	3. 控制图片，文字内容样式

### header区域-布局
通栏：宽度与浏览器窗口相同的盒子
标签结构： 通栏 > 版心 > logo + 导航 + 搜索 + 用户

### logo 制作技巧
logo功能：
* 单击跳转到首页
* 搜索引擎优化：提升网站百度搜索排名
实现方法：
* 标签结构：h1 > a > 网站名称（搜索关键字）
* CSS 样式：
```
.logo a {
	dispaly: block;
	width: 195px;
	height: 41px;
	background-image: url(../iamges/logo.png);
	/* 隐藏文字 */
	font-size: 0;
}
```