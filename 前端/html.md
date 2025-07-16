## 文本格式化
#### 代码
strong加粗、emphasize倾斜、insert下划线、delete删除线
```
  <strong>strong是加粗的字体(强调)</strong>
  <b>b是加粗的字体</b>
  <em>em/i是倾斜的字体(强调)</em>
  <i>i是倾斜的字体</i>
  <ins>ins是下划线(强调)</ins>
  <u>u是下划线</u>
  <del>del是删除线(强调)</del>
  <s>s是删除线</s>
```
#### 展示效果

**strong是加粗的字体(强调)**<br>
**b是加粗的字体**<br>
*em/i是倾斜的字体(强调)*<br>
*i是倾斜的字体*<br>
<u>ins是下划线(强调)</u><br>
<u>u是下划线</u><br>
~~del是删除线(强调)~~<br>
~~s是删除线~~<br>

## 图片标签img
#### 标签
```
<img src="">
```
#### 属性

| 属性     | 作用    | 说明                |
| ------ | ----- | ----------------- |
| alt    | 替换文本  | 图片无法显示的时候显示的文字    |
| title  | 提示文本  | 鼠标悬停在图片上面的时候显示的文字 |
| width  | 图片的宽度 | 值为数字，没有单位         |
| height | 图片的高度 | 值为数字，没有单位         |

## 音频标签audio
#### 标签
```
<audio src=""></audio>
```

#### 属性

| 属性        | 作用       | 特殊说明                    |
| --------- | -------- | ----------------------- |
| src（必须属性） | 视频URL    | 支持格式：MP3,Ogg,Wav        |
| controls  | 显示音频控制面板 |                         |
| loop      | 循环播放     |                         |
| autoplay  | 自动播放     | 为了提升用户体验，浏览器一般会禁用自动插放功能 |

在 HTML5 里面 ，如果属性名和属性值完全一致，可以简写为一个单词。比如
```
<audio src="" control></audio>
```


## 视频标签video
#### 标签
```
<video src=""></video>
```

#### 属性

| 属性        | 作用       | 特殊说明                    |
| --------- | -------- | ----------------------- |
| src（必须属性） | 视频URL    | 支持格式：MP4,WebM,Ogg       |
| controls  | 显示视频控制面板 |                         |
| loop      | 循环播放     |                         |
| muted     | 静音播放     |                         |
| autoplay  | 自动播放     | 为了提升用户体验，浏览器支持在静音状态自动插放 |

## 超链接
#### 标签
```
<a href="#"></a>
```
使用#号进行占位操作

#### 展示效果

<a href="www.baidu.com">跳转百度</a>
#### 属性
`target="_blank"`在新界面打开网页

## 列表

### 无序列表
作用：布局排列整齐的不需要规定顺序的区域。<br>
标签：ul嵌套li，ul是无序列表 ，li是列表条目。
#### 标签
```
<ul>
    <li>example</li>
    <li>example</li>
    <li>example</li>
    <li>example</li>
    <li>example</li>
    <li>example</li>
  </ul>
```

#### 展示效果
* example
* example
* example
* example
* example
* example
* example

### 有序列表
作用：布局排列整齐的需要规定顺序的区域。<br>
标签： ol嵌套 li, ol是有序列表，li是列表条目。

#### 标签
```
<ol>
    <li>example</li>
    <li>example</li>
    <li>example</li>
    <li>example</li>
    <li>example</li>
    <li>example</li>
  <ol>
```

#### 展示效果
1. example
2. example
3. example
4. example
5. example
6. example

### 定义列表
标签： dl嵌套 dt 和 dd ，dl 是定义列表，dt 是定义列表的标题，dd 是定义列表的描述/详情。

#### 标签
```
<dl>
  <dt>title1</dt>
  <dd>test1</dd>
  <dd>test2</dd>
  <dt>title2</dt>
  <dd>example1</dd>
  <dd>example2</dd>
</dl>
```
#### 展示效果
![[{C2BFBE84-E3B6-4E2E-8F2D-3B1448E9C3EC}.png]]

## 表格
#### 标签
table 嵌套 tr, tr 嵌套 td /th。

| 标签名   | 说明    |
| ----- | ----- |
| table | 表格    |
| tr    | 行     |
| th    | 表头单元格 |
| td    | 内容单元格 |

```
<table>
  <tr>
    <th>姓名</th>
    <th>年龄</th>
    <th>班级</th>
  </tr>
  <tr>
    <td>张三</td>
    <td>18</td>
    <td>软工一班</td>
  </tr>
  <tr>
    <td>李四</td>
    <td>16</td>
    <td>大数据一班</td>
  </tr>
</table>
```

#### 展示效果

| 姓名  | 年龄  | 班级    |
| --- | --- | ----- |
| 张三  | 18  | 软工一班  |
| 李四  | 16  | 大数据一班 |

#### 表格结构标签
作用：用表格结构标签把内容划分区域，让表格结构更清晰，语义更清晰。<br>
（给浏览器读的，与用户无关）

| 标签名   | 含义   | 特殊说明   |
| ----- | ---- | ------ |
| thead | 表格头部 | 表格头部内容 |
| tbody | 表格主体 | 主要内容区域 |
| tfoot | 表格底部 | 汇总信息区域 |

#### 合并单元格
合并单元格的步骤：
1. 明确合并的目标
2. 保留最左最上的单元格，添加属性（取值是数字，表示需要合并的单元格数量）
		跨行合并，保留**最上**单元格，添加属性`rowspan`
		跨列合并，保留**最左**单元格，添加属性`colspan`
3. 删除其他单元格

## 表单
### input
#### 标签
```
<input type="...">
```

#### 展示效果

根据属性不同效果不同
![[Pasted image 20250709215253.png]]
![[{82755516-F1FA-4FEE-998E-656D665875AE}.png]]

#### 类型

| type属性值  | 说明           |
| -------- | ------------ |
| text     | 文本框，用于输入单行文本 |
| password | 密码框          |
| radio    | 单选框          |
| checkbox | 多选框          |
| file     | 上传文件         |

#### input其他属性

###### placeholder
用于在文本框中预显示文字

##### 单选框radio

| 属性名     | 作用   | 特殊说明                |
| ------- | ---- | ------------------- |
| name    | 控件名称 | 控件分组，同组只能选中一个（单选功能） |
| checked | 默认选中 | 属性名和属性值相同，简写为一个单词   |

##### 多选框checkbox
| 属性名     | 作用   | 特殊说明              |
| ------- | ---- | ----------------- |
| checked | 默认选中 | 属性名和属性值相同，简写为一个单词 |
###### 文件上传file
| 属性名      | 作用    | 特殊说明              |
| -------- | ----- | ----------------- |
| multiple | 多文件上传 | 属性名和属性值相同，简写为一个单词 |


### 下拉菜单
标签： select 嵌套 option, select 是下拉菜单整体，option 是下拉菜单的每一项。
#### 标签
```
<select>
  <option>北京</option>
  <option>上海</option>
  <option>重庆</option>
  <option>四川</option>
  <option>哈尔滨</option>
</select>
```

#### 展示效果

<select>
  <option>北京</option>
  <option>上海</option>
  <option>重庆</option>
  <option>四川</option>
  <option>哈尔滨</option>
</select>

#### 属性
| 属性名      | 作用   |
| -------- | ---- |
| selected | 默认选中 |


### 文本域textarea
可进行多行文本输入
#### 标签
```
<textarea>默认提示词</textarea>
```

#### 展示效果
<textarea>默认提示词</textarea>

### label标签
增大点击范围。 <br>
支持 label 标签增大点击范围的表单控件：文本框、密码框、上传文件、单选框、多选框、下拉菜单、文本域等等。

#### 写法一
* label 标签只包裹内容，不包裹表单控件
* 设置 label 标签的 for 属性值和表单控件的 id 属性值相同

```
<inpu type="radio" name="gender" id="male">
<label for="male">男</label>
<input type="radio" name="gender" id="famale">
<label for="famale">女</label>
```

<input type="radio" name="gender1" id="male">
<label for="male">男</label>
<input type="radio" name="gender1" id="famale">
<label for="famale">女</label>

#### 写法二
直接使用 label 标签包裹文字和表单控件，不需要属性
```
<label><input type="radio" name="gender" id="male">男</label>
<label><input type="radio" name="gender" id="famale">女</label>
```

<label><input type="radio" name="gender2" id="male">男</label>
<label><input type="radio" name="gender2" id="famale">女</label>


### 按钮button
#### 标签

```
<button type="">按钮</button>
```

#### 属性

| type属性值 | 说明                             |
| ------- | ------------------------------ |
| submit  | 提交按钮，点击后可以提交数据到后台（默认功能）        |
| reset   | 重置按钮，点击后将表单控件恢复默认值             |
| button  | 普通按钮，默认没有功能，一般配合 JavaScript 使用 |
#### 展示效果

<button type="submit">按钮</button>


### form标签
用来规定表单的区域，方便reset

## 布局标签
作用：布局网页（划分网页区域，摆放内容）
### div标签
双标签，独占一行

#### 标签
```
<div>双标签，独占一行</div>
<div>双标签，独占一行</div>
```

#### 展示效果
<div>双标签，独占一行</div>
<div>双标签，独占一行</div>

### span标签
双标签，不换行
#### 标签
```
<span>双标签，不换行</span>
<span>双标签，不换行</span>
```

#### 展示效果
<span>双标签，不换行</span><span>双标签，不换行</span>


## 字符实体
作用：在网页中显示预留字符。

| 显示结果 | 描述  | 实体名称    |
| ---- | --- | ------- |
|      | 空格  | \&nbsp; |
| &lt; | 小于号 | \&lt;   |
| &gt; | 大于号 | \&gt;   |
