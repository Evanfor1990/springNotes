## Spring

### 目录结构

```
- src
	- main
		- java 代码
		- resource 资源、配置文件
	- test 
		- java 测试
```



### 启动流程

#### 1. prepareEnvironment

主要构造Environment,是全局的参数、如命令行输入的参数、配置文件的参数。

#### 2. prepareContext

主要是初始化Context，如设置资源（路径）；配置BeanFactory，如Convert（如时间转Date类）等

#### 3. refreshContext

1. 添加内置的处理器，并执行。
2. 完成BeanDefinition（包括Processor）定义。
3. 根据BeanDefinition生成实例



### Profile 实现

### 国际化和本地化

### 重要的类

### Listener &　Event

### 常用的注解

**@Configuration**

标识这个类代表一种配置（工厂类），有专门的**Configuration Processor**处理

[proxyBeanMethods](https://stackoverflow.com/questions/61266792/when-to-set-proxybeanmethods-to-false-in-springs-configuration)



**@Import**

导入一个Bean，通常是一个Configuration。当一个Configuration不能被注入容器时（比如不在扫描路径下时）可以使用这个方法注入。



**@Indexed**

编译时生成索引文件 ***METE-INF/spring.components*** 方便查找需要的类，避免扫描大量的目录来查找需要的类(***@CompoentScan***)。需要 ***org.springframework:spring-context-indexer***  支持。

**@AliasFor**

* 成对使用 value 和 path 是相同的含义

```java
   @AliasFor("path")
      String[] value() default {};
  
      @AliasFor("value")
      String[] path() default {};
```

* 等价于```Configuration```中的```proxyBeanMethods```

```java
@AliasFor(annotation = Configuration.class)
boolean proxyBeanMethods() default true;
```

**@Component**

### 代码织入

### 日志

### 认证 Spring Security

####  权限设置



## Mysql

### 常用命令

* show tables;

### 并发与锁

### 执行计划

> explain

## Mybatis

## Redis

## Mongodb

**配置**
```xml
// application.properties
spring.data.mongodb.database=  MongoTemplate 默认使用的数据库
spring.data.mongodb.uri=mongodb://user:pass@host:port/admin
```

