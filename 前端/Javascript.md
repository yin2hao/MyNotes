NaN 不等于任何人，包括他自己


# JS执行机制
1. 先执行执行栈中的同步任务。
2. 异步任务放入任务队列中。
3. 一旦执行栈中的所有同步任务执行完毕，系统就会按次序读取任务队列中的异步任务，于是被读取的异步任务结束等待

# BOM

## 延迟函数
### 设置
JavaScript 内置的一个用来让代码延迟执行的函数，叫 setTimeout
* 语法：
	`setTimeout (回调函数， 延迟时间)`
* setTimeout 仅仅只执行一次，所以可以理解为就是把一段代码延迟执行, 平时省略window

### 清除
```
let timer = setTimeout (回调函数， 延迟时间)
clearTimeout(timer)
```
注意点：
* 延时器需要等待,所以后面的代码先执行
* 每一次调用延时器都会产生一个新的延时器

## location
### location.href
href 属性获取完整的 URL 地址，对其赋值时用于地址的跳转
### location.search
 search 属性获取地址中携带的参数，符号 ？后面部分
### location.hash
hash 属性获取地址中的啥希值，符号 # 后面部分
### location.reload
reload 方法用来刷新当前页面，传入参数 true 时表示强制刷新
```
loaction.reload()
```
强制刷新无视本地缓存，直接从服务器获取最新网页


## navigator
获取浏览器信息
如：
```
// 获取浏览器UA
const userAgent = navigator.userAgent
```


## history

| history对象方法 | 作用                                     |
| ----------- | -------------------------------------- |
| back()      | 后退                                     |
| forword()   | 前进                                     |
| go(参数)      | 前进后退功能参数如果是 1 前进 1 个页面如果是 -1  后退 1 个页面 |


## 本地存储
### localStorage
特点：
* 永久存储在本地
* 以键值对的形式存储使用
用法：
* 存储数据：`localStorage.getItem(key)`
* 获取数据：`localStorage.removeItem(key)`
* 删除数据：`localStorage.removeItem(key)`

### sessionStorage
特点：
* 生命周期为关闭浏览器窗口
* 在同一个窗口(页面)下数据可以共享
* 以键值对的形式存储使用
* 用法跟localStorage 基本相同
用法：
* 存储数据：`sessionStorage.getItem(key)`
* 获取数据：`sessionStorage.removeItem(key)`
* 删除数据：`sessionStorage.removeItem(key)`

### 存储复杂数据类型
使用 `JSON.stringify()` 将复杂数据类型转化为JSON字符串存储
使用 `JSON.parse()` 将JSON字符串转化回复杂数据类型


## map和join
map() 可以处理数据，并且返回新的数组
join() 方法用于把数组中的所有元素转换一个字符串


## 正则表达式
### test方法
test 方法用于判断是否有符合规则的字符串，返回的是布尔值找到返回 true, 否则 false
```
const str = "我们在学习前端，希望学习前端能高薪毕业"
const reg = /前端/  //正则表达式式子
console.log(reg.test(str)) //ture
```

### exec方法
exec 方法用于检索（查找）符合规则的字符串，找到返回数组，否则为 null
```
const str = "我们在学习前端，希望学习前端能高薪毕业"
const reg = /前端/  //正则表达式式子
console.log(reg.test(str))
//打印一个字符串
```

### replace
```
字符串.replace(/正则表达式/, 替换的文本)
```


# js进阶
## 函数进阶
### 不定数量形参
#### 动态参数
arguments 是函数内部内置的伪数组变量，它包含了调用函数时传入的所有实参
```
function sum() {
  let s = 0
  for(let i = 0; i < arguments.length; i++) {
    s += arguments[i]
  }
  console.log(s)
}
sum(5,10)
sum(1,2,4)
```

1. arguments 是一个伪数组，只存在于函数中
2. arguments 的作用是动态获取函数的实参
3. 可以通过for循环依次得到传递过来的实参

#### 剩余参数
剩余参数允许我们将一个不定数量的参数表示为一个数组
```
function config(baseURL, ...other) {
  console.log(baseURL)
  console.log(other)
}
config('http://baidu.com', 'get', 'json')
```

1. `...` 是语法符号，置于最末函数形参之前，用于获取多余的实参
2. 借助 `...` 获取的剩余实参，是个真数组

### 展开运算符
展开运算符`...`,将一个数组进行展开，不会修改原数组
```
const arr = [1,2,3,4,5]
console.log(...arr) // 1 2 3 4 5
```


### 箭头函数
类似java的拉姆达表达式
```
const fn = () => {
  console.log()
}
```

形参放在小括号处
形参只有一个，小括号可省略
只有一行代码的时候，我们可以省略大括号和return语句
```
const fn = x => x + x
console.log(fn(1)) // 值为2
```

箭头函数可以直接返回一个对象
```
const fn = (uname) => ({uname: uname})
fn('刘德华')
```

***箭头函数没有argumrnts动态参数，但是有剩余参数`...args`***
***箭头函数不会创建自己的this，它只会从自己的作用域的上一层沿用this***

### 数组解构
基本语法：
1. 赋值运算符 = 左侧的 [] 用于批量声明变量，右侧数组的单元值将被赋值给左侧的变量
2. 变量的顺序对应数组单元值的位置依次进行赋值操作

```
const arr = [1,2,3]
const [a,b,c] = arr
console.log(a)
console.log(b)
console.log(c)
```
或者
```
const [a,b,c] = [1,2,3]
console.log(a)
console.log(b)
console.log(c)
```

**注意**：变量多，单元值少的情况：
```
const [a, b, c, d] = ['小米', '苹果', '华为']
console.log(a) // 小米
console.log(b) // 苹果
console.log(c) // 华为
console.log(d) // undefined
```
3. 交换2个变量   
```
let c = 1
let d = 3; //这里必须有分号
[b, a] = [c, d]
console.log(a)
console.log(b)
```

**注意**：js 前面必须加分号情况
* 立即执行函数
```
(function t() { })();
// 或者
;(function t() { })()
```
* 数组解构
	如上
3. 利用剩余参数解决变量少，单元值多的情况
```
const [a, b, ...tel] = ['小米', '华为', '苹果', '格力', 'vivo']
console.log(a) // 小米
console.log(b) // 苹华为
console.log(tel) // ['苹果', '苹果', '格力', 'vivo']
```
剩余参数返回的还是一个数组
4. 防止有undefined传递单元值的情况，可以设置默认值：
```
const [a = '手机'， b = '华为'] = ['小米']
console.log(a) // 小米
console.log(b) // 华为
```
允许初始化变量的默认值，且只有单元值为 undefined 时默认值才会生效

5. 按需导入，忽略某些返回值
```
const [a, , c, d] = ['小米', '苹果', '华为', '格力']
console.log(a) // 小米
console.log(c) // 华为
console.log(d) //格力
```

6. 支持多维数组的结构：
```
const [a,b] = ['苹果'， ['小米','华为']]
console.log(a) // 苹果
console.log(b) // ['小米','华为']
```
```
const [a,[b,c]] = ['苹果'， ['小米','华为']]
console.log(a) // 苹果
console.log(b) // 小米
console.log(c) // 华为
```

### 对象解构
对象解构是将对象属性和方法快速批量赋值给一系列变量的简洁语法

* 基本语法：
1. 赋值运算符 = 左侧的 {} 用于批量声明变量，右侧对象的属性值将被赋值给左侧的变量
2. 对象属性的值将被赋值给与属性名相同的变量
3. 注意解构的变量名不要和外面的变量名冲突否则报错
4. 对象中找不到与变量名一致的属性时变量值为 undefined
```
const user = {
	name: '小明',
	age: 18
};
const {name, age} = user

console.log(name) // 小明
console.log(age) // 18
```

* 给新的变量名赋值：可以从一个对象中提取变量并同时修改新的变量名
```
const user = {
	name: '小明',
	age: 18
};
const {name: uname, age} = user

console.log(name) // 小明
console.log(age) // 18
```

* 数组对象解构
```
const pig = [
	{
		name: '佩奇'，
		age: 6
	}
]
const [{name, age}] = pig
console.log(name,age)
<<<<<<< HEAD
```
=======
```

this is pull test text



>>>>>>> mynotes/master
