## 异常
异常种类：
1. 运行时异常（RuntimeException）
2. 编译时异常


## 异常处理
### 抛出异常
在方法上使用throws关键字，可以将方法内部出现的异常抛出去给调用者处理

如果不做处理，程序会直接退出

### 捕获异常
使用try…catch语句捕获异常

抛出异常后程序会继续运行，不会提出
## 自定义异常

#### 泛型方法
语法：
```
修饰符 <类型变量, 类型变量, ...> 返回值类型 方法名(形参列表){
}
```

举例：
```
public static <T> void test(T t) {
}
```

通配符：就是"?" ，可以在“使用泛型”的时候代表一切类型；E T K V 是在定义泛型的时候使用。
泛型的上下限：
* 泛型上限：`?extend Car`：?能接收的必须是Car或者其子类
* 泛型下限：`?super Car`：?能接收的必须是Car或者其父类
## 泛型

## Collection

## List

## Set

## Map

## Stream流

![img](https://www.runoob.com/wp-content/uploads/2013/12/iostream2xx.png)
图片来自菜鸟教程
### 字符流
使用`BufferedReader`方法读取字符
```
// 读取单个字符
char c;
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
c = (char) br.read();
```

现在，一般使用Scanner方法读取输入
### 字节流

| 类名                      | 类型        | 描述                                                |
| ----------------------- | --------- | ------------------------------------------------- |
| `InputStream`           | 抽象类 (输入流) | 所有字节输入流的超类，处理字节的输入操作。                             |
| `OutputStream`          | 抽象类 (输出流) | 所有字节输出流的超类，处理字节的输出操作。                             |
| `FileInputStream`       | 输入流       | 从文件中读取字节数据。                                       |
| `FileOutputStream`      | 输出流       | 将字节数据写入文件。                                        |
| `BufferedInputStream`   | 输入流       | 为字节输入流提供缓冲功能，提高读取效率。                              |
| `BufferedOutputStream`  | 输出流       | 为字节输出流提供缓冲功能，提高写入效率。                              |
| `ByteArrayInputStream`  | 输入流       | 将内存中的字节数组作为输入源。                                   |
| `ByteArrayOutputStream` | 输出流       | 将数据写入到内存中的字节数组。                                   |
| `DataInputStream`       | 输入流       | 允许从输入流中读取 Java 原生数据类型（如 `int`、`float`、`boolean`）。 |
| `DataOutputStream`      | 输出流       | 允许向输出流中写入 Java 原生数据类型。                            |
| `ObjectInputStream`     | 输入流       | 从输入流中读取序列化对象。                                     |
| `ObjectOutputStream`    | 输出流       | 将对象序列化并写入输出流中。                                    |
| `PipedInputStream`      | 输入流       | 用于在管道中读取字节数据，通常与 `PipedOutputStream` 配合使用。        |
| `PipedOutputStream`     | 输出流       | 用于在管道中写入字节数据，通常与 `PipedInputStream` 配合使用。         |
| `FilterInputStream`     | 输入流       | 字节输入流的包装类，用于对其他输入流进行过滤处理。                         |
| `FilterOutputStream`    | 输出流       | 字节输出流的包装类，用于对其他输出流进行过滤处理。                         |
| `SequenceInputStream`   | 输入流       | 将多个输入流串联为一个输入流进行处理。                               |

## File

## 字符集

## IO流

## 多线程

## 线程安全

## 线程池

[^1]: 
