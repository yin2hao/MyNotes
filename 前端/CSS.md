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



### 复合选择器
定义：两个或多个基础选择器通过不同的方工组而成。<br>
作用：更准确、更高效的选择目标元素（标签）。

#### 后代选择器
后代选择器：选中某元素的后代元素。<br>
选择器写法：父选择器 子选择器 {css属性}，父子选择器之间用空格隔开。

#### 子代选择器
子代选择器：选中某元素的子代元素（最近的子级）。<br>
选择器写法：父选择器 > 子选择器{CSS属性}，父子选择器之间用 > 隔开。

#### 并集选择器
并集选择器：选中多组标签，设相同的样式。<br>
选择器写法：选择器1,选择器2,……选择器N {CSS属性}，选择器之间用`,`隔开。

```

```