# Csis2NetWebMng记录

---

## 典型问题记录

1. Log4j-to-slf4j.jar（包含在spring-boot-starter-amqp依赖中） 依赖和 slf4j-log4j-iml.jar 冲突

   需要修改pom.xml文件，在spring-boot-starter-amqp中exclude掉Log4j-to-slf4j：

   ```xml
   <dependency>
               <groupId>org.springframework.boot</groupId>
               <artifactId>spring-boot-starter-amqp</artifactId>
               <exclusions>
                   <exclusion>
                       <groupId>org.apache.logging.log4j</groupId>
                       <artifactId>log4j-to-slf4j</artifactId>
                   </exclusion>
               </exclusions>
               <version>2.1.6.RELEASE</version>
           </dependency>
   ```

   

2. java.lang.ClassNotFoundException: org.apache.jsp.WEB_002dINF.pages.result.index_jsp

   在相应的jsp文件中注释掉：

   ```jsp
   <%--<%=username %>--%>
   ```

   

3. 查看shiro框架

4. 出现网络问题的时候，看看是不是代理的问题（比如开了全局）

5. 添加了css或js后，要相应地在 common-css.jsp 或者 common-javascript.jsp 中引用（调试树形选择框时记录）



## TODO

- bug：点很多页面总会请求 /404

## 进展

### 9-11

- 实现登陆功能，登陆界面，md5加密，shiro框架，考虑DES加密



## 未解决问题记录

1. shiro框架怎么支持des验证？



## 疑惑



## 待沟通

- 部门管理设计成这个样子行不行？

  - 不行，要做成树状结构

- 客户端包管理 建立一个download目录，下面放ini文件，在界面上可以进行修改？

  - 是的，只会会给一个表结构，做一个更改表结构（主要是部门）的界面

  



