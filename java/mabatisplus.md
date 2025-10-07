## 引入
1. 使用maven引入mybatisPlus依赖
```
<dependency>  
    <groupId>com.baomidou</groupId>  
    <artifactId>mybatis-plus-boot-starter</artifactId>  
    <versionn>3.5.3.1</version>
</dependency>
```

2. 定义Mapper接口并继承BaseMapper
```
public interface UserMapper extends BaseMapper<User> {

}
```

# 常见注解

**@Data**：MyBatisPlus通过扫描实体类，并基于反射获取实体类信息作为数据库表信息
注：
* 类名驼峰转下划线作为表名
* 名为id的字段作为主键
* 变量名驼峰转下划线作为表的字段名

**@TableName**：用来指定表名

**@TableId**：用来指定表中的主键字段信息
IdType枚举：
* AUTO：数据库自增长
* INPUT：通过set方法自行输入
* ASSIGN_ID：使用接口identifierGenerator的方法nextId来生成id。默认实现类为DefaultIdentifierGenerator雪花算法

**@TableField**：用来指定表中的普通字段信息
使用@TableField的常用场景
* 成员变量名与数据库段名不一致
* 成员变量名以is开头，且是布尔值
* 成员变量名与数据库关键词冲突
* 成员变量不是数据库字段

<table>
  <caption>名称：tb_user   注释：用户表</caption>
  <tr>
    <th>#</th>
    <th>名称</th>
    <th>数据类型</th>
    <th>注释</th>
    <th>默认</th>
  </tr>
  <tr>
    <td>1</td>
    <td>id</td>
    <td>BIGINT</td>
    <td>用户id</td>
    <td>AUTO_INCREMENT</td>
  </tr>
  <tr>
    <td>2</td>
    <td>username</td>
    <td>VARCHAR</td>
    <td>用户名</td>
    <td>无默认值</td>
  </tr>
  <tr>
    <td>3</td>
    <td>is_married</td>
    <td>BIT</td>
    <td>密码</td>
    <td>0</td>
  </tr><tr>
    <td>4</td>
    <td>order</td>
    <td>TINYINT</td>
    <td>序号</td>
    <td>NULL</td>
  </tr>
</table>
![[{EBC4016C-1735-4D10-80FF-97CB2FED89C2}.png]]


## 条件构造器
* `QuerWrapper`和`LambdaQueryWrapper`通常用来构建`select`、`delete`、`update`、`where`条件部分
* `UpdateWrapper`和`LambdaUpdateWrapper`通常只有在set语句比较特殊才使用
* 尽量避免`LambdaQueryWrapper`和`LambdaUpdateWrapper`,避免硬编码


