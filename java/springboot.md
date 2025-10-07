# 三层架构
**controller**：控制层，接收前端发送的谲求，对请求进行处理．并响应数据。
**services**：业务逻辑层，处理具体的业务逻辑。
**dao**：数据访问层（Data Access 0bject) （持久层），负责数据访问操作，包括数据的增、删、改、查。

## 分层解耦

**控制反转**：`Inversron Of Control`，简称IOC。对象的创建控剩权由程序自身转哆到外部（容器），这种思想称为控制反转。
**依赖注入**：`Dependency lnjection`, 简称DI。容器为应用程序提供运行时所依賴的资源，称之为依赖注入。
**Bean对象**：IOC容器中创建、管理的对象，称之为`Bean`

## 注解
### 分层解耦
**`@Bean`** 是 Spring 框架中的一个重要注解，主要用于将方法返回的对象注册为 Spring 容器中的一个 Bean 实例，由 Spring 容器进行管理。带impl后缀的是实现类

**`@Component`**：将当前类交给IOC容器管理
`@Component`的衍生注解：
* **`@Controller`**:标注在控制层类上
* **`@service`**：标注在业务层类上
* **`@Repository`**：标注在数据访问层类上（由于与mybatis整合，用的少）
**`@autowired`**：从IOC容器中找到对应类型的bean并完成依赖注入

### SpringBoot配置

**`@Value`**：将配置文件中对应的属性值注入到一个Bean的字段上。使用时，直接在需要注入值的字段上添加该注解，并指定配置文件中属性的键名。
```
@Component
public class MyComponent { 
	@Value("${myapp.name}")
	private String appName;
}
//如果配置文件中有myapp.name=myApp的配置，那么appName字段就会被注入对应的值。
```
**`@ConfigurationProperties​​`**：将配置文件中的属性批量绑定到一个Java对象上。
	

**`@Mapper`**
```
@Mapper
public interface UserMapper {
	@Select("SELECT * FROM user WHERE id = #{id}")
	User getUserById(int id);
	
	@Insert("INSERT INTO user(name, age) VALUES(#{name}, #{age})")
	void insertUser(User user);
}
```
在这个例子中， `UserMapper` 接口被 `@Mapper` 注解标记后， MyBatis 会自动处理该接口，开发者可以直接通过依赖注入等方式使用该接口的实例来操作数据库，而无需手动编写实现类。

另外，在 `SpringBoot` 项目中，除了在每个 Mapper 接口上添加`@Mapper`注解外，还可以通过在配置类上添加 `@MapperScan` 汪解来仳量扫庙指定包下的所有 Mapper 接口，这样就无需在每个接口上单独添加 `@Mapper` 注解了。


**`@Bean`** 是 Spring 框架中的一个重要注解，主要用于将方法返回的对象注册为 Spring 容器中的一个 Bean 实例，由 Spring 容器进行管理。

**`@Configuration`** 是 Spring 框架中的核心注解之一，用于标记一个类作为**配置类**


**`@Resource`**
1. **与 `@Autowired` 的区别**：
    
    - `@Autowired` 是 Spring 注解，默认按类型匹配，需配合 `@Qualifier` 指定名称
    - `@Resource` 是 JDK 注解，默认按名称匹配，无需额外注解即可指定名称
    - `@Resource` 不支持 `required` 属性（而 `@Autowired(required = false)` 可设置非必须注入）

@RequstBody以json格式提交

@RequestMapping 全局设置前端参数
@PostMapping 设置前端参数

@RequiredArgsConstructor 对全局需要在初始化阶段注入的函数注入

@ApiParam 为 API 的某个参数（通常是方法参数）添加元数据，使得在自动生成的 API 文档中，该参数能够有更清晰的说明，包括名称、是否必填、默认值、描述信息等。


@ComponentScan 用于告诉 Spring 扫描指定包及其子包下的组件（如被 `@Component`、`@Service`、`@Repository`、`@Controller`等注解标记的类），并将这些组件注册到 Spring 容器中，以便在应用程序中进行依赖注入和其他 Spring 相关的操作,已在@SpringBootApplication中集成

#### Bean注册
如果要注册的 bea n 对象来自于第三方（不是自定义的），是无法用 `@Component` 及衍生注解声明 bean 的
```
@SpringBootApplication
public class SpringBootRegisterApplication {
	@Bean
	public Resolver resolver(){
		return new Resolver();
	}
}
```
实际上，不建议在启动项中最直接注册，而是在配置类中集中注册
```
@Configuration
public class CommonConfig {
	@Bean
	public Resolver resolver(){
		return new Resolver();
	}
}
```

@Configuration

@Import 当一个配置类需要依赖另一个配置类中的Bean时，可直接导入目标配置类，无需再给目标类加 @ComponentScan 扫描。


@Import



| 注解                        | 说明                         |
| ------------------------- | -------------------------- |
| @ConditionalOnProperty    | 配置文件中存在对应的属性，才声明该 bean     |
| @ConditionalOnMissingBean | 当不存在当前类型的 bean 时，才声明该 bean |
| @ConditionalOnClass       | 当前环境存在指定的这个类时，才声明该 bean    |


@ConditionalOnProperty
@ConditionalOnMissingBean
@ConditionalOnClass

@Transactional
- 当 `addEmployee()`方法被调用时，Spring 会为这个方法开启一个数据库事务。
    
- 方法内所有的数据库操作（比如通过 MyBatis 执行的 insert/update/delete）都会在 ​**​同一个事务上下文中执行​**​。
    
- 如果方法 ​**​正常执行完毕（没有抛出异常）​**​，事务会 ​**​自动提交​**​。
    
- 如果方法 ​**​抛出了异常（默认是 RuntimeException 或 Error）​**​，事务会 ​**​自动回滚​**​。