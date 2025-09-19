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