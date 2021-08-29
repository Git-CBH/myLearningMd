# 	Java三阶段

> @author：HB、ocean
>
> @time：2021-7-5 => 2021-8-24 （37 天）

## 大纲

三部分：SSM、第四阶段做准备SpringBoot等、整合小项目

15年经验的老师 家乡邯郸

![image-20210705094513452](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705094513452.png)

![image-20210705094834810](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705094834810.png)

![image-20210705094931917](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705094931917.png)

![image-20210705094942828](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705094942828.png) `

![](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705094931917.png)

## 开始学习

### Day01

#### Maven工具

1. 什么是maven？

  maven是Apache基金会管理的项目，开源的。

  maven是**自动化构建**工具。

  1）自动化---给出命令，maven可以根据给出的命令实现操作

  2）构建---将项目所需要的原材料，生产加工成为可以被运行和使用的项目的过程（JDBC（JAR、DbUtils）、数据库、前端、连接池）

  3）项目的原材料：静态和动态的两部分。静态：html、css、js、图片、音频、视频、flash动画、gif动图；动态：servlet、jsp、代码、配置文件（不能直接访问的、放在web-info、classpath类路径下）

2. maven的作用？

  1）自动化构建

  2）实现jar包的管理

  3）实现项目结构设计

3. maven官网

  1）https://maven.apache.org/

4. 下载和安装

  1）下载位置

  http://archive.apache.org/dist/ （apache基金会项目档案目录）

  2021.4.4 maven 3.8.1 

  注意：jdk1.8 和 开发工具支持什么版本

  2）安装

  A、maven的条件：jdk安装、maven安装路径不能有中文和空格

  B、解压即用，配置环境变量，可能需要初始化配置

  环境变量 配置MAVEN_HOME 和Path  ;%MAVEN_HOME%/bin;

  测试安装 mvn -v 是否配置完成

  C、初始化 --- 如果都不配置，均使用默认配置方式

  镜像配置、jdk版本配置、本地仓库配置

  本地库配置（默认配置：C/Users/Adminstrator/.m2/repository（默认用户家目录））

  路径不含有中文和空格 maven路径 conf/settings

  配置localRepositiory

  镜像配置

  常见：阿里、华为

  阿里云maven镜像 https://maven.aliyun.com/mvn/guide

  配置mirror

  jdk版本(默认情况下，使用创建maven项目时，jdk版本默认1.5)

  配置profile

5. maven的仓库

  1）存储内容---jar包

  2）本地库和远程库

  3）本地库：当前所使用的电脑中的路径

  4）远程库：中央库、镜像库、私服

  A、中央库：maven世界下的中心仓库 **默认**

  B、镜像库：是中央库的副本 国内镜像目的提高下载速度

  C、私服：局域网内的路径 （公司内部共用的仓库 指定的计算机 网络链接下载JAR包）

  ![image-20210705111353483](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705111353483.png)

6. 要使用maven工具、那么遵守工具的一些规则

  1）创建项目时，项目的目录结构规则

  ![image-20210705113926820](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705113926820.png)

  ![image-20210705114235610](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705114235610.png)

  2）pom.xml 文件

  A、pom---project object model 项目对象模型，对使用maven工具创建的项目进行了相关的定义，是maven项目的核心，在pom.xml文件中可以定义？

  B、可以定义项目的打包方式、相关依赖、当前项目坐标（GAV）、jar包统一管理、相关插件配置等

  3）坐标

  用于确定jar包在仓库中的唯一位置的组成（groupId、artifactId、version）

7. maven的使用

   1）和其他工具整合使用，比如和eclipse整合、和idea整合

   2）eclipse 或者 idea 负责准备项目的原材料；maven项目的结构设计、jar包的管理、项目自动化构建；分工协作

   3）idea工具和maven工具的整合

   settings---bulid---build tools---maven

   设置maven home directory

   设置 settings files

   设置 local repository

   4）使用 idea+maven 创建项目（在 idea 整合 maven 之后使用综合性质的工具创建项目），只是借助了maven，符合 maven 要求的目录结构，那么项目就可以称为maven项目，但实际上项目的本质还是java项目或者web项目

   A、创建java性质的maven项目

   使用模板、也可以不使用模板

   apache.maven下的quickstart模板

   当前项目的坐标设置：

   GroupId：组名，设置组名称，为项目实现分组，设置格式；通常是域名倒置，如：com.baidu；com.ujiuye，如果项目较为复杂，实现了分模块的设计，那么在 GroupId 中可以添加整体项目名称，如 com.ujiuye.xxx（整体项目名称）

   ArtifactId：项目Id，设置项目名称（如果项目较为复杂，实现了分模块设计，那么artifactId可以设置模块名称）

   Version：版本号，标志当前项目的开发版本；版本号的组成：大版本号、副版本号、小版本号、希腊字母（单词）

   例如Spring 5.1.1.RELEASE 

   大版本号轻易不会改变，在 jdk 或者是项目的架构发生时才会修改此号

   副版本号在项目中扩展了新的功能时候，会变化此号

   小版本号变动频繁，主要是修复bug之后

   希腊字母：标志当前项目处于哪个阶段，比如开发阶段、测试阶段、稳定版

   com.offcn

   maven_01

   项目的属性标志：packaging标签 默认是Java项目

   jar java项目 war web项目 pom 父项目

   B、创建web性质的maven项目

   两种 项目的属性标志：war web项目

8. 项目的构建操作

   1）假设项目原材料已经准备齐全，那么如何实现构建自动化操作

   A、构建过程包含有主要的一些步骤：清理、编译、测试、报告、打包、安装、部署

   B、对应这些步骤有关命令

   清理：对应命令 clean 清除上一次编译的结果，为下一次重新编译做准备

   编译：对应命令 complie，将 java 源程序进行编译

   测试：对应命令  test 执行 test-java 中的测试代码

   报告：展示测试结果

   打包：对应命令package，将项目实现打包处理，java项目生成jar包，web项目生成war包

   安装：对应命令 install，将打包成的包复制到本地库

   部署：对应命令 deploy 将本地库jar包上传远程哭或者实现项目部署

   2）生命周期

   A、是指构建过程中的步骤实现分组（一个生命周期包含几个操作步骤）；

   B、maven生命周期包含三个：清理周期（clean、lifecycle）、默认周期（default lifecycle）、站点周期（site lifecycles）

   C、当输入相关命令执行构建时，构建不是只执行指定的步骤，而是从本生命周期第一个命令步骤开始，执行到命令指定步骤

   D、还可以使用组合命令（组合生命周期）实现不同周期执行一次性的操作

   简化了人工操作

9. maven 的 jar 包管理

   1）依赖：就是当我们的项目需要其他项目中的程序代码时，我们的项目中需要把其他项目引入，那么对于两个项目的关系来说，我们的项目依赖于被引入的项目；通常在项目中引入其他项目，实际上引入的是项目生成的jar包；所以把jar包看做依赖也可以；

   2）如何把jar包引入到当前项目？在当前项目的pom.xml文件中，使用依赖配置来实现。

   3）依赖的配置就是一个依赖的坐标配置，组成结构

   dependency标签 groupId、artifactId、version

   4）在依赖配置中，决定依赖的作用范围的配置

   scope标签，通过此配置可以决定jar包中的程序在什么位置可以使用

   scope标签的设置值有：compile（默认值）、test、provided

   ![image-20210705163908517](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210705163908517.png)

   5）jar包管理

   A、maven 可以实现 jar 包引入

   B、jar包的传递---依赖的传递：如果乙项目中使用到丙项目生成的jar包，而甲项目又需要使用乙项目生成的jar包，那么maven工具在甲项目引入乙项目依赖时，也会把丙项目的依赖引入到甲项目中，此时在甲项目中会有两个jar包，甲项目pom.xml文件中不需要添加丙依赖配置，这是maven的jar包传递操作

   C、按照maven的默认情况，丙项目jar包会向甲项目中传递，有些时候，可能在甲项目中不需要把丙传递过来，想实现不传递，可以考虑scope标签中的值设置（乙项目能做主 test和provided都排除依赖的传递）或者排除方式（exclusions标签exclusion标签groupId与artifactId）jar包排除操作

   D、版本冲突的问题：同一种 jar 包不同版本的情况（在项目中 jar 包的依赖和传递等特点可能造成同一个 jar 包，出现不同版本），maven 工具帮助我们解决不同版本的冲突问题；解决的原则：就近原则（传递路径最短的优先）、声明原则（dependency上面的优先）

   E、jar包的统一版本管理 抽离version

### Day02

#### 回顾

Maven工具

1. 介绍

2. 构建的主要步骤

3. 生命周期、包含哪些

4. Jar 包管理

   1）依赖配置

   2）依赖传递

   3）依赖排除

   4）版本冲突

#### 内容

1. maven 的功能--jar包管理

   + jar 包版本统一管理

     properties自定义标签junit-version标签版本号

     ${junit-version} OGNL表达式使用 对象导航图语言（Object Graph Navigation Language），应用于EL。

2. maven 功能--项目结构设计

   + 项目结构---项目有哪些组成部分，这些部分之间存在什么关系

   + 使用 maven 实现项目结构设计：简而言之就是通过maven可以帮助我们实现项目的组成划分，可以实现组成中各个成员之间关系的设置

   + 如何划分组成，可以设置哪些关系？

     1）继承关系：项目由多层父项目和子项目组成，项目和项目之间存在父子关系，子和子之间是并列关系

     先建空项目，再建moudles，建父项目，建子项目指定parent 

     继承关系特点：对于父项目来说，不知道自己有哪些子项目；对于子项目来说，知道自己父项目是谁 

     继承关系作用：使用继承关系的项目结构，可以实现 jar包 的统一管理 

     使用 dependencies

     缺点是子项目不需要的包也会继承

     统一管理（即有 jar 包 又有版本） 区别继承（不同项目 jar 包不同 ）

     父项目使用 dependencyManagement 标签

     子项目使用dependency 去掉version

     2）聚合关系：项目由多层多个模块项目和一个聚合项目组成，聚合项目和模块之间存在父子关系，模块项目和模块项目之间并列关系

     先建空项目，再建moudles，建父项目，建子项目指定moudle

     聚合关系特点：对于聚合项目来说，知道自己包含哪些模块，对于模块项目来说不知道自己被哪个聚合项目包含；侧重于对项目进行功能划分

     3）不论是继承关系项目还是聚合关系项目 父项目都是 pom 项目 GAVP maven 的四元组 src 路径可删除

3. 总结 maven

   + 介绍
   + 围绕三个功能实现 -- **重点**

#### 框架部分

三部分：ssm部分

##### 框架

1. 简单来说，框架就是一种半成品的程序，开发者可以在此基础之上实现再开发。框架可以不断地更新维护，便于项目再开发

2. 有哪些常用的框架

   1）持久层的框架：mybatis、（DbUtils）、spring-jdbc、hibernate

   2）表现层的框架：springmvc、struts2

   3）全栈性质的框架：（可以在所有层可用）spring

3. 分层思想/概念，目的是降低耦合、结构清晰、实现和维护相对更简单；分工协作

   1）MVC是一种分层设计思想，把项目中某些内容分成 M，V，C 层

   2）M-Model，模型层，包含：实体类层，实现数据的封装和传输；V-View，视图层，包含：视图界面（jsp\html\excel\word），实现信息展示以及和操作者交互

   C-Controller，控制层，包含：Servlet，实现接收和处理请求，做出响应

   3）三层架构

   A、适合于所有语言、适用于所有的项目形式

   B、表现层，用于实现数据的展示，和操作者交互

   C、业务逻辑层，用于实现项目的业务逻辑的

   D、数据访问层，用于实现数据的操作，和数据库交互

##### mybatis框架

1. **是什么？**

   是持久层框架、和数据库交互、实现CRUD、封装了jdbc、参数自动传递、结果自动封装、由开发者实现SQL编写，mybatis是由apache管理的开源项目，目前托管在GitHub。由于SQL语句需要开发者编写，所以mybatis又称为半ORM框架。

2. ORM---Object Relational Mapping 对象关系映射，是指数据库表和实体类对应，表中字段和实体类属性对应，表中字段类型和实体类属性类型对应

3. 优点

   1）减少代码量

   2）实现软编码，通过 xml 配置方式

   3）提高效率，比如减少连接对象的操作

   4）还可以实现注解方式的操作

   5）简单易学

4. mybatis 的官网

   http://mybatis.org/mybatis-3/

5. mybatis 的入门案例

   1）比如需求是实现添加操作

   2）准备

   A、准备数据库和表

   ```mysql
   CREATE DATABASE mybatis CHARSET utf8
   USE mybatis
   CREATE TABLE t_user(
       uid INT PRIMARY KEY AUTO_INCREMENT,
       uname VARCHAR(30),
       upwd VARCHAR(30)
   );
   ```

   

   B、搭建项目环境

   创建项目 -- java 性质 maven 项目，添加依赖，创建实体类

   C、准备 mybatis 相关配置文件：两类文件（mybatis 核心配置文件和映射文件）

   核心文件 --- 名称任意、保存位置在类路径下，项目中一般只有一个

   映射文件 --- 名称任意（通常和表关联）、保存位置在类路径下（可以在其他任意位置），项目中可能有多个

   D、准备持久层

   E、测试

6. CRUD

   1）查询操作 根据主键id查询……

7. **mybatis的执行流程**（从上到下、顺序关系）

   + 配置文件：核心文件（环境、映射导入）和映
     射文件（SQL语句）

   + 加载配置文件、创建工厂：生产SqlSession

   + 创建会话：获取代理对象、实现增删改查
   + 执行器：真正实现增删改查功能的对象---Executor
   + 容器：负责保存SQL语句、查询结果等信息---MappedStatement（环境参数在独立保存位置）

##### 在mybatis中有两种符号

1. `#{}`与`${}` 两种符号的使用格式相同

2. 区别

   1）作用上： `#{}`是占位符`${}`是字符串拼接符 

   2）预编译：`#{}`在预编译时转回 ?，框架帮我们判断类型添加单引号，`${}`在预编译拼接字符串，值拼接不添加单引号，会产生错误，需要自己添加单引号

   3）安全：`#{}`防SQL注入 更安全

    	 `${}`不能防止SQL注入 不安全 

   4）`${}`可以进行字段名称的拼接（用途）

3. log4j 日志 1.2.47 log4j.properties日志文件从官网复制 ERROR、WARN、INFO、DEBUG四个级别设置最低的DEBUG显示信息多

#####  parameterType 属性的相关介绍

1. 何时使用？

   有参数时候

2. 可以缺省配置（设置一般类型时（数组、集合），或者添加注解时）

3. 可以设置哪些属性值（不缺省配置情况下）？

   1）一般类型（八个包装类、String、Date）

   2）实体类类型

   3）Map 类型

   4）复合实体类类型

### Day03

#### 回顾

1. Maven

   + jar包管理的统一版本管理

   + 项目结构设计 

     1）对聚合项目做相应的构建操作（清理、打包……） 相应模块也会做操作

2. mybatis

   + 什么是？

   + 优点

   + 入门案例

   + 执行原理

   + crud测试

   + 两种符号

   + 有参数使用parameterType

   + 规则：

     1）命名空间（接口全限定名）

     2）标签id（方法名）

     3）parameterType属性类型（方法形参类型）

     4）resultType属性类型（方法返回值类型）

#### 新内容

##### 注解方式

1. 使用了 Param 注解  省略parameterType（适合多参数）

   注解中变量名称要和井号括号中变量名称相同

   对象里面对象嵌套要使用.来连接

##### 核心配置文件的其他配置

1. 环境

   1）事务配置 JDBC（有事务管理，提交回滚）/MANAGED（没有事务管理）

   2）数据源配置 POOLED（连接池）/UNPOOLED（非连接池，每次请求连接和关闭）/JNDI（外部配置数据源）

2. 映射导入

   1）mapper 标签有三种属性 

   A、resource（类路径下，和接口不在一个目录）

   B、class（使用注解代替映射文件实现增删改查，用 class 设置接口名称/映射文件和接口在同一个路径且映射文件和接口名相同，也可以使用 class 引入）

   C、url 统一资源定位符 三部分：协议（http/file）+主机端口+资源路径如果映射文件没有在类路径中也没有和接口在同包，在任意的位置

   2）package标签 下 name 包名 在映射文件和接口在同位置且同名时可以一次性加载或者引入多个映射文件

3. 类型别名 typeAliases

   1）别名 -- 用来设置别名的（例如 数据库）；需求就是为了简化在映射文件中parameterType或者resultType设置类型名称时较长的全名

   2）设置 注意顺序 在 enviroments 上面 一次只能给一个类定义别名 typeAlias 标签 中 type 全限定名 alias 别名（缺省alias属性缺省配置，此时默认别名就是类名不含包名，不区分大小写）**package标签 中 name 包名** 简化操作 一次给一个包中的所有类定义默认别名（默认基本类型已经定义别名）

4. properties 标签

   1）配置标签 -- 用来实现加载外部 properties 文件的

   可以把项目中一些相同的参数抽取到properties 文件中，实现参数统一管理，什么位置需要，如核心文件，通过 properties 标签加载，再使用 OGNL（对象图形导航语言）表达式加载变量值

5. plugins 标签(在typeAliases下enviroments上)

   1）插件配置 -- 可以配置多种插件 目的是为了给 mybatis 添加其他功能

   2）添加分页插件 -- 给 mybatis 添加分页插件，实现分页功能 Mybatis_PageHelper 插件 托管在 github

   (mysql 借助 limit 关键字分页 除了第一页 limit后两个参数

   5.X版本的使用PageInterceptor 之前版本用PageHelper)

   3）Spring AOP 思想的体现 -- 实现把 limit片段向 SQL 添加

   ```xml
       <!-- 分页插件-->
       <plugins>
           <plugin interceptor="com.github.pagehelper.PageInterceptor">
               <!-- 指定底层数据库-->
               <property name="helperDialect" value="mysql"/>
               <!-- 分页页码合理-->
               <property name="reasonable" value="true"/>
           </plugin>
       </plugins>
   ```

##### 获取主键生成值 -- 介绍映射文件的相关配置 -- <font color="red">重点</font>

1. 由于MySQL数据库中，表中主键字段，在设计时设置自动生成值，那么有些时候是需要在程序中获取到MySQL自动生成的这个主键值

2. 如何获取

   1）两种方式：

   属性方式（新增语句中添加两个属性useGeneratedKeys="true" keyProperty="uid"）

   标签方式（添加selectKey标签 keyProperty、keyColumn、resultType、order）

   ```xml
   <selectKey keyProperty="uid" keyColumn="uid" resultType="int" order="AFTER">
       select last_insert_id()
   </selectKey>
   ```

   2）在数据库有 auto_increment 属性时都可用；如果没有，只能用标签方式

3. 映射文件中SQL片段概念以及相关操作

   1）为了实现映射文件中多处的相同SQL片段的统一管理，采取了 SQL 片段抽离 以及引用回去的设计，以便于在修改和维护的时候比较方便

   2）实现 抽离 sql标签 属性id为唯一标识 引用 include标签 属性refid

4. 动态SQL标签 -- <font color="red">重点</font>

   1）是指通过这些标签可以实现SQL动态变化

   2）包含的标签有：where、if、choose+when+ohterwise、set、foreach、trim

   3）where 标签用于代替where关键字，有条件则转回where关键字向SQL中传入，如果没有条件则不传入。

   4）set 标签代替 set 关键字，在预编译的时候又转回set关键字传入 SQL 中

   5）if 选择判断标签 用于实现条件成立时，向SQL中传入被 if 标签包裹的内容 mybatis框架能自动帮我们删除多余的and 关键字（前后都会删除）

   6）foreach 标签 循环遍历标签，在循环时向SQL中传入指定的内容 

   7）choose+when+ohterwise 标签 用于实现选择判断，当when 部分有一个条件成立时，其他所有成立的条件都不执行，因此只把成立位置的SQL片段传入SQL中去

   8）trim 标签 --- 自定义标签 可以使开发者更灵活的向SQL中传入指定的内容 prefix、suffix 管前后传入

   prefixoverrid、suffixoverrid 管前后删除

5. resultType 和 resultMap 属性加标签 -- <font color="red">重点</font>

   1）在实现 select 查询时使用 resultType 或者 resultMap

   2）区别：

   A、resultType 只有属性；resultMap 有属性和标签

   B、当实体类属性名和表中字段名称相同时使用resultType；

   当实体类属性名和表中字段名称不相同时使用resultMap（使用mysql的字段别名也可以）

   C、实现多表关联查询的时候使用resultMap，不能使用resultType。

   3）resultType 可以设置的类型有哪些？

   A、实体类类型

   B、一般类型：Integer、String、Date……

   C、Map 类型

   4）resultMap （标签）可以设置类型有

   A、实体类类型

   B、复合实体类类型

### Day04

#### 回顾

1. parameterType 注解的使用

2. 核心文件介绍

   1）环境

   2）映射导入

   3）别名

   4）加载外部文件

   5）插件

3. 映射文件介绍

   1）获取主键

   2）SQL片段

   3）动态SQL标签

   where、if、set、foreach、choose-when-ohterwise、trim

   4）resultType和resultMap

   > 注：在使用resultType时，如果所有的字段名称和所有的属性名都不相同，那么框架不会创建对象

#### 新内容

##### resultMap属性和标签 -- <font color="red">重点</font>

##### 关联查询第一套方案

​	嵌套结果查询 -- 连接查询

1. 多表关联查询时，resultMap的使用 -- 要把数据映射封装到实体类/复合实体类对象中（否则使用Map key-value即可）

   ![image-20210708094520354](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210708094520354.png)

2. 多表关联查询，结果使用 map 封装，如何处理？

   1）查询用户信息，关联详细信息

   2）resultType 写map 用List Map 接收 即可

3. 关联查询一对一查询（实体类和复合类封装数据）

   1）查询用户信息，关联详细信息

   2) resultMap 标签 id result 标签 写 查询表的实体使用 association 标签 中 id、result 标签写连接的表实体 

   3）SQL语句是连接查询语句（包括内外连接）

   4）查询用户详细信息属于哪个用户

   A、实体主方 添加 关联实体

4. 关联查询 实现 一对多关联查询

   1）查询用户信息，管理多收件地址

5. 多对多的关联查询

   1）查询用户信息，关联用户购买商品

   2）通过 实体类设计 collection association标签嵌套关系 实现连接查询

##### 关联查询第二套方案

1. 一对一、一对多、多对多关联查询，换一种方式嵌套查询、分表查询方式。

2. 一对一的分表查询实现

   1）查询用户信息，关联查询详细信息

   2）配置文件变化 语句变化为单表查询

   一对一查询嵌套 association 标签中添加 column 属性（本方字段id值）和 select 属性（本方的字段值送到对方的具体位置，实际上就是对方的某个方法处）相当于左外连接查询

   特点：

   + SQL语句变化连接查询变为单表查询

   + 在 association中没有下级标签 多了两个属性 column 和 select 对方需要配置相应xml内容

3. 一对多实现

   1）查询用户信息 以及具备的地址信息

   2）association替换为collection javaType替换为ofType即可

4. 多对多实现

   1）查询用户 关联购买商品有哪些

##### 延迟加载

1. 介绍

   延迟策略、懒加载、延迟查询，是和查询有关。是指在实现查询的时候把查询语句，从框架向数据库的发送时间延后。在后续程序中如果需要使用相关的数据了，此时才向数据发送SQL查询语句。

2. 在 mybatis 中延延迟策略的实现只有一种情况，关联查询时，**查询对方数据可能会被延迟**。

3. 在 mybatis 中实现延迟策略时，只有分表方案才能实现延迟。（所以分表方式常用！）

4. 演示

   1）局部：使用get展示看效果

   一对一、一对多的配置 association、collection 标签中 加入属性 fetchType 值为lazy 不用不发数据，中间可以隔一段时间，用了才发送。

   2）全局：核心配置文件加入全局配置settings标签（properties下typeAliases上）

   name为 lazyLoadingEnabled、

   aggressiveLazyLoading（极其懒加载）

   value为true

   3）目的：为了减少向数据库发送 SQL 的次数、从而降低数据库的压力，起到提高整体性能好处

##### mybatis 中逆向工程

1. 介绍

   利用表，使用相关的工具，可以用工具帮助开发者创建出实体类、持久层接口、映射文件，这样的操作就是逆向工程

2. 作用

   调高开发的效率

3. 实现

   1）导入相关的包

   org.mybatis.generator

   mybatis-generator-core 

   1.4.0

   2）创建一个 xml 配置文件 -- 逆向工程需要的配置文件

   官网

   https://mybatis.org/generator/quickstart.html

   使用 MyBatis3驱动 xml 文件（不用Simple）

   --- 文件中进行相关配置

   + 驱动配置

   + 逆向生成的时候 取消注释配置

   + commentGenerator标签下 property标签 属性name为suppressAllComments 属性value为true

   + 数据源配置
   + targetPackage
   + 生成实体类 model 保存位置

   + 生成的 xml 文件的保存位置

   + 生成的持久层接口 mapper 的配置

   + 哪些表要参与逆向工程

   + table标签 tableName属性 写入表名

   3）运行工具代码

   找到官网 copy run with Java

   位置写绝对路径

   运行

   4）默认命名规则 表明 属性  去掉下划线 字母大写

   example类封装条件片段（写入了很多常用SQL查询的条件）抽象类 有三个内部类 将SQL片段传入 生成完整的SQL语句

   条件的操作 -- example 条件对象 -- 没有SQL片段

   使用需要example下静态内部类

   封装片段查询对象：example.createCriteria

   逆向工程 不生成关联查询

### Day05

#### 回顾

resultMap

嵌套结果查询 

一对一 association javaType

一对多 collection ofType

分表查询 加入属性column select

延迟加载

分表查询才有效

局部

一对一、一对多 association、collection 标签加入属性 fetchType 值为lazy

全局

核心配置文件 settings标签 （properties下 typeAliases上）

setting标签 name为 lazyLoadingEnabled、value为true 

逆向工程



#### 新内容

##### mybatis缓存和注解实现

##### mybatis缓存

缓存空间（计算机内存条）临时存放 内存读写速度较快 降低数据库的压力 提高整体的性能

1. 一级缓存和二级缓存

   1）一级缓存属于session，由session管理，有session才有一级缓存，一个session对应一个一级缓存，有多少个session有多少个一级缓存，可以借助session实现一级缓存数据的清理和更新（clearCache方法）。实现数据的增删改操作，一级缓存数据自动删除。查询时候重新缓存。

   2）二级缓存属于mapper级别的，多个session共用的 的缓存 一般只有一个，可以清理和更新。实现数据的增删改操作，二级缓存数据也自动删除。

   （注意：第一个session直接到数据库查询，再到二级缓存保存 守护线程判断是否为第一个）

   ![image-20210709094314779](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210709094314779.png)
   
2. 一级缓存

   1）有 session 就有一级缓存、所以当 session 被创建出来那么一级缓存就有了

3. 二级缓存

   1）默认是关闭的

   2）如果需要使用则首先开启：有两个位置需要操作：全局配置 settings cacheEnabled（新版本默认开启）位置和映射文件 加入cache标签即可 默认类型设置为 PerpetualCache 永恒的缓存 也可以选用其他二级缓存类型 导入jar包 添加type设置 如ehCache、memberCache、**Redis** 如需要自定义实现类 就是定义Cache接口的实现类

##### mybatis注解

Overrid、Test、 WebServlet等注解

1. 介绍

   代替配置实现增删改查等功能，不同的注解具备不同功能

2. 有哪些注解:

   1）实现增删改查的注解：@Insert、@Delete、@Update、@Select

   2）实现获取主键的注解：@SelectKey

   3）实现名称不一致或者联合查询的注解：@Results、@Result、@one、@Many

   Results 相当与ResultMap 标签

   注解中添加相应的属性如：id=true、column、 property、javaType、one、many、select

   多表的话many可以将javaType缺省 没有ofType 

   one和many里的属性 fetchType = FetchType.LAZY/EAGER 懒加载与急加载

3. 实现

4. 业务复杂度没有那么高适合使用注解的方式，SQL变化不大适合使用注解方式，其他情况使用配置，分布式项目配置为主

##### mybatis总结

1. 配置 --- 核心配置文件、映射文件配置
2. 介绍
3. 入门案例
4. 执行原理
5. 两种符号
6. 延迟策略
7. 逆向工程
8. 关联查询
9. 缓存策略
10. 注解

##### Spring框架

1. 介绍 -- <font color="red">重点</font>

   1）概述

   + 轻量级、一站式、开源框架，为了解决项目开发复杂度，实现了 IOC 和 AOP 设计思想，实现解耦的框架

   + 轻量级：代码体积小、资源的耗费较少

   + 一站式：提供的功能较为全面
   + 耦合：是指两者之间存在依靠、依赖关系，耦合有高耦合、低耦合。
   + 低耦合、高内聚 指项目的设计原则

   2）作用、特点

   + 存在配置和注解两套方式
   + 可以实现解耦
   + 基于接口式的开发
   + 存在声明式的事务管理
   + 提供AOP设计实现
   + 测试比较简单
   + 整合外部优秀框架
   + 对javaee的封装（javaEmail，RMI 。Spring封装好了易用）

   3）组成 

   + 20多个子部分、子模块

   + 每个部分/模块具备不同的功能

   + 主要的相关组成

     A、核心容器：core container --- spring-core，spring 框架的基础

     spring-beans 是实现对象管理的（工厂）

     spring-context 是上下文环境

     spring 框架实现的管理的内容（配置文件）

     B、spring-aop：面向切面编程思想的实现

     C、spring-aspects：整合包，整合其他框架

     D、spring-jdbc：相当于mybatis的持久层框架

     E、spring-orm：整合包，整合其他持久层框架

     F、**spring-webmvc**：表现层模块，实现表现层功能

     G、spring-test：整合包，把单元测试整合

   4）spring的官网

   Rod Johnson 创始人

   http://spring.io

   通常说的Spring是Spring Framework

   5.2.15 和 5.3.8 稳定版 同时维护

   5）核心思想 --- IOC 思想 -- <font color="red">重点</font>

   + 思想的实现涉及到 core container 核心容器，涉及到其中相关子模块

   + 介绍 --- 什么是 IOC

     A、IOC --- Inversion of control 控制反转/控制倒置、控制倒转

     是指在程序中把对象的管理工作交由第三方容器负责

   + IOC 实现

     A、spring 配置文件 -- 名称任意的，官方使用 applicationContext.xml，保存位置一般类路径中

     ```xml
     <!-- 创建对象的配置-->
     <!--servlet-->
     <!-- id属性标识：唯一性，通过id可以找到类，找到对象-->
     <!-- class：设置类的全限定名-->
     <!-- 综合起来表示要创建（由容器创建）哪个类的对象，由id对对象进行标识-->
     <bean id="helloServlet" class="com.bh.servlet.HelloServlet">
         <!-- 把 service 对象给 servlet 对象注入进去-->
         <property name="helloService" ref="helloService"></property>
     </bean>
     <!-- service-->
     <bean id="helloService" class="com.bh.service.HelloService"></bean>
     ```

     ```java
     // 先有容器 -- 加载配置文件
     ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
     
     // 从容器中获取对象
     HelloServlet hs = (HelloServlet) context.getBean("helloServlet");
     HelloService helloService = (HelloService) context.getBean("helloService");
     
     // 测试是否可以正常获取对象
     System.out.println(hs);
     System.out.println(helloService);
     
     // 测试方法
     hs.save();
     ```

   + 依赖注入 -- DI

     A、servlet 对象需要 service 对象，容器负责把自己创建出来的 service 对象给 servlet 传递过去，这个操作被称为 DI -- 依赖注入

     B、Dependency Injection，所谓的依赖注入是指存在依赖关系的两个对象，**容器**负责把内层对象（被依赖的对象）给外层对象实现注入（传递）

   + IOC 和 DI 有无关系？如果有，是什么关系？

     有关系；IOC 是阐述控制反转概念，侧重于说明容器管理对象，没有指明是哪些关系；DI 是一种动作是一种实现，侧重于进行容器的依赖注入操作，指明是实现依赖的注入管理；实际上 IOC 和 DI 就是一个概念的不同的说明

   + 为什么使用 IOC？ 解耦

   + IOC 的底层原理

     利用 dom4j 模拟spring ioc实现
     
     ```java
     // map对象
     private static Map<String,Object> map = new HashMap<>();
     
     static {
         try {
             // 静态代码块 类加载时读取配置文件，并创建对象
             // xml 文档的解析
             // 解析对象
             SAXReader reader =new SAXReader();
             // 读取配置文件
             Document document = reader.read("src/main/resources/applicationContext.xml");
             // 从文件中解析获取内容 -- 根标签
             Element rootElement = document.getRootElement();
             // 在获取其他标签
             List<Element> beans = rootElement.elements("bean");
             // 遍历集合
             for (Element element : beans) {
     
                 // 获取属性的值
                 String idValue = element.attributeValue("id");//helloServlet helloService
                 String classValue = element.attributeValue("class");// com.bh.servlet.HelloServlet  com.bh.service.HelloService
                 // 反射方式造对象 -- 放入map
                 Class cla = Class.forName(classValue);
                 // 通过反射造对象
                 Object o = cla.newInstance();
                 map.put(idValue,o);// helloServlet+对象
             }
         } catch (DocumentException e) {
             e.printStackTrace();
         } catch (ClassNotFoundException e) {
             e.printStackTrace();
         } catch (InstantiationException e) {
             e.printStackTrace();
         } catch (IllegalAccessException e) {
             e.printStackTrace();
         }
     }
     
     public static Object getBean(String name) {
         return map.get(name);
     }
     ```
### Day06

#### 回顾

Mybatis

1. 缓存

   一级、二级

2. 注解

Spring

1. 介绍
2. IOC

#### 新内容

##### IOC 实例化对象的方式有哪些？

1. 容器读取何种配置，就可以创建对象

2. 三种：无参构造配置方式、静态工厂的配置方式、动态工厂的配置方式

   1）无参构造配置

   ```xml
   <!-- 无参构造的配置方式，实现对象实例化-->
   <!-- cla.newInstance() 就是执行无参构造方法-->
   <!-- 此配置方式底层借助的是类的无参构造创建的对象，因此把这种配置方式称为无参构造的配置方式-->
   <bean id="str1" class="java.lang.String"></bean>
   ```

   2）静态工厂

   ```xml
   <bean id="calendar" class="java.util.Calendar" factory-method="getInstance"></bean>
   ```

   3）动态工厂

   factory-bean、factory-method

   ```xml
   <!-- 先配置动态工厂方法所属对象-->
   <bean id="factory" class="com.bh.factory.DynamicFactory"></bean>
   <!-- factory-bean 表示通过id获取到一个对象-->
   <!-- factory-method表示上面获取到的对象中的指定方法-->
   <!-- 此种配置就是容器识别到此配置，那么调用factory-bean获取到的对象，让这个对象调用自己指定方法，最后容器创建出返回值对象-->
   <bean id="str3" class="java.lang.String" factory-bean="factory" factory-method="getString"></bean>
   ```

3. 小结

   bean标签的相关属性：id、calss、factory-method、factory-bean

   1）id --- 唯一标识、用于在容器中标志一个对象以及对象所属的类型

   2）Class --- 要创建的对象（被容器管理的对象）所属类型

   3）factory-method --- 类或者对象要调用的方法（通过此方法调用可以获取到其他对象）

   4）factroy-bean --- 通过指定id名称来设置一个对象，容器让此对象调用factory-method指定的方法

   5）scope --- 对象的作用范围，值：singleton（默认）、prototype、request、session、globalsession。

   A、容器创建的对象特点：singleton此值决定当前对象是一个单例对象{即每次从容器获取的时候都是同一个对象} --- spring在此处使用了单例模式

   B、prototype此值决定当前对象不是单例对象，{即每次从容器获取的时候，取出来的都是新的对象}

   C、request 和 session 在 web 项目中使用，request 表示容器创建对象在一个request 域中是同一个（在一次请求中每次获取的对象是同一个）

   D、session 表示容器创建的对象在一个 session 中是同一个（在一次会话中每次获取的对象是同一个）

   6）destroy-method -- 表示在对象销毁之前先调用此属性指定的方法

   7）init-method -- 表示在对象创建之后先执行此属性指定的方法进行对象的相关初始化操作

   8）lazy-init -- 表示容器何时创建对象：默认是加载配置文件后立即创建对象；设置为true加载配置文件没有立即创建，何时使用何时创建

##### 依赖注入的方式有哪些？-- <font color="red">重点</font>

1. 依赖注入的实现方式有：两种 -- 一种是借助 set 方法注入；另一种是借助有参构造实现注入

2. 借助 set 方法方式实现注入

   1）在类中要提供 set 方法、在 bean 标签中使用 property 下级标签 设置 name 和 ref 属性

3. 借助有参构造的方式实现注入

   1）在类中提供有参构造方法，在 bean 标签中使用 constructor-arg 下级标签 设置 name 和 ref 属性

4. 小结

   1）在 propertity 和 constructor-arg 标签中都含有 name、ref、value 三个属性

   2）作用：

   A、name 用于设置类中的属性名

   B、ref 用于设置 id 标识名称，通过此标识在容器中的对应对象

   C、value 用于设置普通的值（Integer、Double、Boolean、character、String）

5. 如果在类中，各种不同形式的属性（一般、实体、数组、集合），如何注入？

   1）不同形式属性注入都可采用set/有参构造

   2）使用不同的标签和属性实现

   ```xml
   <!-- 不同类型属性注入-->
   <bean id="helloService2" class="com.bh.service.HelloService">
       <!-- 简单类型注入 4类8种-->
       <property name="size" value="10"></property>
       <property name="size1" value="11"></property>
       <property name="length" value="12"></property>
       <property name="sho" value="13"></property>
       <property name="by" value="14"></property>
   
       <property name="dou" value="15.2"></property>
       <property name="flo" value="16.3"></property>
   
       <property name="flag" value="true"></property>
   
       <property name="cha" value="A"></property>
   
       <property name="str" value="abcd"></property>
   
       <!--<property name="date" ref="date"></property>-->
   
       <!-- 类似 xxxx.setDate(new Date())-->
       <property name="date">
           <bean class="java.util.Date"></bean>
       </property>
   
       <property name="helloDao" ref="helloDao"></property>
   
       <property name="ints">
           <array>
               <value>20</value>
               <value>21</value>
               <value>22</value>
               <value>23</value>
           </array>
       </property>
   
       <property name="chars">
           <array>
               <value>a</value>
               <value>x</value>
               <value>7</value>
           </array>
       </property>
   
       <property name="strs">
           <array>
               <value>abcde</value>
               <value>opqm</value>
               <value>22222</value>
           </array>
       </property>
   
       <property name="dates">
           <array>
               <!-- 把已有的对象注入-->
               <ref bean="date"></ref>
               <bean class="java.util.Date"></bean>
           </array>
       </property>
   
       <property name="helloDaos">
           <array>
               <!-- 把已有的对象注入-->
               <ref bean="helloDao"></ref>
               <bean class="com.bh.dao.HelloDao"></bean>
           </array>
       </property>
   
       <!-- 集合-->
       <property name="integerList">
           <list>
               <value>30</value>
               <value>31</value>
               <value>32</value>
           </list>
       </property>
   
       <property name="integerSet">
           <set>
               <value>40</value>
               <value>41</value>
               <value>42</value>
           </set>
       </property>
   
       <property name="integerMap">
           <map>
               <entry key="k1" value="1"></entry>
               <entry key="k2" value="2"></entry>
               <entry key="k3" value="3"></entry>
               <entry key="k4" value="4"></entry>
           </map>
       </property>
   
       <property name="daoList">
           <list>
               <ref bean="helloDao"></ref>
               <bean class="com.bh.dao.HelloDao"></bean>
           </list>
       </property>
   
       <property name="daoSet">
           <set>
               <ref bean="helloDao"></ref>
               <bean class="com.bh.dao.HelloDao"></bean>
           </set>
       </property>
   
       <property name="daoMap">
           <map>
               <entry key="hd1" value-ref="helloDao"></entry>
               <entry key="hd2">
                   <bean class="com.bh.dao.HelloDao"></bean>
               </entry>
           </map>
       </property>
   
       <property name="properties">
           <props>
               <prop key="k1">v1</prop>
               <prop key="k2">v2</prop>
               <prop key="k3">v3</prop>
           </props>
       </property>
   </bean>
   ```

##### 相关注解 --- 既有配置文件又有注解方式（ioc 和 di）

1. 实现对象实例化的相关注解 --- 等价 bean 标签

   1）@Component、@Controller、@Service、@Repository

   2）@Component 相当于父类 其他三个继承，主要的区别是不同层上用不同的注解，方便维护

   A、@Controller 用于控制层 -- Servlet层

   B、@Service 用于业务层 -- Service层

   C、@Repositiory 用于持久层 -- Dao层

   D、@Component 除以上三层使用

2. 实现注入的相关注解 --- 等价 property 或者 constructor-arg 标签

   1）@Autowired（+@Qualifier）、@Resource、@Value

   2）@Autowired和@Resource实现对象注入的，@Value实现值注入的

   3）Autowired 自动装配 -- 在容器中通过类型找此类的对象，然后完成注入；@Resource -- 可以通过名称找容器中的对应 id 标识的对象，也可以通过类型找对象

   4）单独使用@Autowired，只能通过类型找到对象，如果@Autowired和@Qualifier结合使用，那么可以通过@Qualifier指定名称，此时可以从容器中通过名称找到对应 id 标识的对象，最后实现注入

   5）@Value 加载 外部 properties 数据

   ```xml
   <!-- 加载properties文件-->
   <context:property-placeholder location="classpath:spring.properties"></context:property-placeholder>
   
   <!-- 扫描包：告知spring框架到哪里找有什么注解-->
   <!-- base-package 设置包名 扫描包和下级子包-->
   <context:component-scan base-package="com.bh">
   </context:component-scan>
   ```

   ```java
   @Component// 默认标识 --- 类名，首字母小写
   public class HelloService {
   
       // 从容器中找此类型 找不到 抛出异常
       //@Autowired
   
       // 按属性名id找，找不到 在按类型找
       //@Resource(name = "hd")
       @Autowired()
       private HelloDao helloDao;
   
       @Value("${spring_name}")
       private String name;
   ```

##### 纯注解的方式实现（ioc 和 di）-- <font color="red">重点</font>

1. 纯注解的方式没有了配置文件，但是多了一个配置类

   @Configuration、@ComponentScan、@PropertySource、@Bean

   ```java
   // 声明是配置类
   @Configuration
   // 扫描包 <context:component-scan>
   @ComponentScan(basePackages = "com.bh")
   // 加载properties文件
   @PropertySource(value = "classpath:spring.properties")
   public class SpringConfig {
   
       // 创建对象的方法
       // 将方法返回的对象放入容器，实现容器管理 放哪个类中都可以（灵活）
       @Bean
       public ModelMap getModelMap() {
           return new ModelMap();
       }
   }
   ```

##### spring 和 junit 实现整合

1. 简化测试

2. 如何实现整合

   ```java
   // 注解
   // 把当前测试类也放入IOC容器管理
   @RunWith(SpringRunner.class)
   // 加载xml配置文件
   //@ContextConfiguration(locations = {"classpath:applicationContext.xml"})
   // 加载配置类
   @ContextConfiguration(classes = {SpringConfig.class})
   
   public class SpringTest {
   
       // 也可以实现注入
       @Autowired
       private HelloService helloService;
   
       @Test
       public void test1() {
           helloService.method();
       }
   }
   ```

##### spring整合mybatis思考

```xml
<!-- 动态工厂测试-->
<!-- inputStream 为抽象类 不能配置bean -->
<bean id="inputStream" class="org.apache.ibatis.io.Resources" factory-method="getResourceAsStream">
    <constructor-arg value="mybatis.xml"></constructor-arg>
</bean>

<bean id="sqlSessionFactoryBuilder" class="org.apache.ibatis.session.SqlSessionFactoryBuilder"></bean>

<bean id="factory2" class="org.apache.ibatis.session.SqlSessionFactory" factory-bean="sqlSessionFactoryBuilder" factory-method="build">
    <constructor-arg ref="inputStream"></constructor-arg>
</bean>

<bean id="sqlSession" class="org.apache.ibatis.session.SqlSession" factory-bean="factory2" factory-method="openSession"></bean>
```

```java
// 测试动态工厂
@Test
public void testDynamicFactory() {
    ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
    SqlSession sqlSession = (SqlSession) context.getBean("sqlSession");
    System.out.println(sqlSession);
    System.out.println("====================");
    UserDao mapper = sqlSession.getMapper(UserDao.class);
    User user = mapper.selectOne(2);
    System.out.println(user);
    System.out.println("====================");
}
```

### Day07

#### 回顾

IOC、DI

1. 纯配置的方式

   1）IOC实现方式

   a 无参构造的方式

   b 静态工厂的方式

   c 动态工厂的方式

   2）对象的作用范围

   3）DI 的实现方式

   A、set 方法的方式

   B、有参构造的方式

   4）各种不同属性的注入

2. 有配置有注解的方式

   1）实例化对象：

   2）注入：

   3）**设置对象作用范围的注解@Scope("singleton")**，在类上添加，设置对象作用范围

   4）扫描包、加载外部 properties 文件

3. 纯注解的方式

   1）配置类代替配置文件

   2）配置类中添加新的注解：

   A、声明配置类的注解

   B、扫描包

   C、加载 properties

   D、@Bean

把单元测试框架进行整合

1. 整合包
2. 把测试类对象也进行容器管理

#### 内容

##### spring持久层模块介绍 --- 在此处 spring 框架采用了模板设计模式

1. spring的持久层模块：spring-jdbc

2. 功能：也是对原生 jdbc 的封装，也是实现和数据库交互的，实现增删改查功能，能实现参数传递，能实现结果映射，需要设计实现SQL语句，在程序中写SQL

3. 演示

   jdbcTemplate 更新update 查询query （单个queryforObject、多个query）

   使用RowMapper的实现类new BeanPropertyRowMapper<对象>(对象.class)封装数据

   DriverManagerDateSource 数据源

   数据源配置bean Autowired引入
   
   ```xml
       <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
           <property name="driverClassName" value="com.mysql.jdbc.Driver"></property>
           <property name="url" value="jdbc:mysql:///mybatis?characterEncoding=utf8"></property>
           <property name="username" value="root"></property>
           <property name="password" value="admin"></property>
       </bean>
   ```
   
   

##### 模板设计模式

1. 设置模式注重模板的设计，把相同的东西封装，便于代码复用。

2. 设计实现

   1）定义接口（可有可无）

   2）定义抽象类 -- 实现接口 -- 把重复性的代码在类中实现

   3）有其他的类继承抽象类的 -- 重写那些需要根据实际情况变化的内容

3. 举例：

   定义接口为所有要进行的步骤

   定义抽象类实现接口，实现公共的步骤，有区别的步骤用抽象方法定义

   定义实现类继承抽象类，自定义实现抽象方法，共有方法抽象类模板已经实现

##### AOP 设计思想 -- spring框架中的另一个核心思想、核心概念

1. 产品经理需求变动频繁 代码要求灵活 

2. 代理方式，设计目的就是为了实现代码的灵活扩展，解决继承时从父类全继承、或者对象和对象之间出现高耦合

   原生的代理方式：

   1）介绍

   一方（对象）代替另一方（对象）实现功能

   2）代替方 -- 代理对象 ； 被代替方 -- 目标对象

   实现

   代理有静态代理的方式和动态代理的方式

   Proxy代理 

   3）静态代理：

   **缺点**

   实现多个目标对象 同名方法会冲突

   所以一个代理对象一个目标对象，代码多了近乎一倍，代码冗余太多了

   4）动态代理：

   A、两种动态代理方式 -- jdk动态代理方式、cglib动态代理方式

   B、jdk 方式借助 jdk 中提供的类（java.lang.reflect.Proxy）、接口等功能实现；cglib 方式属于框架提供C、jdk 动态代理实现方式：接口、实现类、代理工厂类

   **回顾反射**

   ```java
   // 测试反射
   Class cla = Clas.forName("全限定名");
   // 创建对象
   Object o = cla.newInstance();
   // 获取方法
   Methid me = cla.getMethod("方法名");
   // 调用方法
   Object invoke = me.invoke(o);
   ```

   实现 InvocationHandler 接口

   传入目标对象

   实现方法 invoke（反射方式调用方法也是invoke）return invoke

   invoke(Object proxy,Method method,Object[] args) 

   **获取代理对象的方法**		getProxyObject

   return Proxy.newProxyInstance(

   obj.getClass().getiClassLoader(),

   obj.getClass().getInterfaces(),

   this)

   参数类加载器、接口、实现接口的类的对象

   **解释**

   目标接口 -- 接口的实现类 -- Proxy动态代理 工厂动态生成 代理类 并销毁

   ```java
   // 动态 代理工厂
   public class ProxyServiceFactory implements InvocationHandler {
   
       private Object obj;
   
       public void setObj(Object obj) {
           this.obj = obj;
       }
   
       @Override
       public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
   
           // 相当于目标对象调用功能 -- 原始功能的执行
           Object invoke = method.invoke(obj, args);
           if("register".equals(method.getName())) {
               return invoke;
           }
           add();
           return invoke;
       }
   
       public void add() {
           System.out.println("添加新的功能.......");
       }
   
       // 获取到代理对象的方法
       public Object getProxyObject() {
           // 第一个参数类加载器
           // 第二个参数是接口
           // 第三个参数是实现InvocationHandler接口的类的对象 -- 本类对象
           return Proxy.newProxyInstance(obj.getClass().getClassLoader(),obj.getClass().getInterfaces(),this);
       }
   }
   ```

   5）动态代理和静态代理的区别

   静态代理静态类一直存在 动态代理动态类是生成的

   6）cglib 动态代理介绍

   A、这种代理方式不需要接口，只需要类（项目没有接口，只有类）

   spring-context导入就有 cglib

   实现 MEthodInterceptor接口

   实现 Intercept 方法 （和jdk的invoke类似）

   **获取代理对象的方法**		getProxyObject

   Enhancer enhancer = new Enhancer();

   // 父类

   enhancer.setSupperclass(目标类.class)

   // 本类对象

   enhancer.setCallBack(this);

   //返回代理对象

   return enhancer.create();

   B、实现

   目标类

   工厂

   测试

   ```java
   public class ProxyServiceFactory implements MethodInterceptor {
   
       private Object obj;
   
       public void setObj(Object obj) {
           this.obj = obj;
       }
   
       @Override
       public Object intercept(Object o, Method method, Object[] objects, MethodProxy methodProxy) throws Throwable {
   
           Object invoke = method.invoke(obj, objects);
           add();
           return invoke;
       }
   
       // 新增功能
       public void add() {
           System.out.println("新增的功能......");
       }
   
       // 获取代理对象的方法
       public Object getProxyObject() {
   
           // 增强器
           Enhancer enhancer = new Enhancer();
   
           // 设置父类
           enhancer.setSuperclass(obj.getClass());
   
           // 设置 回调本类实现MethodInterceptor的类
           enhancer.setCallback(this);
   
           // 返回创建的代理对象
           return enhancer.create();
       }
   
   }
   ```

   7）动态代理同样存在缺点

   jdk 基于接口的动态代理

   cglib 基于父类（不是继承）的动态代理

   如果目标类有多个功能，实现功能扩展，需要不同功能扩展不同内容，使用动态代理，invike 方法实现较为复杂（调用哪个方法Proxy就动态代理生成哪个方法的代理类）

   需要有区别的进行添加，加判断？

   method.getName() 判断。。。

   如果方法很多 需要写大量的代码

3. aop 介绍

   1）spring 的 aop 实现默认基于的是 jdk 动态代理

   导入spring-aspects 导入的其实是aspectj
   
   例
   
      ```xml
   <aop:config>
       <aop:aspect ref="">
           <aop:pointcut id="" expression="execution(void com.xxx.xxx())">			</aop:pointcut>
           <aop:after-returning method="" pointcut-ref="">
           </aop:after-returning>
       </aop:aspect>
   </aop:config>
      ```

   2）AOP

   Aspect Oriented Programming

   面向切面编程

   是面向对象编程的扩展、补充，实现了松耦合，在开发过程中中专注于切面的开发，切面是由切点和扩展功能组合的模块，是通过预编译方式和运行期动态代理实现程序统一维护设计思想

   降低耦合、提高代码可重用性

   3）相关术语的介绍

   A、切面

   是切点和增强的模块化；包含切点和增强（aop：aspect）

   B、切点

   是指确定向哪些方法实现添加功能的点（定义），如何确定要被扩展的方法呢？通常使用函数和表达式来实现。

   函数：execution()

   表达式：最终确定的是方法(表达式代表的是方法)

   表达式有格式：精确格式、模糊格式（带有符号：*和.）

   模糊格式：方法返回值类型、包名、类名、方法名、形参都可以使用符号

   ```java
   // 几种扩展功能
   // 指定方法
   * com.bh.service.UserServiceImpl.login()
   // 所有方法
   * com.bh.service.UserServiceImpl.*(..)
   // do开头方法
   * com.bh.service.UserServiceImpl.do*(..)
   // 所有类所有方法
   * com.bh.service.*.*(..)
   // 所有
   *.*.*(..)
   ```

   C、增强、通知

   是指扩展的功能，通常封装成方法

   不同的增强方式：前通知（前增强）、后通知（后增强）、环绕通知（环绕增强）、异常后通知（异常后增强）、最终通知（最终增强）

   前通知：在原有的功能执行之前先执行的通知
   
   后通知：在原有的功能执行之后执行的通知，如果原有的功能发生异常，那么后通知无法执行
   
   环绕通知：在原有的通知执行之前和执行之后分别都有执行，如果原有的功能发生异常，那么在原有功能执行之后的再次执行就无法执行了
   
   ```java
   //环绕通知增强
   public Object arround(ProceedingJoinPoint pjp) throws Throwable {
       System.out.println("环绕前增强……");
       // 切点方法
       Object proceed = pjp.proceed();
       System.out.println("环绕后增强……");
       return proceed;
   }
   ```
   
   
   
   异常后通知：只有在原有功能发生异常时才执行，如果原有功能没有异常则不执行
   
   最终通知：不论原有功能是否发生异常，在原有功能执行之后都会执行
   
   D、连接点
   
   E、代理
   
   F、目标
   
   G、织入

### Day08

#### 回顾

1. spring 的 jdbc 介绍

2. 模板设计模式

3. spring 的 aop（需求开发演变（功能扩展））

   + 代理

     1）静态代理

     2）动态代理：jdk 代理（框架默认使用）、cglib代理

   + aop

     1）介绍

     面向切面编程

     2）术语

     切面、切点、增强（通知）

#### 内容

##### Aop-- <font color="red">重点</font>

1. 术语

   1）连接点

   是指在程序**运行过程中**的一些特殊的点/位置；在 spring 框架连接点通常指的是程序运行过程中某个**方法被调用**（如：前通知，执行前那一刻，**结合增强**在此方法被调用之前或者之后或者抛出异常时这些**位置**都是连接点）

   2）目标

   原文being advised 过去被增强 

   被增强**之后**的对象（原始功能扩展新的功能之后方法所属的对象）

   3）代理

   框架创建出来的对象（容器注入属性的对象）

   4）织入

   把扩展功能向原始功能进行添加，并创建被增强对象的过程

   （英文文档便于理解）

2. 纯配置实现

   1）ioc 实现原始功能所在类的对象、扩展功能所在类的对象

   2）aop:config 标签、aop:aspect 标签、aop:pointCut 标签、aop:before 标签、aop:after-returning 标签、aop:around 标签、aop:after-throwing 标签、aop:after 标签

3. 配置和注解

   1）实现 IOC 功能的注解:@Service、@Commponent、@Controller、@Repositiory

   2）实现切面、增强（切点）的注解：@Aspect、@Before、@After、@AfterReturning、@AfterThrowing、@Around

   3）自动代理

   aop：aspect-autoproxy（默认为 jdk 动态代理）

   切换cglib 属性 proxy-target-class = true

   spring 开发一般用接口，用类少

   ```xml
   <!-- 扫描包-->
   <context:component-scan base-package="com.bh"></context:component-scan>
   
   <!-- aop自动代理-->
   <aop:aspectj-autoproxy></aop:aspectj-autoproxy>
   ```

   ```java
   @Component
   @Aspect// 定义一个切面 声明当前类是一个切面
   // 封装扩展功能 -- 通知
   public class AdviceTypeClass {
   
       // 通知
       @Before("execution(* com.bh.service..*.*(..))")
       public void before() {
           System.out.println("before通知！！！");
       }
       @AfterReturning("execution(* com.bh.service..*.*(..))")
       public void after() {
           System.out.println("after通知！！！");
       }
       @Around("execution(* com.bh.service..*.*(..))")
       public void round(ProceedingJoinPoint joinPoint) throws Throwable {
           System.out.println("round前通知！！！");
           // 原始功能被调用
           joinPoint.proceed();
           System.out.println("round后通知！！！");
       }
       @AfterThrowing("execution(* com.bh.service..*.*(..))")
       public void exception() {
           System.out.println("exception通知！！！");
       }
       @After(("execution(* com.bh.service..*.*(..))"))
       public void last(){
           System.out.println("last通知！！！");
       }
   }
   ```

   > 注意：注解时候环绕通知变为最前和最后，xml配置则为原功能紧邻的

4. 纯注解实现

   1）相关类上的注解不变（有配置有注解方式中类上面的添加注解）

   2）创建配置类（没有了配置文件），类上有声明注解@Configuration、@ComponentScan、自动代理注解@EnableAspectAutoProxy
   
   ```java
   @Configuration
   @ComponentScan(basePackages = {"com.bh"})
   @EnableAspectJAutoProxy
   public class SpringConfig {
   }
   ```

##### aop典型的应用场景-- <font color="red">重点</font>

1. 分页插件采用 aop 思想

   如：mybatis 分页插件 pageHelper（采用 aop 思想）

2. 日志管理采用 aop 思想

   如：log4j 日志打印信息 （aop 前通知的思想）

3. 拦截器采用 aop 思想、实现 

   如：spring-mvc Interceptor

4. 权限验证采用 aop 思想

   如：Spring Security 权限验证框架 用户的操作权限

5. 事务管理采用 aop 思想

**总结**

Spring 框架涉及到的设计模式？

单例模式 scope属性/注解

工厂模式 BeanFactory

代理模式 aop 动态代理

模板模式 jdbcTemplate

##### aop 思想实现事务管理-- <font color="red">重点</font>

1. 什么是事务？

   是一个完整的数据库增删改查的执行单元，可能由多条 SQL 语句组成。

2. 事务的特性？

   原子性（atomicity）、一致性（consistency）、隔离性（isolation）、持久性（durability） --ACID

   1）原子性：要成功都成功（commit）、要失败都失败（rollback）

   2）一致性：事务在执行前后，数据保持不变

   3）隔离性：事务和事务之间彼此互不影响

   4）持久性：事务在执行前后，对数据的影响是持久的

3. 数据异常

   脏读数据、不可重复读数据、幻读数据

   1）脏读：读未提交

   2）不可重复读：多次读数据不同

   3）幻读：插入或者更改造成读取不同

4. 数据异常的处理

   事务隔离级别：读未提交、读已提交、可重复读、串行化/序列化

5. 事务的传播性 -- spring实现事务管理时提出的概念

   比如：在 service 层的某个方法中存在多个 dao 层方法的调用，service.save(){dao.insert();dao.select();dao.update()},那么传播性就是事务由第一个 insert 方法传播到第二个 select() 再传播到第三个 update 方法；反过来就是把多个方法纳入一个事务管理单元。

   **保证同一个连接对象（连接对象绑定到线程中ThreadLocal）**

6. spring 中如何实现事务管理？

   1）需求：银行中的转账功能的实现

   2）实现：

   A、创建表、实体类

   B、造持久层功能方法

   C、造业务层功能

   D、相关配置以及事务管理的类

   ThreadLocal<> 将连接对象绑定到线程中

   queryRunner.query传递链接对象参数，保证事务传播一致性

7. spring 框架中提供的事务管理的方式的实现

   1）纯配置

   ```xml
    <!--自定义事务管理类对象-->
       <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
           <property name="dataSource" ref="dataSource"></property>
       </bean>
   
       <!--指定某些方法的增强方式-->
       <tx:advice id="txAdvice" transaction-manager="transactionManager">
           <tx:attributes>
               <!--<tx:method name="*"/>-->
               <!--<tx:method name="account*"/>-->
               <!--isolation设置事务隔离级别，default表示默认级别，即数据库是什么级别就按照什么级别处理-->
               <!--read-only表示只读，即方法中只有查询操作，可以没有事务管理-->
               <!--REQUIRED当account方法被执行的时候，如果其中有多个SQL，那么在执行第一个SQL对应的方法被调用的时候，
               如果没有事务则创建事务并把SQL纳入当前事务管理之中；
               当第二个SQL对应的方法被调用的时候，如果当前已经存在了事务，那么就把SQL纳入已经存在的事务管理之中-->
               <tx:method name="account" isolation="DEFAULT" read-only="false" propagation="REQUIRED"/>
           </tx:attributes>
       </tx:advice>
   
   
       <!--切入-->
       <aop:config>
           <aop:pointcut id="pointcut1" expression="execution(* com.offcn.service.impl.AccountServiceImpl.account(..))"/>
           <aop:advisor advice-ref="txAdvice" pointcut-ref="pointcut1"></aop:advisor>
       </aop:config>
   ```
   
   
   
   2）配置和注解
   
   ```xml
   <!-- 开启事务注解驱动-->
   <tx:annotation-driven>
   ```
   
   @Transactional
   
   3）纯注解
   
   @EnableTransactionManagement
   
   开启事务管理等同于上面标签

##### spring 和 mybatis 的整合

1. 整合之后的分工：mybatis 负责持久层的操作，即增删改查；spring 负责 IOC、AOP、事务管理

2. 实现整合的步骤

   1）搭建项目、导入依赖

   spring依赖、mybatis依赖、整合包、驱动、连接池、日志、分页插件、测试的整合包、单元测试

   2）配置 spring 配置文件：扫描包、数据源、事务对象、事务注解驱动、整合 mybatis 的配置

   3）准备 mybatis 核心文件（可以没有任何配置）和映射文件（相关功能配置）

   **工厂配置**：SqlSessionFactoryBean实现类

   ```xml
   <!--整合mybatis的配置-->
   <!--工厂-->
   <bean id="factory" class="org.mybatis.spring.SqlSessionFactoryBean">
       <!--加载mybatis核心配置文件-->
       <property name="configLocation" value="classpath:mybatis.xml"></property>
       <!--加载映射文件-->
       <property name="mapperLocations" value="classpath:mappers/*.xml"></property>
       <!--数据源-->
       <property name="dataSource" ref="dataSource"></property>
       <!--设置别名-->
       <property name="typeAliasesPackage" value="com.offcn.pojo"></property>
       <!--设置插件-->
       <property name="plugins">
           <array>
               <bean class="com.github.pagehelper.PageInterceptor">
                   <property name="properties">
                       <!--使用下面的方式配置参数，一行配置一个 -->
                       <value>
                           helperDialect=mysql
                           reasonable=true
                       </value>
                   </property>
               </bean>
           </array>
       </property>
   </bean>
   ```
   
   **创建代理对象，使用IOC容器管理配置**
   
   MapperScannerConfigurer
   
   property name=basePackage
   
   ```xml
   <!--创建代理对象，使用IOC容器管理-->
   <!--UserDao ud = session.getMapper(UserDao.class);-->
   <!--此配置的内部的执行作用是：当前对象到指定的包中进行扫描，扫描到所有的持久层的字节码文件对象，然后框架底层调用session.getMapper()方法
   把每个持久层字节码文件对象作为是参数传入getMapper()方法，进而创建出来所有的持久层接口的代理对象，最后把这些代理对象放入IOC容器-->
   <bean id="mapperScannerConfigurer" class="org.mybatis.spring.mapper.MapperScannerConfigurer">
       <!--扫描包：持久层接口所在的包-->
       <property name="basePackage" value="com.offcn.dao"></property>
   </bean>
   ```
   
   4）业务层

### Day09

#### 回顾

1. Aop

   + 术语

     1）连接点

     2）目标对象

     3）代理对象

     4）织入

   + 应用场景

   + 事务管理 -- 声明式事务管理方式（另一种是：编程式事务管理方式）

2. spring 和 mybatis 整合

#### 内容

##### springmvc介绍

1. MVC --- （属于表现层）三层中
2. 开发的历程：Model1阶段 Model2阶段 mvc 三层架构 分布式 微服务
3. Springmvc --- Spring-webmvc，是spring 框架的一个子模块，轻量级、开源的、应用于企业级 web 项目的开发的、表现层框架、底层封装了 servlet，基于 MVC 分层思想。
4. springmvc 的执行流程（图为重点，虚框为mvc执行流程）

![favicon](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/favicon.png)

   ![image-20210715095652702](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210715095652702.png)

​	**前端控制器必须有。核心红色**

​	**映射器 适配器注释了也可以运行（框架可以自己找）**

​	如果需求多了 需要使用了必须配置

​	映射器和适配器的替代品

​	mvc:annotation-driven标签（不能同时存在）

​	**后端控制器自定义的类。绿色需要自定义实现，可以有很多**

​	**视图解析器，配置会产生变化**

​	**渲染不用配置**

​	**适配器模式**

5. springmvc 框架中涉及的模式

   适配器模式：接口、抽象类、实现类

6. springmvc 流程中涉及的 springmvc组件（组成元件、组成元素）

   1）前端控制器

   前端控制器是执行流程的中心，也是执行流程的出入口，前端的控制中心，配置一次、加载 springmvc 配置文件，不处理请求。

   2）映射器

   可以不配置、框架底层到 properties 文件中自动加载，也可以使用注解驱动代替配置，查找映射关系（哪个后端控制器处理哪个请求）

   3）适配器

   可以不配置，框架底层到 properties 文件中自动加载，也可以使用注解驱动代替位置，起到适配的作用，可以调用不同的后端控制器（例如tpec口可以连接不同设备）

   4）后端控制器

   需要自定义，可以有很多，其中的方法是处理某个请求的具体位置，后端控制器可以和业务层交互，可以封装模型和视图名

   5）视图解析器

   可以不配置，框架到 properties 文件自动加载，也可以配置（其他配置需求），通过视图名查找视图文件（文件被封装到视图对象中 View 类型的对象）

   6）mvc 注解驱动

   代替上面的映射器和适配器，也可以提供其他相关配置

##### 后端控制器类

1. 类中方法可以设置的返回值类型有哪些？

   1）ModelAndView

   A、特点：使用 ModelAndView 作为方法返回值的类型，可以使用 ModelAndView 类型的对象设置模型数据和视图名；被设置到 ModelAndView 中的模型**数据**最后会转入 **request** 域对象；响应方式为**转发**方式；会经过流程中的视图解析器。

   2）void

   A、特点：使用void作为方法的返回值类型，那么通过原生的 request 和 session 设置数据；响应方式可以转发、重定向；不在经过视图解析器

   sendRedirect 重定向不能访问WEB-INF 路径，重定向 / 代表项目根目录。

   3）String

   A、默认

   可以通过 Model（接口）、ModelMap（实现类）、Map 设置模型数据；数据同样转入 request；视图名就是返回值；是转发响应方式；经过视图解析器

   B、关键字设置：forward（转发） redirect（重定向）【冒号分割】

   与原生redirect不同，带了项目名

   **RedirectAttributes** 重定向参数(底层还是 session 传递 参数)，

   **addFlashAttribute**("name",xxx)可以重定向传递参，结合**@ModelAttribute**("name")注解用形参String xxx获取，

   可以通过 Model（接口）、ModelMap（实现类）、Map 设置模型数据；数据同样转入 request；关键字添加在返回值里面，返回值是视图名或者是URL；不经过视图解析器

   @ModelAttribute 从域对象获取值

   **@ResponseBody 声明是异步请求和响应，框架底层会借助jackson实现对象转json串，前端jQuery中底层也有操作：json串转回对象**

   jackson-databind 2.9.10版本

   高版本 springboot 需求

   4）实体类、集合等相关类型 -- **通常结合异步操作**

   A、特点：和异步结合、传递过程中使用 json 串（表单、超链接传递、ajax接收）（从后端控制器向也面传数据和从页面向后端传数据）

   (原生异步请求JS对象XHR createXHR open、send、get

   responseText

   XMLHttpRequest)

   ```javascript
   1. open(method, url, async) 方法需要三个参数:
   
   　 method：发送请求所使用的方法（GET或POST）；与POST相比，GET更简单也更快，并且在大部分情况下都能用；然而，在以下情况中，请使用POST请求：
   
   无法使用缓存文件（更新服务器上的文件或数据库）
   向服务器发送大量数据（POST 没有数据量限制）
   发送包含未知字符的用户输入时，POST 比 GET 更稳定也更可靠
   　url：规定服务器端脚本的 URL(该文件可以是任何类型的文件，比如 .txt 和 .xml，或者服务器脚本文件，比如 .asp 和 .php （在传回响应之前，能够在服务器上执行任务）)；
   
   　async：规定应当对请求进行异步（true）或同步（false）处理；true是在等待服务器响应时执行其他脚本，当响应就绪后对响应进行处理；false是等待服务器响应再执行。
   
   2. send() 方法可将请求送往服务器。
   
   3. onreadystatechange：存有处理服务器响应的函数，每当 readyState 改变时，onreadystatechange 函数就会被执行。
   
   4. readyState：存有服务器响应的状态信息。
   
   0: 请求未初始化（代理被创建，但尚未调用 open() 方法）
   1: 服务器连接已建立（open方法已经被调用）
   2: 请求已接收（send方法已经被调用，并且头部和状态已经可获得）
   3: 请求处理中（下载中，responseText 属性已经包含部分数据）
   4: 请求已完成，且响应已就绪（下载操作已完成）
   5. responseText：获得字符串形式的响应数据。
   
   6. setRequestHeader()：POST传数据时，用来添加 HTTP 头，然后send(data)，注意data格式；GET发送信息时直接加参数到url上就可以，比如url?a=a1&b=b1。
   
   PS：Fetch polyfill 的基本原理是探测是否存在window.fetch方法，如果没有则用 XHR 实现。
   ```

   5）四种返回值类型的对比

   A、数据的处理：ModelAndView 直接封装数据；void 是使用原生 request 或者 session 封装数据；String 是 Model、ModelMap、Map 封装数据；实体类或者集合类型是直接返回数据

   B、视图处理：ModelAndView 直接封装视图名；void是使用 request 或者 response 封装视图；String 返回值就是视图名；实体类或者集合不需要设置页面

2. 传参 -- 参数传递、参数绑定（从也面向后端控制器传递数据）

   1）主要介绍在页面把数据送到后端控制器之后，后端控制器如何接收数据

   2）方式：原生 request 方式、

   同名形参的方式

   （框架借助 ioc、di req.getParameterNames实现）、不同名形参方式、

   @RequestParam 实现名称匹配

   | 属性         | 属性释义                       |
   | ------------ | ------------------------------ |
   | value        | 请求参数名称（映射到参数）     |
   | required     | 是否必须包含参数，默认true     |
   | defaultValue | 没有提供参数，使用指定的默认值 |

   使用实体类封装、使用数据封装、使用集合封装
   
   **RequestMapping 默认可以缺省.do配置（会自动补齐）**

### Day10

#### 回顾

1. springmvc
   + 介绍
   + 执行流程、组件
   + 后端控制器的返回的返回值类型
   + 传参

#### 内容

##### 传参 -- 参数绑定-- <font color="red">重点</font>

1. 实体类

   1）实现

   同名形参，表单名和实体类字段名一致

   2）中文乱码处理方式

   超链接 get 请求方式中文没问题（Tomcat 版本问题）

   表单 post 请求方式 中文乱码

   过滤器配置，框架提供好

   ```xml
   <!-- 配置全局过滤Filter-->
   <filter>
       <filter-name>CharacterEncodingFilter</filter-name>
       <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
       <init-param>
           <param-name>encoding</param-name>
           <param-value>utf-8</param-value>
       </init-param>
   </filter>
   <filter-mapping>
       <filter-name>CharacterEncodingFilter</filter-name>
       <!-- 所有请求都被过滤-->
       <url-pattern>/*</url-pattern>
   </filter-mapping>
   ```

   3）在参数传递过程中，可能发生日期类型转换问题，如何解决？

   局部和全局方式

   A、局部方式是框架提供的

   @DateTimeFormat(pattern="yyyy-MM-dd") 将指定格式转成日期格式，要求送来的格式正确。（缺点每个地方都要加入）

   （400 状态码 代表坏请求 请求参数有问题，在此是类型转换问题）

   B、全局方式是自定义的

   先自定义一个日期转换的类 实现接口 Converter

   ```xml
   public class DateConverter implements Converter<String, Date> {
       @Override
       public Date convert(String dateStr) {
           // 将日期字符串转换成日期对象 返回
           SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd");
           Date date = null;
           try {
               date = format.parse(dateStr);
           } catch (ParseException e) {
               e.printStackTrace();
           }
           return date;
   
       }
   }
   ```

   

   转换器工厂：可以包含多种，自定义、框架提供

   ```xml
   <bean id="conversionService" class="org.springframework.context.support.FormattingConversionServiceFactoryBean">
       <property name="converters">
           <set>
               <bean class="com.bh.converter.DateConverter"></bean>
           </set>
       </property>
   </bean>
   ```

   

   工厂注册：

   ```xml
   <mvc:annotation-driven conversion-service="conversionService"/>
   ```

   

2. 数组

   同数组名即可（底层request.getParameterValues）

3. 集合 -- list、set、map

   **集合需要绑定在对象上，而不能直接写在Controller方法的参数中。**

   1）List 集合接收数据

   taglib 

   c 核心标签

   c:forEach 做便利输出

   items 结合 EL 表达式

   var 

   varStatus 下标 借助EL表达式 .index 获取下标

   fmt 格式化标签

   fmt:formatDate 

   value pattern，做日期格式化

   单双引号嵌套 防止错误

   PojoVO 设置 集合对象pojo 封装属性List<>，专门接收对象（前端加索引下标确定对象，动态下标）

   2）set 集合接收数据

   局限性 VO类 必须 newHashSet，并且构造方法add对象。

   3）map集合接收数据

   map[key名].对象属性

4. 异步

   1）从页面向后台传递的数据以 json 串方式传递

   ```javascript
   // 自定义json串
   var jsonData = "[{'uid':1003,'uname':'张飞','upwd':'123'},{......}]";
   
   // 异步请求
   $.ajax({
       url:"",
       type:"post",
       data:jsonData,
       dataType:"json",
       contentType:"application/json;charset=UTF-8",
       cache:false,
       success:function (obj) {
           console.log(obj);
       }  
   });
   ```

   **@RequestBody 把 json 串转成对象 底层还是jackson**

   **异步加@ResponseBody**

   ```java
   // json串转对象
   public void xx(@RequestBody 对象) {
       xxxdo
   }
   ```

##### 编程 -- 写项目的风格 -- restful

1. **REST 风格** （英文：**Representational State Transfer**）是Roy Fielding博士在2000年他的博士论文中提出来的一种[软件架构](https://baike.baidu.com/item/软件架构/7485920)风格。它是一种针对[网络应用](https://baike.baidu.com/item/网络应用/2196523)的设计和开发方式，可以降低开发的复杂性，提高系统的可伸缩性。

   直译：**表现层状态转换**

2. 是指资源发生状态转换，在表现层发生；即资源在表现层发生状态转换。

3. http://域名/xxxx

   http 协议 **无状态协议**（不知道从前、当前、未来的状态）
   
   1）网络上：URL对应资源，需要请求什么资源就对应URL，在资源请求过程中，会发生  由当前所处的状态转换成另一种状态，资源需要知道自己下一个要转换的状态是哪种状态，但是 URL 中 http 协议不带有状态信息，直接使用 http 协议不能告知资源要转换成哪种状态，解决？
   
   http 协议含有不同的请求方式，所以利用不同的请求方式来告知资源下一个要转换状态是什么
   
    2）请求方式和对应状态
   
      有不同的请求方式（8个？）
   
   Get 请求方式 查询状态 对应（资源变成查询状态、实际上就是实现资源的查询）
   
   Post 请求方式 增加状态 对应（资源变成增加状态，实际上对应就是资源的增加）
   
   Delete 请求方式 删除状态 对应（资源变成删除状态，实际上对应就是资源的删除）
   
   Put 请求方式 修改状态 对应（资源变成修改状态，实际上对应就是资源实现了修改）
   
   3）简而言之：如果采用 restful 风格来实现项目，那么设计 URL 的同时还要设计对应的**请求方式**
   
      <p style="color:red">使用"url+请求方式"表示一次请求目的
   
4. restful 风格的 URL 样式

   1）传统 URL 和参数的格式

   http://localhost:8080/项目名/资源名

   http://localhost:8080/项目名/资源名.do

   http://localhost:8080/项目名/资源名?key1=value&k2=value2

   2）restful 风格的 URL 和参数的格式

   http://localhost:8080/项目名/资源名(一般不添加扩展名，多采用名词复数做资源名)

   http://localhost:8080/项目名/资源名/value1/value2/......

5. 入门案例 -- springmvc 支持 result 风格

   **需要DispatcherServlet 路径由 *.do 改为 /**

   / 代表匹配所有（除了jsp页面请求）不能直接进入jsp页面

   1）使用 **@GetMapping 只处理Get请求**，表示资源要转为查询状态，资源查找

   405 请求不支持

   2）使用 **@PostMapping 只处理Post请求**

   **@PathVariable("xx") 从URL中通过指定变量名找到值，并注入给形参**

   ```java
   @GetMapping("xxx/{id}/{name}")
   
   public String xxx(@PathVariable("id") int uid,@PathVariable("name") int uname,) {
       
   }
   ```

   3）**post 请求 数据和 URL 分离 不用串入 URL**

   put、delete http 没有真正意义上实现

   **是spring模拟的 格式如下**

   ```html
   <!-- 固定格式-->
   <!-- 由post模拟put请求，put请求是被模拟-->
   <form action="xxx" method="post">
   <!-- 隐藏文本框-->
   <input type="hidden" name="_method" value="PUT">
   </form>
   ```

   **@PutMapping 只处理Put请求**

   **加入过滤器在前端控制器上(HiddenHttpMethodFilter)**

   ```xml
   <filter>
       <filter-name></filter-name>
       <filter-class>xxx.HiddenHttpMethodFilter</filter-class>
   </filter>
   ```

   4）**@DeleteMapping 只处理Delete请求**

   **Tomcat maven插件方式没问题**　Tomcat 原生方式会出错（jsp页面只能被get、post请求访问、put、delete不能请求jsp页面）

   > 类上加 RequestMapping 抽取方法相同的映射地址，框架自动将类片段和方法片段拼接匹配

   5）**DispatcherServlet 路径由 *.do 改为 / 产生的问题**

   + 静态资源也被后端控制器处理，倒置无法被读取

     正常情况不需要 Controller 去响应

   + 两种解决方式：

       ```xml
       <mvc:resources mapping="/js/**" location="/js/"></mvc:resources>
       ```
       
       ```xml
       <mvc:default-servlet-handler></mvc:default-servlet-handler>
       ```

##### 注解的总结

1. @Controller：IOC 实现

2. @RequestMapping：实现 url 请求和方法匹配

3. @GoMapping：实现请求的方法和匹配，只处理 get 请求方式

4. @PostMapping：实现请求的方法和匹配，只处理 post 请求方式

5. @DeleteMapping：实现请求的方法和匹配，只处理 delete 请求方式

6. @PutMapping：实现请求的方法和匹配，只处理 put 请求方式

7. @ResponseBody：声明是异步请求，对象转 json 串，返回

8. @ModelAttribute：从域对象获取数据；可以把方法的返回值数据暴露给视图（注解在方法上，方法返回值会返回到所有的页面，数据统一管理思想）

9. @RequestParam：传参时不同名实现匹配；默认值，是否必须传参

10. @RequestBody：从页面向后台串 json 串时，将 json 串转对象

11. @DatetimeFormat：实现局部的字符串类型转日期类型

12. @PathVariable：实现 restful 风格中从 url 里面获取数据，注入给指定形参

13. @CookieValue：从 cookie 中获取数据

14. @SessionAttributes：将数据转存到 session，在类上加注解，键值对(value="xxx键值对名")或者实体类型

    （EL表达式${sessionScope.xxx}只从session拿数据）

### Day11

#### 回顾

1. 传参
   + 使用实体类封装数据
   + 使用数组封装数据（放实体类）
   + 使用集合封装数据（放实体类）
   + 异步传递 json 串
2. Restful 风格
   + 表现层状态转换
   + 介绍
   + 使用
3. 注解的总结

#### 内容

##### 注解的总结

1. @CookieValue

   1）从 cookie 中通过指定的 key 获取数据

   2）cookie 会话跟踪 （请求时候电脑信息送到对方）sessionId 借用 cookie 送回服务器端

   3）使用

2. @RequestHeader

   1）获取请求头中的信息

##### 上传和下载

1. 上传 -- 从用户端把文件上传到服务器端

   1）注意事项

   A、前端页面：必须是 post 请求；表单中添加input[type=file];form[encType=multipart/form-data] 默认键值对格式、改成字符串格式（同步上传方式），异步需要form-data

   B、上传解析器 -- 把用户端向服务器端发送的内容，进行字符串截取，截取之后注入到对应的位置。

   C、考虑重名位置、考虑上传文件保存位置问题

   2）实现

   A、创建项目，导入依赖

   (commons-io 会传递依赖)

   ```XML
   <dependency>
   <groupId>commons-fileupload</groupId>
   <artifactId>commons-fileupload</artifactId>
   <version>1.4</version>
   </dependency>
   ```

   B、springmvc 配置文件中添加上传解析器

   (**id 名称是固定的**)

   ```xml
   <!-- 配置文件上传解析器 -->
   <bean id="multipartResolver"
   class="org.springframework.web.multipart.commons.CommonsMultipartResolver
   ">
   <!-- 编码 -->
   <property name="defaultEncoding" value="utf-8"/>
   <!-- 上传文件总大小限制 的单位B -->
   <property name="maxUploadSize" value="5242800"/>
   </bean>
   ```

   String 只保存文件名称，不能同名；要保存文件使用字节数组。

   C、前端（表单）

   D、后端（controller）

   ![image-20210719103546560](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210719103546560.png)

   ![image-20210719104228401](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210719104228401.png)

   文件存储：本机（任意路径）、远程存储（自搭建、别人搭建）

   fastDFS（linux 分布式文件系统）

   阿里云（对象云存储OOS）

   文件解析器先存在c盘临时位置，在使用 transferTo 复制，存储位置

2. 下载

   1）从服务器端向用户端下载文件

   2）实现

   A、准备下载列表

   B、点击链接，下载对应文件

   C、后端实现下载功能

   new File().list 文件名称列表展示

   **下载 原生方案就可以：一个头、两个流：响应头、本地读取流、远程写出流**

   ```java
   response.setHeader("content-disposition","attachment;filename="+name)
   ```

   **对字符二次编码 处理中文乱码**

   ```java
   name.getBytes("utf-8")
   new String(bytes,"iso8859-1")
   ```

##### 统一异常处理

编译时异常 加 thorw、try catch

**运行时错误**

代码、前端（正则表达式约束）

不可控异常 运行逻辑异常

异常默认处理方式：向上抛出

**抛给异常处理中心**![image-20210719141052635](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210719141052635.png)

1. 是指：在项目中没有进行异常处理的其他处理，采用 java 默认 异常处理方式， 即向上抛出的方式，你如由持久层抛给业务层，由业务层抛给控制层，控制层抛给异常处理中心；在异常处理中心进行异常的统一处理。

2. 实现：

   1）关注异常处理中心的实现

   A、自定义异常处理的类 -- 进而创建对象 -- 由容器管理即可

   实现 HandlerExceptionResolver

   实现的方法 resolveException 即为异常处理中心

   返回值 ModelAndView

   实现给运维保留信息：采用 Tomcat 自带的日志记录方式（log）；向数据库中保存；自定义日志；日志服务器等等；

   Exception e 就是抛出的异常对象

   e.printStackTrace() 可以使用流

   e.getMessage() 获取异常信息

   ![image-20210719144623930](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210719144623930.png)

##### 拦截器

1. 介绍

   1）对于静态资源不拦截的；对于向 controller 的请求都会先拦截（然后可以在程序中在进一步判断）

2. 和过滤器对比

   1）**过滤器 依赖于 web 容器**（servlet 容器 Tomcat造）（类加载造、方法调用造 load-on-startup）

   ```java
   // 非静态方法 servlet 对象 调用
   UserServlet{
   
   Init();
   
   Destroy();
   
   Service();
   
   }
   ```

   **拦截器 依赖于 springmvc 容器**

   2）过滤器采用函数回调方式实现过滤器功能；拦截器采用反射方式实现拦截功能，基于 AOP 思想进行切入

   3）拦截过滤的顺序：请求时先过过滤器再过拦截器；响应时先过拦截器再过过滤器（先进后出）

   4）过滤器可以过滤所有请求，拦截器只可以拦截 controller 的请求

   ![image-20210719151738132](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210719151738132.png)

3. 实现

   实现 HandlerInterceptor

   实现三个方法

   preHandler：请求处理之前调用

   postHandle：返回模型和视图名之前切入，可以获取到后端控制器向适配器返回的模型和视图名，**通常在此方法中可以实现模型和视图名的统一设置**

   afterCompletion：也没有拦截或者放行的功能，此方法的切入位置是在视图解析器向前端控制器返回视图文件时，可以获取到向 controller 发出请求时发生的异常。**统一异常处理另一套方案,无法设置返回页面**。

   （不使用异常处理中心的方案时）

   ![image-20210719153829238](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210719153829238.png)

   ```xml
   <!-- 配置拦截器 -->
   <mvc:interceptors>
   <mvc:interceptor>
   <!-- 对那些资源执行拦截操作 /**代表对所有方法 -->
   <mvc:mapping path="/**"/>
   <bean class="com.bh.interceptor.Myinterceptor1"/>
   </mvc:interceptor>
   </mvc:interceptors>
   ```

   /** 表示一级多级都可以拦截

##### 拦截器的使用案例

1. 需求：登录拦截

   有些请求不需要登录就可以直接访问；但是还有些请求是需要登录才可以访问的；当用户请求需要登录才可以访问的连接，使用拦截器拦截，进行登录验证（验证用户是否登录），登录则放行，反之则登录

2. 拦截器获取当前请求 url

   request.getRequestURI()

   if **endsWith() 判断后缀是什么**

   1）需要登录才可以访问的

   判断是否有登陆...

   2）不需要登录就可以访问的

   > 注意：url 片段前面是否有/，如果没有，则默认当前 url 统计目录下；如果有/，则代表当前根目录，端口后，不带项目名称

### Day12

#### 回顾

1. 注解

   @CookieValue、@RequestHeader

2. 上传和下载

   （拓展：responseEntity 工具类下载、压缩打包下载）

3. 统一异常处理

   （拓展：框架自带的实现 HandlerExceptionResolver 接口的类（异常解析类））

4. 拦截器

#### spring 总结

1. IOC 和 DI 介绍
2. IOC 和 DI 实现
3. 对象作用范围
4. 代理和 AOP
5. AOP 典型应用
6. 事务管理
7. SpringMVC 介绍
8. SpringMVC 处理流程 
9. SpringMVC 组件
10. 方法返回值类型
11. 传参
12. Restful 风格、静态资源拦截处理
13. 注解总结
14. 上传和下载
15. 统一异常处理
16. 拦截器

#### 内容

##### SSM 整合

1. 整合

   SSM -- SpringMVC、Spring、MyBatis

   协作：共同实现项目功能、完成项目的需求；

   SpringMVC 负责表现层的实现

   Spring 负责 IOC、DI、AOP 实现

   MyBatis 负责持久层的实现

2. 步骤：

   1. 创建项目、导入依赖

      ![image-20210720095211162](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210720095211162.png)

   2. SpringMVC 整合 Spring

      1）web.xml 中配置前端控制器、过滤器

      2）SpringMVC 配置文件（扫描包、注解驱动、视图解析器、类型转换工厂、上传解析器）

      3）测试

   3. Spring 和 MyBatis 整合

      1）Spring 配置

      扫描包、数据源、事务管理对象、事务注解驱动、MyBatis工厂、代理对象

      2）准备 MyBatis 映射文件

      增删改查、动态SQL 相关配置

      3）测试

   4. 把整合结果整合到项目中

      加载 Spring 配置文件

      等同于

      ```java
      ApplicationContext context = new XmlClasspathApplicationContext("applicationContext.xml");
      ```

      ```xml
      <context-param>
          <param-name>contextConfigLocation</param-name>
          <param-value>classpath:applicationContext.xml</param-value>
      </context-param>
      <listener>
          <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
      </listener>
      ```

      Spring 容器和 SpringMVC 容器，父子容器，Spring 是父，SpringMVC 是子；SpringMVC 可以调用父容器对象，反之不可以。

      ![image-20210720105507966](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210720105507966.png)

      ![image-20210720105616712](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210720105616712.png)

      1）web.xml 添加配置

      A、加载文件配置

      B、监听器配置

   5. 整体测试

##### Git

 之后要讲：博客项目、Linux、三阶段高级部分、项目

###### GIt的作用

追踪文件变更（备份）

协同开发（内容冲突、合并）

![image-20210720144001222](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210720144001222.png)

###### git 初始化

```shell
# 名称
git config global user.name "binghan" 
# 邮箱
git config global user.email 1114865162@qq.com 
# 查看
git config --list
# 在文件夹 打开 git bash 初始化 出现.git隐藏文件
git init
# 增加暂存区
git add .
# 提交本地仓库
git commit -m ""
# 查看提交记录 id
git log 
# 回退到id
git reset --hard 'commit_id'
# 删除 已提交的文件 删除工作区 不删除本地仓库
git rm 文件名
# 查看本地分支（-v 查看消息）
git branch (-v)
# 造分支
git branch 分支名
# 切换分支
git checkout 分支名
# 合并分区
git merge 分支名
# 删除分支
git branch -d 分支名
```

解决换行报错问题（Git 使用默认回车换行符CRLF，下面命令禁用）

`git config --global core.autocrlf false`

###### 使用码云Gitee

1. http 方式

```shell
# 克隆 https 方式
git clone "https地址"
```

2. ssh 方式

   生成公钥和私钥

```shell
# 克隆 ssh（Secure Shell） 方式
ssh -keygen -t rsa
# 将公钥方法码云 测试链接
ssh -t "git@gitee.com"
# 克隆内容
git clone "ssh地址"
```

到 ..四阶段 支付 对称非对称公钥私钥算法

###### 远程仓库操作

```shell
 # 查看远程仓库服务器
 git remote -v 
 # 添加远程仓库 建立连接
 git remote add origin "远程仓库地址"
 # 提交 主分支(第一次需要-u)
 git push -u origin master
 # 拉取文件
 git pull origin master
 # 代码冲突 push 失败 需要先 pull 代码，然后打开修改冲突在 push
```

### Day13

#### 回顾

1. SSM  整合
   + 分工：
   + 步骤：
   + SpringBoot 的基础
2. Git 工具
   + 版本控制工具
   + 集中式、分布式的分类
   + 概念
   + 使用命令窗口实现 git 操作

#### 内容

##### idea操作 git

1. 配置 VersionControl--Git 路径（bin或cmd下git.exe）

2. 配置 Editor--File Types 下 .gitignore 上传忽略的文件

   ![image-20210721093407390](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210721093407390.png)

3. 配置 Gitee 插件

   ![image-20210721093629381](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210721093629381.png)

4. Share Project on Gitee

   VCS--Import inot Version Control--Share Project on Gitee

5. 红棕色：新建的文件默认状态，不在暂存区、不在本地仓库

   绿色：刚添加到暂存区，本地库没

   蓝色：修改过文件，默认放在暂存区，不需要add，暂存区有，本地库有

   黑色：提交暂存区到本地库 变为黑色

6. Push 到远程库 VCS--Git--Push

7. 克隆远程库到本地

   ![image-20210721101905296](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210721101905296.png)

8. 分支

   VCS--Branches--New Branch

   右下角可以切换分支

   分支合并 Merge into Current

9. 回退

   Git show History--Log--Checkout Tag or Revision （发生在本地库）

10. 冲突

    多分支：分支合并冲突。冲突可手动修改

    多用户：协作开发冲突。冲突可手动修改

##### 项目案例 -博客

###### 环境搭建

导入项目依赖

使用mybatis 逆向工程

 表结构

![image-20210721141155366](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210721141155366.png)

###### 实现流程

![image-20210721142918509](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210721142918509.png)

实现用户分页条件查询

PageHelper 的 PageInfo、Navigator

![image-20210721160658794](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210721160658794.png)

实现用户删除：逻辑删除、物理删除

实现分类的查询，大类、子类查询

(RequestMapping 也叫做名称空间)

实现分类的大类的添加、子类的添加

**${param} EL表达式从url拿取值**

###  Day14

#### 回顾

1. idea中 Git 操作
2. 两个配置、插件安装
3. 分享操作，远程库、本地库
4. 克隆、拉取、版本回退、检出、创建分支、分支合并、多人协作、冲突合并

#### 内容

##### 项目案例 -博客

##### 实现流程

1. 实现分类列表的修改操作

   两部：先查询，回显数据到修改页面；在提交，请求加表单数据

   ![image-20210722093202590](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210722093202590.png)

2. 实现分类列表的删除操作

   分情况：

   博客类是否使用该分类，若使用，则将博客的类别外键设置为0，代表暂无分类

   > 注：外键约束，不能外键约束不存在的

   > 外键约束 不一定要有，代码逻辑约束也可

   若该类别有子类，先删除子类别，再删除该类别

   删除这样的操作需要用js 函数实现，格式a --href--javascript:--函数名，方便先提示在进入 controller 层 进行操作

3. 着重博客管理功能

   博客列表页面（异步实现、分页）

   ![image-20210722104155222](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210722104155222.png)

   先加载页面视图、在异步返回数据

   **@RestController 注解**

   **等价于 @Controller+@ResponseBody**

   使用 jQuery 的 预加载 

   前端获取 json 对象 

   将要更新的内容放到 ajax success方法中

   先清空 tbody，再向 tbody 添加

   找到要添加的元素节点，先使用方法 empty 清空，each 方法 循环 列表对象

   在 append 追加 标签与内容

   函数：毫秒值和日期字符串转换，把毫秒值转成日期字符串

   ```javascript
   var date = new Date(ms);
   var year = date.getFullYear;
   var month = date.getMonth()+1;
   var day = date.getDate();
   
   if(month <= 9) {
       month = "0" + month;
   }
   if(day <= 9) {
       day = "0" + day;
   }
   return year + "-" + month + "-" + day;
   ```

   博客列表删除操作

   博客详情评论查询操作
   
   登录、退出操作
   
   session的invalidate()方法，可以让session 失效

##### 晚自习递归删除 思考与实现（含有物理外键约束的做法）

```java
// 删除类别 多个 SQL 语句 加入事务
    @Override
    @Transactional
    public void delete(Integer typeid) {

        // 当前类是否被博客使用(先将博客的外键约束修改,修改为0暂无类别博客)
        // 该方法 加入到递归删除之前修改！！
        //updateBlogFKType(typeid);

        // 当前类是否有子类(先删除子类 递归删除子类，删除子类之前也需要修改博客外键约束)
        selectDeleteType(typeid);
    }

    // 修改博客类别外键的方法
    public void updateBlogFKType(Integer typeid) {
        // 封装条件
        BlogExample blogExample = new BlogExample();
        BlogExample.Criteria criteria = blogExample.createCriteria();
        // 寻找博客 （判断 外键 type_fk 为 当前类的 id）
        criteria.andTypeFkEqualTo(typeid);
        // 查询 结果封装 list
        List<Blog> blogs = blogMapper.selectByExample(blogExample);
        // 如果存在 博客
        if( null!=blogs && blogs.size()>0 ) {

            // 循环 每个博客
            for (Blog blog : blogs) {

                System.out.println("修改博客ID为："+blog.getBid());
                // 设置类别外键为0
                blog.setTypeFk(0);

                blogMapper.updateByPrimaryKey(blog);

            }

        }
    }


    // 递归删除子类的方法
    public void  selectDeleteType(Integer typeid) {

        // 临时 id 用来判断是否有子类别
        Integer tmp_big_typeid = typeid;
        {
            // 封装条件
            BtypeExample btypeExample = new BtypeExample();
            BtypeExample.Criteria criteria = btypeExample.createCriteria();
            // 寻找子类 （判断是否存在一个类的 pid 为当前类的 id）
            criteria.andTypePidEqualTo(tmp_big_typeid);
            // 查询 当前类的子类 封装 list 集合
            List<Btype> btypeList = btypeMapper.selectByExample(btypeExample);
            // 如果 存在子类
            if (btypeList != null && btypeList.size() > 0) {
                // 循环 每个子类
                System.out.println("==============开始循环id为--"+tmp_big_typeid+"--类的子类：");
                for (Btype btype : btypeList) {
                    // 获取 循环的当前子类的 id
                    // 防止将大类的 id 修改 在定义 临时变量
                    Integer tmp_child_typeid = btype.getTypeid();
                    // 开始递归判断
                    selectDeleteType(tmp_child_typeid);
                }
            }
            // 递归终止的条件：如果 不存在子类 就直接不会进行递归了
            // 删除的情况分为两种：1、当前类本来就不存在子类 2、当前类的子类已经递归删除完毕 （总的来说 就是没有子类了已经）
            // 首先需要外键约束的删除：  修改 类别为 当前类 的 博客 的外键为 暂无类别的 0
            // 然后可以直接删除当前 类
            System.out.println("---------开始修改博客外键id为:"+tmp_big_typeid);
            updateBlogFKType(tmp_big_typeid);
            System.out.println("---------修改博客外键id为:"+tmp_big_typeid+"修改成功!");
            System.out.println("----开始删除当前类的id为:"+tmp_big_typeid);
            deleteType(tmp_big_typeid);
            System.out.println("----删除当前类的id为:"+tmp_big_typeid+"删除成功！");
        }
    }
    // 删除的方法
    public void deleteType(Integer typeid) {
       btypeMapper.deleteByPrimaryKey(typeid);
    }
```

### Day15

#### 回顾

#### 内容

##### Linux

> 发布由1991年8月一 位来自芬兰赫尔辛基大学的年轻人
>
> 作者林纳斯 本纳第克特 托瓦兹（Linus Benedict Torvalds, 1969 年~）制作开源的Linux 内核（核心代码）
>
> 多用户、[多任务](https://baike.baidu.com/item/多任务/1011764)、支持[多线程](https://baike.baidu.com/item/多线程/1190404)和多[CPU](https://baike.baidu.com/item/CPU)的操作系统
>
> 组织和个人二次开发 实现功能扩展的发行版

Linux 发行版本 红帽、红旗、ubuntu、centos等

Ubuntu（个人爱好者开发的，社区版，版本更新迭代快，一天多版本？广大爱好者，最潮流、最新的，不稳定，世界范围用的多，不属于国内公司的发行版）

**主要CentOS**（组织开发维护的发行版，以稳定著称，版本更新迭代慢，CentOS后续不在更新，到8就没了）

Debian、Red Hat 等

##### CentOS版本

选用 7.3（1611版本）使用 4.1G 的版本

VMware14 虚拟机 安装(尽量保证相同版本卸载、安装)

高版本 改 低版本 容易造成不能用！！注册表残留

##### 安装 VMware 裸机

一个虚拟机 正常情况 最小 20 G

拆分多个文件 方便挂个硬盘 做 扩容

##### 安装 CentOS系统

BIOS是软件，CMOS是硬件，BIOS运行在CMOS上。

BIOS是基本输入输出系统，Basic input-output System的缩写，它负责系统从硬件启动到操作系统，当然还负责开机的自检，以及对计算机功能的设置，比如启用、禁用USB，更改硬盘接口模式等等。我们装系统时候按F2所进入的蓝色界面就是BIOS了，常见的BIOS有：Award BIOS AMI BIOS Phoenix BIOS等。

CMOS是Complementary Metal Oxide Semiconductor，互补金属氧化物，从名字就可以看出是硬件。它负责存储BIOS的信息，其通常由一块纽扣电池供电，通过取下电池，可以清除里面保存的数据信息。

(acer)宏碁：进入BIOS需按F2，进入Boot引导需按F12

WIN10 系统

找寻Intel Virtualization Technology选择Enable，按enter键,最后保存退出即可( F10 保存退出)

打开电脑 bios 系统 设置允许安装虚拟机（宽宽的大引脚，半硬件的系统 保存电脑基础设置 CMOS芯片 开机时候进去）

内存和实际内存挂钩的

处理器是模拟的

硬盘 20G + 不存在分区

CD/DVD(IDE)

.iso是电脑上[光盘镜像](https://baike.baidu.com/item/光盘镜像/10590214)（CD Mirror）的存储格式之一，因为其是根据ISO-9660有关[CD-ROM](https://baike.baidu.com/item/CD-ROM)文件系统标准存储的文件，所以通常在电脑中以后缀.iso命名，俗称iso镜像文件。

ctrl + alt 显示/隐藏 鼠标

安装 选择中文 需要确认硬盘大小

设置的密码 为 123 过于简单 确定 两次 用户名 默认为 ROOT

安装 300 多个文件 等 重启 

命令窗口 传文件不方便 所以远程连接

##### 远程连接

FinalShell 远程连接工具 免费 （XShell 有个人和收费）

Java 写的 界面简陋

知道 Linux 系统的ip

ifconfig（Network Interface Config 简化版本的 命令 ipaddr）

启用网卡 配置

```shell
# tab 自动补齐
cd /etc/
cd sysconfig/
cd network-scripts/
vi ifcfg-ens33
# 修改内容如下
ONBOOT=yes
```

ins 编辑 esc :wq 保存退出

reboot 重启虚拟机（或者重启网卡systemctl restart network.service）

蓝屏可能VM工作站版本问题

```shell
ifconfig
# 查看动态ip
```

FinalShell 连接 管理器 SSH 连接

##### Linux 目录结构

![image-20210723135847556](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210723135847556.png)

+ "/" : **根目录Linux文件系统的入口.也是最高级，最重要的的目录.**除衍生出其它目录，还和系统的开机，还原，系统修复有的，一般要求不要把任务应用程序直接放在根目录下，**如果满了，可能就登录不了了**（需要注意是否日志输出在根目录下）

+ "/bin":**基本系统所需要的命令**,主要是单用户模式下，还能执行的命令。主要有cat，mv,mkdir,cp,bash ,ls

+ "/boot":**内核和加载内核所需要的文件**.grub系统引导管理器也在这个目录下,存在/boot/grub/

+ "/dev":在linux系统下，任何设备及接口设备，都是以文件的形式存在，**设备文件存储目录**.像终端.磁盘等.比较重要的有/dev/null （crontab经常把不想输出输到这里）;/dev/zero;/dev/tty;/dev/lp*;/dev/hd*;/dev/sd*

+ "/etc":系统的主要配置文件都放在这个目录下，一般来说，这个普通人是看不到这些文件的;这里最好也不要放可执行文件。常见的目录有如下：

  /etc/inittab ;

  /etc/init.d/;

  /etc/modprobe.conf ;

  /etc/X11/ ;

  /etc/fstab/ ;

  /etc/sysconfig/ ;

  /etc/init.d/开机启动脚本放在这里;

  /etc/xinetd.d/ super daemon启动脚本放在这里

  <font color="red">/etc/sysconfig/network-scripts/网管配置放在下面下</font>

+ "/home":**普通用户的目录默认存储目录**.主文件夹有两种代号：

  ~ 代表这个用户的主目录

  ~dmtsai:代表 dmtsai的主文件夹

+ "/lib":**库文件和内核模块存放目录.主要是开机用到**，以及在/bin/;/sbin目录下命令会调用的库函数。/lib/modules会放内核相关的模块。

+ "/lib64":和/lib类似，主要是64的库函数

+ /usr **是存放可以分享与不可以动的内容**，不是user的缩写，而是 **UNIX Software Resource** 的缩写，就是UNIX操作系统的软件资源 

  主要子目录有：

  /usr/X**/ X Windows数据存在于此

  /usr/bin/ 绝大部分用户可用命令在此

  /usr/include/ C/C++等的头文件与包含文件在些。如果以源码的*.tar.gz安装软件时，可能会引用下面的文件

  /usr/lib/ 包含应用程序函数库及目标文件，以及不被一般用户惯用的执行文件或脚 本

  /usr/lib64/ 与/usr/lib/相似，会对64位的

  <font color="red">/usr/local/ 本机自己安装的的软件，建议安装到这里</font>，

  下面也有bin,etc,include,lib子目录，这些子目录功能大家可以想到

  /usr/sbin/ 非系统正常运行所需要的命令，最常见的就是网络服务器软件的daemon

  /usr/share/ 放共享文件的地方，基本是文本文件，可读的。子目录有

  /usr/share/man 在线帮助文件

  /usr/share/doc 软件杂项的说明文件

  /usr/share/zoneinfo 软件杂项的说明文件

  /usr/src 软件源码放在这里

+ "/media":**即插即用设备的挂载点自动存放在这个目录下.像U盘**,cdrom/dvd自动挂载后,就会在这个目录下.常见有/media/floppy,/media/cdrom 

+ "/mnt":**临时文件系统的挂载点目录**.以前和/media一样，但有专门/media后，专门做临时挂载

+ "/opt":<font color="red">第三方软件的存放目录</font>.什么叫第三方呢？像KDE，就是第三方的，只是集成到linux里，当然你可以放自己的东西到下面。

+ "/root":**Linux超级权限用户root的根目录**.单独存放，也方便在进入单用户模式的操作。

+ "/sbin":**基本的系统维护命令,只能由超级用户使用**.这些命令为开机、修复、还原系统过程所需要的。常见的命令有fdisk,fsck,ifconfig,init,mkfs

+ "/srv":存放一些服务器启动之后需要提取的数据.主要存放网络服务后的一些数据，如www,ftp

+ "/tmp":**临时文件目录,这个目录任何人可以访问，有可能需要定期清理**。

+ "/usr":存放用户使用系统命令和应用程序等信息.像命令.帮助文件等.

+ "/var":**存放经常变动的数据**,像**日志**.邮件等.这个目录下的数据，需要定期清理，最好写个脚本，放在crontab里。

  常见的子目录：

  /var/cache/ 执行中的缓存文件

  /var/lib/ 软件本身执行的过程中，用到的数据。比如Mysql数据一般放在/var/lib/mysql/;而rpm数据则放在 /var/lib/rpm/

  /var/lock/ 资源被锁时，放在此。有些资源只能一个程序使用，比如刻录机。

  /var/log/ 系统日志存在地，有可能需要定时清理

  /var/mail/ 系统邮件，看情况需要定时清理

  /var/run/ 某些程序或服务启动后，PID放在下现

  /var/spool/放置队列数据， 看情况需要定时清理

+ “/lost+found” 是ext2/ext3文件系统才产生的，目的是当文件系统产生错误里，将一些丢失的片段防在这个目录下。

+ “/proc” 是一个虚拟文件系统。放置内存中的数据，当有一个进程启动时，就有一个文件夹。比较重要的/proc/meminfo,/proc/cpuinfo可以通过这两文件查看内存和CPU情况，当然还有/proc/dma,/proc/interrupts,/proc/ioports,/proc/net/*等

+ “/sys” 和/proc相似，也是虚拟文件系统，主要记录内核相关，比如内核模块，内核检测的硬件信息。

##### Linux 常用命令

###### 1. 命令格式

命令的一般格式:command [options] [arguments] 

说明: 

+ command:命令名。 

+ options:命令的选项，一般是一个单词或字母。有的命令有选项，有的命令没有选项。选项前面一般有“-”符号。选项是对命令参数的补充，当存在参数时才可能有选项。 

+ arguments:命令的参数，有时候选项也带参数。有的命令有参数，有的命令没有参数。 

+ []:方括号表示可有可无的意思。 

###### 2. 文件和目录操作命令

需掌握的常用命令:cd, ls, locate, less, grep, chmod, cp, mv, mkdir, rm。

1. 链接

   + 软链接(相当于快捷方式)

   > ln -s  源文件  目标文件

   + 硬链接

   > ln 源文件 目标文件

   + 源文件被删除之后 硬链接文件依然有效 软链接文件失效

2. pwd 命令：“print working directory”(打印工作目录)

3. **ls 命令**：显示当前工作目录下的内容，包括子目录和文件

4. **ll 命令**：当前目录下子目录和文件列表的详细信息

   显示的文件列表格式如下: 

   `drwxr-xr-x 3 user group 102 Mar11 22:56 Filename `

   **文件列表显示了7个段，每一段分别的含义说明如下**:

   (1) 第1段，drwxr-xr-x，表示文件属性，

   第1个字母d表示这个是个目录，如果是“-”表示文件，l表示链接文件。

   d后面有9个字符，分成三组，每3个字符为一组。

   我们使用括号把他括起来:d(rwx)(r-x)(r-x)

   对应含意:文件类型(所有者权限)(组权限)(其他人 权限)。

   这三组分别说明的是:文件的所有者权限，文件所属的组权限，和“其他人”的权限。

   每一组中每一位字符的含意如下: 

   第 1 位表示是否有读权限，有读权限，显示“r”，没有读权限，显示“-”。

   第 2 位表示是否有写权限，有写权限，显示“w”，没有写权限，显示“-”。

   第 3 位表示是否有执行权限，有执行权限，显示“x”，没有，显示“-”。

   d(rwx)(r-x)(r-x)含意说明:

   第 1 组 d:表示目录。

   第 2 组(rwx):表示文件所有者对这个文件的权限是，有读，写，执行权限。

   第 3 组(r-x):表示文件所属用 户组对这个文件的权限是:有读，没有写权限，有执行权限。

   第 4 组(r-x):表示 其他人对这个文件的权限是:有读，没有写权限，有执行权限。

   (2) 第2段，目录下的文件和子目录个数

   3表示目录下有3个文件或 目录 (注意:每个目录都有一个指向它本身的子目录"." 和指向它上级目录的子 目录"..") 

   (3) 第 3 段，显示文件的所有者:user。

   (4) 第 4 段，显示文件所属用户组:group。 

   (5) 第 5 段，文件大小:102 byte。

   (6) 第 6 段，修改时间:Mar11 22:56。

   (7) 第 7 段，文件名:Filename。 

5. **cd 命令**：改变工作目录

   几个常用 cd 用法: 

   | 命令    | 功能                         |
   | ------- | ---------------------------- |
   | cd tmp  | 进入当前目录下的 tmp 目录。  |
   | cd ~    | 回到当前用户的 HOME 目录下。 |
   | cd /    | 回到整个系统的根目录。       |
   | cd /etc | 进入到/etc 目录              |
   | cd ..   | 回到上一级目录。             |
   
6. **locate 命令**：搜寻文件或目录

   locate命令要使用，需要先安装，安装命令：yum install mlocate（yum 到 linux 远程中央仓库下载）

   更新文件索引数据库，使用 updatedb 命令

   locate 有一个十分有用的选项 -r，它可以让你在搜索文件时使用正则表达式。

7. **find 命令**：文件查找命令（不搜文件夹）

   其一般命令格式为: 

   > find 位置 -name 文件名称

   也可以根据文件大小(通过 -size n 选项指定，-n表示小于多少,+n表示大于多少)、时间(如 -atime n 表示查找 n 天前访问过的文件) 来搜索文件。

   此外，find 命令同样支持在搜索文件时使用正则表达式，你只需指定 -regex 选项即可。

   find 和 locate 命令的区别:locate 是在建立好的索引的基础上进行查找， 查找要快很多。find 功能强大，但它是直接在硬盘上搜寻，查找速度比较慢。

8. clear 命令：用于清除终端窗口

9. **cat 命令**：concatenate(连锁)的简写，意思是合并文件。该命令可以显示文件的内容(经常和 more 搭配使用)，或者是将多个文件合并成一个文件

   cat 主要有三大功能: 

   (1) 一次显示整个文件。cat filename 

   (2) 从键盘创建一个文件。cat > filename << 结束符

   只能用于创建新文件，不能编辑已有文件。

   例如设置结束符为EOF

   cat > 1.txt << EOF 

   编辑文件完后，只需在最后一行键入“EOF”，然后回车即可。

   (3)将几个文件合并为一个文件: cat file1 file2 > file 

   参数:

   -n 或 --number 由 1 开始对所有输出的行数编号

   -b 或 --number-nonblank 和 -n 相似，只不过对于空白行不编号

   -s 或 --squeeze-blank 当遇到有连续两行以上的空白行，就代换为一行的空白行

   -v 或 --show-nonprinting 

10. more 命令：浏览超过一页的文件。（分页）

   在显示满一页时暂停，此时可按空格健继续显示下一个画面。

   按 Q 键退出显示。

   Enter键滚动显示下一行。

11. **less 命令**：浏览超过一页的文件。（同more）

    所不同的是less 命令除了可以按空格键向下显示文件外

    还可以利用上下键来卷动文件。

    当需要结束浏览时，只要在 less 命令的提示符“:”下按 Q 键即可。

12. head、tail 命令：文件浏览（看前/后多少行）

    例如：head/tail -10 xxx

13. **grep 命令**：文件中查指定字符串（显示一行）

    > grep 要查询的内容 文件名

14. **chmod 命令**：改变文件或目录的访问权限

    > chmod 权限数字 文件名

    由三位数字组成，每位数字求和，

    第 1 位数字代表文件所有者对这个文件的权限

    第 2 位 数字代表文件所属用户组对这个文件的权限

    第 3 位数字代表其他人对这个文件 的权限。

    权限属性对应的数字如下:

    | 权限属性 | 对应数字 | 说明                             |
    | :------- | -------- | -------------------------------- |
    | r        | 4        | 文件可以被读取                   |
    | w        | 2        | 文件可以被写入                   |
    | x        | 1        | 文件可以被执行(如果它是程序的话) |
    | -        | 0        | 相应的权限还没有被授予。         |

    （符号加减也可以u、g、o、a、+、-、=、r、w、x）

    查看修改：ll

15. **chown 命令**：改变文件的所有者

    命令格式: 

    > chown [-R] user[:group] file ...

    user : 新的档案拥有者的使用者 ID 

    group : 新的档案拥有者的使用者群体(group) 

    -R : 对目前目录下的所有档案与子目录进行相同的拥有者变更(即以递归的方式 逐个变更)

16. **cp 命令**：(copy)命令文件或目录复制到其他目录中

    命令格式:

    > cp <源> <目标目录> 

    拷贝目录(命令中需要使用-r 选项):

    > cp -r <源目录名> <目标目录> 

17. scp 命令：远程复制，从本地到远程以及远程 到本地的文件传输操作

    类似网上邻居

    > scp <源文件名> root@远程ip:/<目标目录> 

18. **mv 命令**：用于移动文件

    作用：**剪切、重命名**

19. **mkdir 命令**：建立目录

20. **rm 命令**：将文件或目录删除

    如果是链接文件，只是删除了该链接，原有文件保持不变

    如果要删除目录，命令如下:

    > rm -r 目录

    | 选项 | 说明                                                         |
    | ---- | ------------------------------------------------------------ |
    | -i   | 互动。提示你确认删除。这个选项可以帮助你避免误删文件。       |
    | -f   | Force，强制。代替互动模式，不提示地删除文件。除非 你知道自己在干什么，使用这个选项通常不是明智之举。 |
    | -v   | Verbose，显示操作过程的详细信息。显示文件的删除进度。        |
    | -r   | Recursive，递归。将会删除某个目录及其中所有的文件 和子目录。 |

###### 3. 文件归档和压缩命令

需掌握的常用命令:tar，zip，unzip，gzip，gunzip。

1. **zip/unzip 命令**：打包和压缩文件

   先安装 `yum install zip unzip`

   zip 命令用于打包和压缩文件。 

   压缩例子:

   > zip myfile.zip 目录/*

   解压例子:

   > unzip myfile.zip

2. **gzip/gunzip 命令** ：压缩/解开".gz"文件

   先安装 `yum install gzip gunzip`

   先打包、再压缩

   压缩:

   > gzip usr.tar

   解压:

   > gunzip usr.tar.gz

3. tar 命令：文件打包

   打包例子:

   > tar –cvf myfile.tar /tmp

   目录解包例子:

   > tar –xvf myfile.tar

   如果一个压缩包是.tar.gz格式，则可以先通过gunzip解压，然后再通过 tar 解包。

   也可以通过**tar命令直接解压解包**，只需在解包加个参数 z

   如：

   > tar -xzvf myfile.tar.gz tar

   | 选项 | 说明                                       |
   | ---- | ------------------------------------------ |
   | -c   | 建立新的归档文件                           |
   | -x   | 从归档文件中解出文件                       |
   | -v   | 处理过程中输出相关信息                     |
   | -f   | 指定的文件名                               |
   | -z   | 与-x 联用时调用 gzip 完成对 gz 文件 的解压 |

   **linux常见压缩包格式:tar.gz**

###### 4. 系统管理命令

需掌握的常用命令:free, top, shutdown。

1. **free 命令**：查看当前系统内存的使用情况

2. **shutdown 命令**：用于关机

   -c 取消前一个shutdown 命令。

   -f<秒数> 送出警告信息和关机信号之间要延迟多少秒。

3. reboot 命令：重启

4. date 命令：日期

5. cal 命令：日历

6. **top 命令**：性能分析工具(ctrl+c/z可以退出)

###### 5. 用户管理命令

需掌握的常用命令:useradd, passwd, su。

**groupadd、groupdel、groups、useradd、userdel、passwd、usermod（修改用户组）、su（切换用户 超管切换不需要密码 ；切超管后需要exit两次回到最初登录用户）、who、whoami（当前登录）**

###### 6. 网络管理命令

需掌握的常用命令:ping, netstat, ftp,ssh, telnet, wget。

1. **ping **
2. **wget （下载当前目录、需先安装）**
3. **ifconfig ipaddr **
4. **curl 访问页面 （本地测试、打开html代码）**

###### 7. 进程管理命令

常用命令:ps, kill。

1. **ps 命令**：显示程序的状态

   命令常用选项: 

   -a 显示所有用户的所有进程(包括其它用户)。 

   -x 显示没有控制终端的进程，同时显示各个命令的具体路径。 

   -u 按用户名和启动时间的顺序来显示进程。

   -aux 显示所有包含其他使用者的进程。

   >ps -aux | grep ping （带 --color 的不算是查找本身）

2.  **kill 命令**：终止一个程序

   > kill <-数字> PID 

   PID 是指进程 ID。

   | SIG 信号 | 对应数字 | 说明                                                         |
   | -------- | -------- | ------------------------------------------------------------ |
   | SIGINT   | 2        | 这个就是在 shell 下用 Ctrl+C 来结束一个程序时，发送的  信号，进程收到这个程序会结束。  你可以用 kill -INT pid 来发这个信号。 |
   | SIGQUIT  | 3        | 这个是在 shell 下用 Ctrl+\ 来结束程序时，发送的信号，        |
   | SIGKILL  | 9        | 这个信号之所以被称为“强杀”，就是因为无法改变进程收  到这个信号后所执行的动作，进程只能退出。 (前面说  的两个信号，虽然默认是退出，但是应用程序自己可以通  过 signal 系统调用来修改成其他动作，比如忽略那两个信 号等动作)。 |
   | SIGTERM  | 15       | 程序结束(terminate)信号, 与 SIGKILL 不同的是该信号可以 被阻塞和处理。通常用来要求程序自己正常退出 |

   -9 是强杀

###### 8. 服务管理命令

1. systemctl 服务操作start/stop/restart xxx

##### Linux 软件安装与卸载

三种：绿色--免安装；yum--联网安装（远程中央、镜像库），位置不详；安装包--（下载源码，需要先编译在安装；下载是编译后的直接安装）

1. FileZillas 使用（远程传输 基于FTP协议软件）

2. 安装 jdk 

   cd /etc  vi profile 配置环境变量 增加如下

   ```shell
      export JAVA_HOME=/usr/java/jdk
      export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
      export PATH=$JAVA_HOME/bin:$PATH
      export JRE_HOME=/usr/java/jdk/jre
   ```

   source profile 重启

   java version 测试

3. 安装 tomcat

   解压即用 环境变量不用配置

   cd bin/

   ```shell
   #启动不了 则需要增加权限
   chmod u+x startup.sh
   chmod u+x catalina.sh
   chmod u+x shutdown.sh
   ```

   ./startup.sh 启动（./ 是linux启动）

   ps -aux | grep tomcat 查看进程

   curl localhost:8080

4. 安装 mysq7

### Day16

#### 回顾

SSM 内容、注解、文件上传、异常处理、拦截器、SSM整合、Git学习、SSM博客项目、Linux

#### 内容

##### 软件安装

mysql 源码安装方式 

安装gcc 源码编译

首先安装依赖包，避免在安装过程中出现问题

```shell
yum -y install gcc gcc-c++
yum -y install cmake
yum -y install ncurses-devel
yum -y install autoconf
yum -y install perl perl-devel
```

 上面的依赖包安装也可以一行搞定

```shell
yum -y install gcc gcc-c++ cmake ncurses-devel autoconf perl perl-devel
```

创建mysql安装目录以及数据存放目录

```shell
mkdir /usr/app/software/mysql
mkdir /usr/app/software/mysql/data
```

创建用户、用户组

```shell
groupadd mysql
useradd -r -g mysql mysql
```

解压缩文件到当前文件夹

```shell
tar -zxvf mysql-5.6.35.tar.gz
```

安装解压 mysql 初始化 配置文件

```shell
cd mysql-5.6.35
cmake . -DCMAKE_INSTALL_PREFIX=/usr/app/software/mysql 
-DINSTALL_DATADIR=/usr/app/software/mysql/data 
-DDEFAULT_CHARSET=utf8 
-DDEFAULT_COLLATION=utf8_general_ci 
-DEXTRA_CHARSETS=all 
-DENABLED_LOCAL_INFILE=1
make && make install
```

注意事项：

如安装失败重新编译时，需要清除旧的对象文件和缓存信息。

```shell
make clean
rm -f CMakeCache.txt
rm -rf /etc/my.cnf
```

设置目录权限

```shell
cd /usr/app/software/mysql
chown -R mysql:mysql .
chown -R mysql:mysql data
```

将mysql的启动服务添加到系统服务中

```shell
cd /usr/app/software/mysql
cp support-files/my-default.cnf /etc/my.cnf
```

创建基础表：

```shell
cd /usr/app/software/mysql
./scripts/mysql_install_db --user=mysql
```

配置环境变量

```shell
 vi /etc/profile
 #在最下面添加下面两个值
 export MYSQL_HOME=/usr/app/software/mysql
export PATH=$PATH:$MYSQL_HOME/bin
#然后保存
```

让修改的profile文件立即生效

```shell
source /etc/profile
```

将mysql加入到可控制启动的服务的文件夹内，并命名mysql，即service可控制的服务名，至此可用service mysql start控制启动mysql

```shell
cd /usr/app/software/mysql/
cp support-files/mysql.server /etc/init.d/mysql
```

让mysql服务加入到开机启动指令管理的服务列表中

```shell
chkconfig --add mysql
```

开机自启动mysql服务

```shell
chkconfig mysql on
```

现在可以使用下面的命令启动mysql

```shell
 service mysql start
 # 停止 stop 重启 restart
```

连接到mysql

```shell
mysql -u root
```

为root添加远程连接的能力

```mysql
use mysql;
desc user;
GRANT ALL PRIVILEGES ON *.* TO root@"%" IDENTIFIED BY "root"; //为root添加远程连接的能力。
update user set Password = password('xxxxxx') where User='root';
select Host,User,Password from user where User='root'; 
flush privileges;  //刷新权限
exit  //退出
```

开启防火墙mysql3306端口的外部访问

```shell
firewall-cmd --zone=public --add-port=3306/tcp --permanent
```

重启防火墙

```shell
 firewall-cmd --reload
```

##### 博客部署

打包 war 包 ，部署 webapps下

开启8080端口

```shell\
firewall-cmd --zone=public --add-port=8080/tcp --permanent
```

重启防火墙

```shell
firewall-cmd --reload
```

浏览器登录自己的ip:8080/项目名

##### Shell 编程

1. 简介

   Shell 是一个命令行解释器。向 linux 系统内核发送请求以便运行程序的界面系统级程序，shell 脚本 启动、挂起、停止，编写一些程序。

   运维、大数据 写 shell 脚本

2. 编程案例

   1. 编写 shell 的格式规范
      + *.sh 命名
      + 开头为 #!/bin/bash 开头
      + 赋予用户执行的权限 +x（chmod +x 文件名）
      + 执行的时候 可以是相对路径或者是**绝对路径**
   2. 判断if、fi、循环分支等等

##### Redis 和 Nginx（好理解）

。。。。。。Dubbo和Zookper(稍难)

##### Redis介绍

> Redis 是一个开源（BSD许可）的，内存中的数据结构存储系统，它可以用作数据库、缓存和消息中间件。

1. 基于**内存**存储的、以key = value结构**存储**数据、开源的、可以用于实现数据库、缓存、消息中间件的系统（从数据库角度，类似mysql，但是没有表结构，是键值对）

2. 数据结构，以哪些结构存储数据？基本结构：字符串结构、列表结构、集合结构、有序集合结构

3. 有事务管理、可以实现数据复制、可以实现数据的持久化、可以实现 LUA 的脚本操作

4. Redis 有高可用、高性能特点：采用**集群**保证高可用和高性能，在实现集群的时候设置了**哨兵**的功能。

   Tomcat 的并发（同时访问一条连接） 200条 超过300宕机，需要使用集群。（搭建多个服务器，每个都相同 用户随机访问）

   **分布式**：不同功能分不同的模块，加上集群，一堆相同的登录、相同的评论等等等。一堆相同的是一个小集群，小集群与小集群是分布式。

   **哨兵**：用来监测集群的某个服务有没有宕机，是否正常工作，存在主服务。

   端口：6379

##### Redis 安装

1. 下载： http://download.redis.io/releases/

2. 解压： tar -xzvf

3. 安装：`make PREFIX=/usr/app/software/redis install`

   CentOS默认没有安装gcc，这会导致我们无法make成功。使用yum安装：

   `yum -y install gcc`

4. 启动

   + 前端启动方式

     通过 `./redis-server` 启动 由于不能实现交互 常采用后台启动方式

   + **后端启动方式**

     A、到解压文件夹中复制 redis.conf 文件到 安装目录的 bin 文件夹中

     B、vi redis.conf 找 （/来进行搜索/daemonize no 改为 yes）

     C、redis 先停止服务，在启动，

     通过 `./redis-server redis.conf`

##### Redis 的客户端登录操作

1. 自带的客户端

   安装目录中 bin 文件夹里面的 redis-cli

   ./redis-cli 启动

2. 其他客户端工具

3. 在 Java 程序中操作 -- 如果是远程连接

   A、后台启动方式 修改0.0.0.0

   B、把端口防火墙释放

   C、运行远程连接

   D、可选的密码设置

   

##### Redis 的操作 -- 相关命令

1. 全局性质的命令（是指不分数据结构，针对所有的数据结构都可以实现操作）

   A、停止服务器：shutdown [NOSAVE|SAVE] 持久化与非持久化

   B、退出客户端登录：exit/quit（当直接退出客户端登录，会自动持久化）（关机 内存->硬盘；开机 硬盘->内存）

   C、Redis 中默认有16个库，这些库从0-15 编号，客户端登录时，默认操作的是0号库；切换仓库的操作 `select n`（0号库没有数字提示）

   D、可以设置数据的有效时间 `expire key time`

   存储数据 `set key value` 

   E、查看数据的剩余有效时间，`ttl key`

   看到 -1 表示永久有效 -2 表示原来有 但是删除了

   有效期到来自动删除 正值表示剩余有效时间

   F、删除数据 `del key`

   G、查看当前库中有哪些key `keys *`

   H、把当前库的所有数据都删除 `flushdb`

   I、把所有库的所有数据都删除 `flushall`

   J、查看数据所属的结构/类型 `type key`

   K、判断当前库中是否存在某个键值对数据 `exists key` 1代表在 0代表无

2. 局部性质的命令（是指不同的数据结构，操作命令不同）

   A、字符串结构：string

   Value 部分整体就是一个字符串

   专属命令：

   存字符串结构的数据：**set**（一次只能存一对，当前库无同名 key、如果已经有同名 key，则替换操作）、mset（一次可以存多对）、取字符串结构的数据：get（一次只能获取一个值）、mget（一次可以获取多个值）

   向 value 部分追加新串：`append key value`

   计算 value 部分字符串的长度： `strlen key`

   截取字串： `substr key startnum endnum `

   当 value 部分是纯数字时，可以实现值的递增或者递减操作

   增/减1操作： `incr key` `decr key`

   指定增/减量：`incrby key num` `decrby key num`

   B、列表结构 --- list

   Value 部分是 list 列表（有序、可重复、下标访问）

   专属的命令：

   存列表结构的数据：lpush、rpush 

   `lpush key value1...` `rpush key value1...`

   取列表结构的数据：lrange： `lrange key startnum endnum` endnum 取-1 也是所有

   下标访问：lindex `lindex key index`

   删除两端数据：lpop （删除首值）rpop（删尾值）`lpop key` `rpop key`

   删除指定的值（删除几个）：lrem `lrem key count value`

   判断列表中成员个数：llen `llen key`

   C、集合结构 --- set

   value 部分是 set 集合

   专属的命令：

   存数据： sadd：`sadd key value1...`

   取数据：smembers：`smembers key`

   删除数据：随机删除 spop，指定要删除的值srem

   `spop key` `srem key value`

   交集：sinter：`sinter key1 key2`

   并集：sunion：`sunion key1 key2`

   差集：sdiff：`sdiff key1 key2`

   计算集合成员个数：scard ：`scard key`

   把数据从一个集合移动到另一个集合：smove：`smove key1 key2 value`

   D、散列结构 -- hash 结构

   Value 部分是 key=value

   存散列结构数据：hset（一次向 value 部分放一对）、 hmset（一次向 value 部分 放多对）

   获取散列结构数据：hget(一次获取一个)、hmget（一次获取多个）

   获取所有的小 key 的名称：hkeys： `hkeys key`

   获取所有的值：hvals： `havals key`

   指定增量（整数、浮点数）hincrby、hincrbyfloat

   `hincrby bigkey littlekey value` 

   `hincrbyfloat bigkey littlekey value`

   从 hash 结构中删除一个小对：hdel：`hdel bigkey littlekey...`

   获取小对的数量：hlen `hlen key`

   E、有序集合 --- sorted set/zset

   Value 部分也是小对；小对中的 key 部分必须是纯数字（score）；小对中的 key 部分允许重复；小对中 value 部分不允许重复

   zadd：`zadd bigkey littlekey value... `

   zrange：`zrange key startnum endnum`

### Day17

#### 回顾

1. Redis 数据库、缓存和消息中间件
2. **16个库、节点 --- 更小的单元 桶总数量一万四千多**
3. 通用命令、不同类型专用命令

#### 内容

##### Redis 的相关命令

1. 有序集合 -- zset/sorted set

   1）专属命令：

   a、添加：zadd： `zadd key littlekey value...` 

   b、升序获取：zrange： `zrange key 0 -1 ` 

   c、降序获取：zrevrange： `zrevrange key 0 -1`

   d、指定分数区间获取：zrangebyscore 

   `zrangescore key num lscore rscore `

   e、获取值对应的分数：zscore：`zscore key littlekey`

   f、删除一小对：zrem：`zrem key littlekey`

   > 注意：Redis能搭集群，但是Redis 是单线程，不进行多线程并行，事务可以可以把一段操作看成一个整体  开启与关闭事务
   >
   > MULTI 标记开始 UNWATICH 标记结束

##### Java 操作 Redis

1. 前提条件

   1）远程连接条件：后台启动、防火墙释放端口、允许远程连接、可选密码设置（ssm 架构项目需要设置密码、springboot 架构项目不需要）

2. 实现 java 中操作 Redis

   1）创建项目、导入 jar 包 -- Java 和 Redis 连接的包 jedis

   ```xml
   <dependencies>
   
       <dependency>
           <groupId>org.springframework</groupId>
           <artifactId>spring-test</artifactId>
           <version>5.2.9.RELEASE</version>
       </dependency>
   
       <dependency>
           <groupId>org.springframework</groupId>
           <artifactId>spring-context</artifactId>
           <version>5.2.9.RELEASE</version>
       </dependency>
   
       <dependency>
           <groupId>redis.clients</groupId>
           <artifactId>jedis</artifactId>
           <version>3.6.0</version>
       </dependency>
   
       <dependency>
           <groupId>junit</groupId>
           <artifactId>junit</artifactId>
           <version>4.12</version>
       </dependency>
   
       <dependency>
           <groupId>com.fasterxml.jackson.core</groupId>
           <artifactId>jackson-databind</artifactId>
           <version>2.9.10</version>
       </dependency>
   </dependencies>
   ```

   2）实现测试：建立连接、完成功能、释放资源

   **ping 命令 测试是否连通成功 返回 pong**

   ```java
    // 测试是否连通
       @Test
       public void testPing() {
   
           // 建立连接
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           // 实现测试
           String ping = jedis.ping();
           System.out.println(ping);
   
           // 释放资源
           jedis.close();
       }
   ```

   ```java
   // 向 Redis 0号库保存字符串结构数据
       @Test
       public void testSaveString() {
   
           // 建立连接
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           // 保存字符串 默认0号库
           jedis.set("name","zhangfei");
   
           // 释放资源
           jedis.close();
       }
   
       // 获取字符串结构数据
       @Test
       public void testGetString() {
   
           // 建立连接
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           // 获取字符串 默认0号库
           String name = jedis.get("name");
           System.out.println(name);
   
           // 释放资源
           jedis.close();
       }
   
       // 向1号库保存 list 结构数据
       @Test
       public void testSaveList() {
   
           // 建立连接
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           // 切换库
           jedis.select(1);
   
           // 保存集合
           jedis.lpush("list1","bh1","bh3","bh2","bh5","bh1");
   
           // 释放资源
           jedis.close();
       }
   
       // 获取 list 结构数据
       @Test
       public void testGetList() {
   
           // 建立连接
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           // 切换库
           jedis.select(1);
   
           // 获取集合
           List<String> list1 = jedis.lrange("list1", 0, -1);
           System.out.println(list1);
   
           // 释放资源
           jedis.close();
       }
   ```

3. Java 中的对象如何向 Redis 保存和获取

   **Hash 散列**

   ```java
   // 向 Redis 中保存实体类对象 -- 用 hash 散列结构存数据(保证是整体)
       @Test
       public void testPojoSave() {
   
           // 创建对象（视图数据库）
           User user = new User(1001,"张飞","123");
   
           // 建立连接 （配置文件）
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           jedis.select(2);
   
           Map<String,String> map = new HashMap<>();
   
           map.put("uid",user.getUid()+"");
           map.put("uname",user.getUname());
           map.put("upwd",user.getUpwd());
   
           jedis.hmset("user1",map);
   
           // 释放资源
           jedis.close();
       }
   
   // 从　Redis 库 获取数据给实体类对象
       @Test
       public void testPojoGet() {
           // 建立连接 （配置文件）
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           jedis.select(2);
   
           Map<String, String> map = jedis.hgetAll("user1");
   
           User user = new User();
   
           Set<String> strings = map.keySet();
   
           for (String key : strings) {
   
               if("uid".equals(key)) {
                   user.setUid(Integer.parseInt(map.get(key)));
               }
               if("uname".equals(key)) {
                   user.setUname(map.get(key));
               }
               if("upwd".equals(key)) {
                   user.setUpwd(map.get(key));
               }
           }
   
           System.out.println(user);
   
   
           jedis.close();
       }
   ```

   **Json串** --- <font color="red">常用方案</font>

   ```java
       // 向 Redis 库中保存对象数据 -- 使用 json 串格式 -- 利用 Redis 中 string 结构
       @Test
       public void testPojoJson() throws JsonProcessingException {
   
           // 创建对象（视图数据库）
           User user = new User(1001,"张飞","123");
   
           // 转换 json 串
           ObjectMapper objectMapper = new ObjectMapper();
           String json = objectMapper.writeValueAsString(user);
   
           // 建立连接 （配置文件）
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           jedis.select(2);
   
           // 设置 json 串
           jedis.set("user2",json);
   
           // 释放资源
           jedis.close();
   
       }
   
       // 从 Redis 库中获取 json 串，转回对象
       @Test
       public void testPojoGet2() throws IOException {
   
           // 建立连接 （配置文件）
           Jedis jedis = new Jedis("192.168.159.128",6379);
   
           jedis.select(2);
   
           String json = jedis.get("user2");
   
           ObjectMapper objectMapper = new ObjectMapper();
           User user = objectMapper.readValue(json, User.class);
           System.out.println(user);
           jedis.close();
   
       }
   ```

4. Redis 连接池

   ```java
       // 连接池操作
       @Test
       public void testPool() {
   
           // 建立连接池
           JedisPool jedisPool = new JedisPool("192.168.159.128",6379);
   
           // 从连接池中获取连接对象
           Jedis jedis = jedisPool.getResource();
   
           // 实现功能
           String ping = jedis.ping();
           System.out.println(ping);
   
           // 释放资源
           jedis.close();
       }
   ```

5. 实现 Redis 的整合 -- 把 Redis 功能整合到项目中 -- 使用 Spring框架实现把 Redis 整合到项目中（池子对象在 IOC 容器管理）

   1）最终就是实现使用 IOC 容器管理连接池对象即可

   初始化配置 PoolConfig 参数 最大连接对象、初始化对象；超时时间等等

   ```xml
    <bean class="redis.clients.jedis.JedisPool">
           <!-- 池的属性 -->
           <constructor-arg name="poolConfig" ref="poolConfig"/>
           <!-- Redis主机地址 -->
           <constructor-arg name="host" value="192.168.159.128"></constructor-arg>
           <!-- Redis主机端口 -->
           <constructor-arg name="port" value="6379"/>
           <!-- Redis密码 -->
           <constructor-arg name="password" value="123"/>
           <!-- 可以选择Redis数据库（要选择数据库，必须开启了密码） -->
           <constructor-arg name="database" value="0"/>
           <!-- 链接超时时间 -->
           <constructor-arg name="timeout" value="30000"/>
       </bean>
   
       <bean id="poolConfig" class="redis.clients.jedis.JedisPoolConfig">
           <!-- 最大连接数 -->
           <property name="maxTotal" value="10"/>
           <!-- 空闲连接数 -->
           <property name="maxIdle" value="2"/>
           <!-- 设置链接池的连接耗尽时，是否等待 -->
           <property name="blockWhenExhausted" value="true"/>
           <!-- 最大等待时间 -->
           <property name="maxWaitMillis" value="30000"/>
           <!-- 获取到连接时，是否检查链接的有效性 -->
           <property name="testOnBorrow" value="true"/>
       </bean>
   ```

   ```java
   @RunWith(SpringRunner.class)
   @ContextConfiguration(locations = "classpath:applicationContext.xml")
   public class RedisTest {
   
       @Autowired
       private JedisPool pool;
   
       @Test
       public void test1() {
           Jedis jedis = pool.getResource();
           String ping = jedis.ping();
           System.out.println(ping);
           jedis.close();
       }
   }
   ```

   Redis 加密码 

   `vi redis.conf` 搜索并增加 `requirepass 123`

   本机登录 `./redis-cli -a 密码`

   Java连接 

   `jedis.auth("密码");`

6. 缓存异常

   1）缓存穿透

   模拟多个请求、一直**请求不存在的数据**，给数据库压力太大（增加判断，防止恶意信息）

   2）缓存击穿

   **多线程访问同一个数据**，请求缓存存在的数据，多个线程访问，但是数据在**缓存有效时间到期了**，**同时穿过缓存向数据库发送多条SQL**（热点数据，设置缓存永久有效，防止数据库同时访问量大）

   3）缓存雪崩

   **同一时间缓存数据大面积失效**（让不同缓存失效实现错开）

7. 总结 -- <font color="red">重点</font>

   1）基本数据结构/数据类型

   2）常用命令

   3）缓存异常

##### Nginx介绍

1. 是一种服务器 由伊戈尔·赛索耶夫为[俄罗斯](https://baike.baidu.com/item/俄罗斯/125568)访问量第二的Rambler.ru站点（俄文：Рамблер）开发的
2. 提供的服务：**反向代理服务、负载均衡服务、web服务（动静分离）**、虚拟主机服务、邮件服务
3. 特点：轻量级、高性能、高并发、内存占用少/低耗、高稳定性、简单配置（5万并发 250个 Tomcat 的并发顶上一个 Nginx）

##### Nginx下载和安装

官网：[nginx.org](nginx.org)

**使用源码安装方式 安装目录好控制**

进入finalshell 进入 `cd /usr/app`

使用 wget 下载 

`wget http://nginx.org/download/nginx-1.20.1.tar.gz`

安装依赖

```shell
#安装依赖包
yum install gcc-c++
yum install -y pcre pcre-devel
yum install -y zlib zlib-devel
yum install -y openssl openssl-devel
```

解压解包

```shell
#解压解包
tar -zvxf nginx-1.20.1.tar.gz
```

配置文件

```shell
#切换路径 
cd nginx-1.20.1
```

```shell
#执行配置
#先进入nginx的目录
#执行
./configure --prefix=/usr/app/software/nginx
```

安装 nginx

```shell
#安装nginx
#执行 make
make PREFIX=/usr/app/software/nginx install
```

启动 nginx

```shell
#启动
#进入/usr/app/software/nginx/sbin
./nginx
```

测试

```shell
#测试：
curl http://localhost/
```

```shell
#防火墙放行端口
firewall-cmd --zone=public --add-port=80/tcp --permanent
#重启防火墙
systemctl restart firewalld.service
```

本地测试

![image-20210727145836599](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210727145836599.png)

##### Nginx使用

html 目录 下是 web项目空间

重启：`./nginx -s reload`

1. 反向代理服务器

   1）使用 Nginx 可以用于实现反向代理服务器，即 Nginx 实现反向代理功能

   2）反向代理？（翻墙 正向代理 代替客户端浏览器）

   由一方代替另一方实现功能；其中代替者和被代替者均为服务器；由一方服务器代替另一方服务器对外提供服务；

   ![image-20210727154234639](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210727154234639.png)

   3）实现反向代理操作

   A、搭建 Tomcat 集群（伪集群【一个电脑多个 Tomcat】真集群【一个电脑一个 Tomcat】）

   复制多个 tomcat

   ```shell
   mkdir tomcats
   cp -r tomcat/ tomcats
   cd tomcats
   mv toncat/ tomcat1
   cp -r tomcat1/ tomcat2
   cp -r tomcat1/ tomcat3
   ```

   同时启动 需要先改端口

   EditPlus 远程连接 编辑修改

   添加 ftp 账号 ip 用户名 密码

   高级选项修改端口 22 使用 sftp

   ![image-20210727155904358](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210727155904358.png)

   修改完成 Tomcat 端口 

   B、实现反向代理配置

   在修改 Nginx 配置

![image-20210727162146993](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210727162146993.png)

​	`./nginx -s reload` 重启 Nginx 浏览页面 进入的 Nginx 服务器 返回的 未知的 Tomcat 	集群服务器 中的一个

​	**默认的顺序**是**配置的顺序**： 轮流响应处理

2. 负载均衡

   1）什么是负载均衡：

   是指集群中处理请求，实现响应工作，应该实现一种均匀分配，即使集群中每个成员都有工作处理

   2）如何实现负载均衡

   A、采用不同的负载均衡策略实现

   B、有哪些策略：Nginx 有默认策略 -- 轮询、最少连接、权重、ip_hash 四种策略

   C、轮询策略：简而言之即按照集群配置，轮流实现工作

   ```shell
   upstream 名称 {
   server 192.168.159.128:8081;
   server 192.168.159.128:8082;
   server 192.168.159.128:8083;
   }
   ```

   D、权重：比值设置：加入 `weight = 值` ，默认为1，值越高 处理请求越多 长期来看，一段时间之后权重才可以体现

   E、最少连接：当前处理请求最少的成员，把新的请求交给他处理 加入 `least_conn;`

   F、ip_hash：是指当客户端向后台发送请求的时候，客户端的 ip 会送到后台去，后台的 Nginx 会获取到 ip，然后对 ip 进行 hash 值计算，在根据计算得到的 hash 值 找集群中某个成员处理请求和实现响应；此种配置策略有一个特点即：同一个客户的所有请求都是由同一个Tomcat 处理的。Session不同了 不能实现会话跟踪。`ip_hash`

3. 动静分离：静态资源不需要重复、不经过 Tomcat

   1）在项目中有些资源（静态资源 -- js、css、html、图片、音频、视频、动画）是不需要 Tomcat 服务器就可以被直接访问的，那么为了减少 Tomcat 服务器空间的浪费（集群中每个成员都有同一份静态资源 - 浪费空间），那么把每个成员中静态资源从 Tomcat 中分离出去（Tomcat 只剩下动态资源），分离出去的静态资源，当客户请求的时候（客户还能够正常请求），中间者 Nginx 起作用，负责把静态资源给客户响应回去，所以从此点功能上来说，Nginx 也能实现响应（响应的是静态资源），把 Nginx 也能看做是 web 服务器（实现 web 功能）

   ```shell
   location ~ \.(html|css|js|gif|jpg|jpeg|png|bmp|swf)$ {
       root /usr/app/software/nginx/html;
   }
   location ~ \.(jsp|do|action)$ {
       proxy_pass http://名称;
   }
   ```

### Day18

#### 回顾

Redis：

##### 有序集合

1. 操作命令

zadd、zrange

##### 在 java 中如何操作 Redis

1. 导入 Jedis，实现连接、完成功能
2. 整合

##### Nginx

1. 介绍
2. 功能
   + 反向代理【暴露的 Nginx 的 url】
   + 负载均衡

#### 内容

##### Zookeeper介绍

1. 概述

   Apache 基金会管理（像是Maven、Tomcat都是）

   开源分布式、提供**协调服务**（类似调度中心，协调**服务的提供方**）

2. 工作机制

   基于**观察者模式**设计的分布式服务管理框架（listener监听、setInterval计时、setTimeout定时）

   ![image-20210728094506134](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728094506134.png)

   **保存服务注册信息、对外提供服务信息**

   Zookeeper 可以搭集群 每个成员是一个节点

   ![image-20210728210317801](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728210317801.png)

   Server 三个角色：领导者、随从、观察者

   + Zookeeper 一个领导级别的存在，监测和管理多个服务
   + 集群中只要有半数以上节点存活，Zookeeper 集群就能正常服务
   + 数据一致性：从**同一客户端发起的事务请求**，最终将会严格地按照顺序被应用到 Zookeeper 中去
   + 更新请求顺序进行：**来自同一个 Client 的更新请求**按照其发送顺序依此执行
   + 原子性：所有事务请求的处理结果在整个集群中所有机器上的应用情况是一致的，也就是说，要么整个集群中所有的机器都成功应用了某一个事务，要么都没有应用。
   + 实时性：在一定时间范围，Client 能读到最新的数据

##### Zookeeper 数据结构

![image-20210728214005214](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728214005214.png)

Zookeeper 数据模型的数据结构与 Unix 文件系统很类似，都是树结构，树上有若干节点，**每个节点可以存1MB数据**，同时**每个节点**都是通过其**路径可以唯一标识**的

##### Zookeeper 企业应用场景

服务包括：统一命名服务（统一命名一般Dubbo使用域名、ip）、统一配置管理（配置文件同步、实时性的更新）、统一集群管理（**节点特性**和**watcher机制**；掌握节点状态并调整，实时检测节点变化并更新【集群底部守护线程管理】）、服务器动态上下线（动态更新，不影响整体运行）、软负载均衡（...）等。

##### Zookeeper 的安装与配置

下载连接 https://archive.apache.org/dist/zookeeper/zookeeper-3.5.9/

`wget https://archive.apache.org/dist/zookeeper/zookeeper-3.5.9/apache-zookeeper-3.5.9-bin.tar.gz`

新增zoo.cfg 修改data 目录

zookeeper 客户端访问端口 2181，不是内部集群端口

jps 查看进程 `./zkServer.sh start/status/stop` 开启服务、查看状态、停止服务 打开客户端：`./zkCli.sh`

##### Zookeeper 内部原理

1. Zookeeper 选举机制

   1）半数机制：集群中半数以上机器存活，集群可用。所以 Zookeeper 适合安装奇数台服务器

   2）Zookeeper 虽然在配置文件中 没有指定 Master 和 Slave。 但工作时，是有一个节点为 Leader，其他则为 **Follower**，Leader 是通过内部的选举机制临时产生的。

   Follower 集群扩展 参与选举 

   Observer 观察者 不参与选举

   3）

   ![image-20210728140941490](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728140941490.png)

   ![image-20210728140914070](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728140914070.png)

2. Zookeeper 节点类型

   1）持久节点（Persistent）：服务端客户端断开连接后，节点不删除 持久化目录节点、持久化顺序编号目录节点（只是 zook 给该节点名称进行顺序编号）

   2）短暂节点（Ephemeral）：服务端客户端断开连接后，节点自己删除 持久化目录节点、持久化顺序编号目录节点（只是 zook 给该节点名称进行顺序编号）

3. Zookeeper 读写机制

   ![image-20210728142043076](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728142043076.png)

##### Zookeeper 分布式安装部署（伪集群）

复制三份，没份的data清空，data路径更改

增加 myid 文件对应 id 存一个数字编号 1...

增加配置  增加如下 

服务端口

`server.1=ip地址"2888:3888"`

`server.2=ip地址"2889:3889"`

`server.3=ip地址"2890:3890"`

客户端端口也需要更改

第一个2181、第二个2182、依次递增

`clientPort=2181`

##### Zookeeper 常用命令

1. 启动客户端：`./zkCli.sh`
2. 显示所有操作命令：`help`
3. 看当前 znode 中所包含的内容：`ls /`
4. 查看当前节点详细数据：`ls -s /`
5. 分别创建 2 个普通节点：`create /shuihu "songjiang"` `create /shuihu/liangshan "liubei"`
6. 获得节点的值：`get /shuihu`
7. 创建短暂节点：`create -e /person2 "guanyu"`
8. 创建带序号的节点：`create -s /person2 "zhangfei"`
9. 修改节点内容：`set /person2 "zhangfei"`
10. 监听节点变化：`get /person2 watch`
11. 监听子节点变化：`ls /person2 watch`
12. 删除节点：`delete /person2`
13. 递归方式删除节点：`deleteall /person2`
14. 查看节点状态：`stat /person2`

##### Zookeeper 的 API 应用

1. 导入 jar 包

   ```xml
       <dependencies>
           <!--zookeeper-->
           <dependency>
               <groupId>org.apache.zookeeper</groupId>
               <artifactId>zookeeper</artifactId>
               <version>3.5.9</version>
           </dependency>
           <!-- 日志-->
           <dependency>
               <groupId>log4j</groupId>
               <artifactId>log4j</artifactId>
               <version>1.2.17</version>
           </dependency>
           <!--单元测试-->
           <dependency>
               <groupId>junit</groupId>
               <artifactId>junit</artifactId>
               <version>4.12</version>
           </dependency>
       </dependencies>
   ```

2. 测试

   ```java
   public class ZookeeperTest {
   
       // 集群地址
       private String host = "192.168.159.128:2181,192.168.159.128:2182,192.168.159.128:2183,";
       // 超时时间
       private int timeOut = 60000;
       // 客户端属性
       private ZooKeeper zkCli;
   
       // 先客户端登录
       @Before
       public void before() throws IOException {
           zkCli = new ZooKeeper(host, timeOut, new Watcher() {
               @Override
               public void process(WatchedEvent watchedEvent) {
                   try {
                       // 连根节点
                       zkCli.getChildren("/",true);
                   } catch (KeeperException e) {
                       e.printStackTrace();
                   } catch (InterruptedException e) {
                       e.printStackTrace();
                   }
               }
           });
   
       }
   
       // 创建节点的测试
       @Test
       public void testCreateNode() throws KeeperException, InterruptedException {
           // 参数1 要创建的节点路径 参数2 节点数据 参数3 节点权限 参数4 节点的类型
           String s = zkCli.create("/person2","caocao".getBytes(), ZooDefs.Ids.OPEN_ACL_UNSAFE,CreateMode.PERSISTENT);
           System.out.println(s);
       }
   
       // 获取节点的测试
       @Test
       public void testGetNode() throws KeeperException, InterruptedException {
           byte[] data = zkCli.getData("/person2", false, null);
           String str = new String(data);
           System.out.println(str);
       }
   
       // 获取某个上级节点的所有下级子节点
       @Test
       public void testGetChildren() throws KeeperException, InterruptedException {
           List<String> children = zkCli.getChildren("/", false);
           for (String child : children) {
               System.out.println(child);
           }
       }
   
       // 判断某个节点是否存在
       @Test
       public void testExists() throws KeeperException, InterruptedException {
           Stat exists = zkCli.exists("/person2", false);
           System.out.println(exists);
       }
   
       // 删除节点
       @Test
       public void testDelete() throws KeeperException, InterruptedException {
           zkCli.delete("/person2",0);
       }
   
   }
   ```

3. Zookeeper 总结

   单节点 Zookeeper 集群 Zookeeper

   节点就是 **存的 服务器服务地址** **ip对外查询地址** 位置地址 找到了去调用（服务协调）

##### Dubbo

##### 分布式系统概述

**软件架构的演变**

单一的应用架构 --> 垂直的应用架构 --> 分布式服务架构 --> 流动计算机构

a、单一的应用架构 

小型网站、小型管理系统、**所有功能部署到一个服务器里**，简单易用，并发少

缺点：性能扩展比较难、协同开发问题、不利于升级维护

b、垂直的应用架构（纵向的分割）

按功能**模块划分** **分层 MVC等** **服务器（Tomcat）集群** 模块独立部署，降低了维护部署的难度，团队各司其职更易管理，性能扩展方便

缺点：公共模块无法重复利用、开发性的浪费

c、分布式服务架构

集群内部相同的模块集群、不同集群之间不同内容。

RPC 分布式服务框架

d、流动计算架构

服务越来越多 **小服务**资源的浪费问题逐渐显现 分的功能**更细致 微服务** 提高集群利用率 提高机器利用率的

资源调度和治理中心（SOA）【Service Oriented Architecture】是关键 **建立在集群加分布式基础之上**

分布式：：**集群之间有调用关系 单向 双向 集群很多 调用关系很复杂**

**增加 服务治理 服务协调中心**

![image-20210728164401804](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728164401804.png)

而**微服务 是去中心化 没有中心**

两个**设计思想**

> SOA：（Service-Oriented Architecture）面向服务的架构；
>
> RPC：（Remote Procedure Call）远程过程调用	

##### Dubbo 简介

高性能、轻量级、开源 Java RPC 框架（**SOA、RPC 实现**）

三大核心能力：**面向接口的远程方法调用**、**智能容错和负载均衡**，以及**服务的自动注册和发现**。

Dubbox 是一个分布式服务框架，前身是阿里巴巴开源项目Dubbo，阿里不维护了（后交给 Apache），当当在Dubbo的基础上进行优化，继续维护，为了与Dubbo区分，命名Dubbox

Dubbox 致力于提供高性能和透明化的 RPC 远程服务调用方案，以及 SOA 服务治理方案。远程服务调用分布式框架。

##### Dubbo 架构图（菱形图）

五个组成角色

![image-20210728171424023](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210728171424023.png)

### Day19

#### 回顾 

1. Zookeeper

   + 是什么

   + 项目中应用场景
   + 数据树
   + 数据写操作
   + 3.5.x 新版本 多了个插件线程 占用8080端口，不能和 Tomcat 并存，采用改变端口或者分开部署方式解决；老版本没有

2. Dubbo

   + 介绍
   + 架构图示

#### 内容

##### Dubbo 的安装

Dubbo 使用 Zookeeper 作为注册中心

启动 Zookeeper Registry

`./zkService start`

安装监控中心 dubbo-admin 

https://github.com/apache/dubbo-admin 下载源码 

先配置 注册中心地址 application.properties 中 地址 

DubboAdminApplication 主程序启动 

provider 和 consumer 自己写的

provider 提供方 提供 web 和 service等 spring 容器

consumer 消费方 提供 web 和 controller springmvc等

使用Reference 注解 远程过程调用 返回接口实现类

都需要注册

![image-20210729102103039](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729102103039.png)

![image-20210729102304754](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729102304754.png)

配置文件

```xml
<!-- 扫描包-->
<context:component-scan base-package="com.bh"></context:component-scan>

<!-- 给服务提供者命名-->
<dubbo:application name="provider"></dubbo:application>
<!-- 注册中心地址-->
<dubbo:registry address="zookeeper://192.168.159.128:2181"></dubbo:registry>
<!-- 服务注册-->
<dubbo:annotation package="com.bh.service"></dubbo:annotation>
```

远程调用 RPC

容器 是服务提供者 使用的 dubbo 的 Service 注解

Tomcat 容器 （加载 Spring 配置文件） -- Spring 容器  （加载 service） -- 套一个 Dubbo 容器

Dubbo 是同步方案 **同步框架**对象提前得有，响应回复需要等待 ，返回成功才能运行 **后台的数据传输**

**异步框架** 不需要等待 什么时候有了再用 不需要等待

##### Dubbo 的高可用操作

1. 负载均衡

   + 随机策略（本质还是权重）
   + 轮询（按照权重轮询比率）
   + 最少活跃（本质还是最少连接）
   + 一致性 Hash（类似ip_hash，计算相关参数的hash，找集群中某一个）

2. 服务降级

   >当服务器压力剧增的情况下，根据实际业务情况及流量，对一些服务和页面有策略的不处理或换种简单的方式处理，从而释放服务器资源以保证核心交易正常运作或高效运作。
   >可以通过服务降级功能临时屏蔽某个出错的非关键服务，并定义降级后的返回策略。

   服务方忙碌集中处理重要的请求，不重要的服务，先返回一个提示信息，等待处理。

   服务方出问题了，宕机了，给一些提示信息，等待或者先处理之后的。

3. 服务容错

   集群调用失败时，Dubbo 提供了多种容错方案

   + Failover Cluster

     失败自动切换，当出现失败，重试其它服务器。通常用于读操作，但重试会带来更长延迟。可通过 retries="2" 来设置重试次数(不含第一次)。

   + Failfast Cluster

     快速失败，只发起一次调用，失败立即报错。通常用于非幂等性的写操作，比如新增记录。

   + Failsafe Cluster

     失败安全，出现异常时，直接忽略。通常用于写入审计日志等操作。

   + Failback Cluster

     失败自动恢复，后台记录失败请求，定时重发。通常用于消息通知操作。

   + Forking Cluster

     并行调用多个服务器，只要一个成功即返回。通常用于实时性要求较高的读操作，但需要浪费更多服务资源。可通过 forks="2" 来设置最大并行数。

   + Broadcast Cluster

     广播调用所有提供者，逐个调用，任意一台报错则报错 [2]。通常用于通知所有提供者更新缓存或日志等本地资源信息。

##### SpringBoot 简介

> Spring Boot 可以轻松创建独立的、生产级的基于 Spring 的应用程序，您可以“直接运行”这些应用程序。

简化了项目配置，甚至可以没有配置，xml 文件没有了

**简化开发**

两种 一种是联网 一种是maven项目自己写

快速开发 必须连接网络

https://start.spring.io/

idea中 注意版本选2.4.9 选择 启动器

![image-20210729140317798](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729140317798.png)

![image-20210729143826612](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729143826612.png)

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
        </plugin>
    </plugins>
</build>
```

插件保证打包时候 将 依赖打成 jar 包 Boot-INFO 的 lib 下

**通过 properties、yml/yaml 文件 设置 需要修改的参数**

##### SpringBoot 优势

1. 快速构建项目
2. 对主流开发框架无配置集成
3. 项目可独立运行，无需外部依赖Servlet容器（表面上是Java项目，本质上web项目）
4. 提供运行时的应用监控
5. 极大的提高了开发、部署效率
6. 与云计算的天然集成（SpringCloud）

<img src="https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729142543668.png" alt="image-20210729142543668"  />

**启动器（jar 包的集合） 借助了 maven 的依赖传递**

**敏捷开发的依据**  

##### SpringBoot 配置文件

1. 配置文件作用规范

   properties 预定义、自定义的键值对

   ymal/yml

2. yml 文件书写格式

   + key:空格value 如 name: zhangfei

   + 并列关系，左侧对齐

   + 有上下级关系的缩进几个

   + 设置数组属性用 - 、或	[]

   + 双引号则 有转义字符的功能

   + 单引号 为字符串拼接

   ```yaml
   name: zhangfei
   age: 30
   
   #person.pname=zhangfei
   #person.page=30
   #person.idcard.cname=123
   person:
     pname: "zhang \n fei"
     page: 30
     idcard:
       cname: 123
     ids:
       - 10
       - 20
       - 30
   ```

   注入实体类属性

   ```java
   @Component
   @ConfigurationProperties(prefix = "person")
   ```

##### SpringBoot 多环境配置

建立多个 yml 文件 不同文件不同配置

一个 application.yml 主文件 配置如下

```yaml
#springboot 预定义配置 -- 配置的作用就是设置当前项目处于哪个环境，就需要使用哪个配置文件
#spring.profiles.active 写名字即可
spring:
  profiles:
    active: test
```

**配置文件的位置**

项目类路径下/类路径config 文件夹下 （package 打包之后的路径 Boot-INFO 的 classes 是类路径）（磁盘路径 项目config开发可以用 不常用）

##### SpringBoot 的 Web 开发

静态资源 建目录 a/b

四个默认目录

![image-20210729163322095](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729163322095.png)

**自定义目录**

```yaml
# 自定义静态资源保存位置
spring:
  resources:
    static-locations: classpath:/static/,classpath:/resources/,classpath:/public/,classpath:META-INF/resources/,file:C:\Users\Administrator\Desktop\pic\
```

**maven 图片打成 jar 包 放到本地仓库 jar包依赖配置**

建立目录 src/main/resources/META-INF/resources/webjars 放图片

![image-20210729205835690](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210729205835690.png)

install 安装到本地仓库.

需要使用的地方导入 maven 依赖即可

主启动类 格式固定

```java
@SpringBootApplication
public class SpringBootThirdApplication {

    public static void main(String[] args) {

        SpringApplication.run(SpringBootThirdApplication.class,args);
    }
}
```

**静态资源的访问：**

第一种

localhost:8080/图片名称 

第二种

localhost:8080/webjars/图片名称

### Day20

#### 回顾

1. Dubbo
2. SpringBoot
3. 静态资源处理 Nginx服务器也可以 动静分离

#### 内容

##### SpringBoot 中的拦截器

```java
public class FirstInterceptor implements HandlerInterceptor {
    @Override
    public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
        System.out.println("放行或者拦截的方法。。。。。。");
        return true;
    }
}
```

```java
// 自定义配置类 声明此类配置类
@Configuration
public class CustomConfig implements WebMvcConfigurer {
    // 拦截器注册 -- 把自顶有拦截器实现注册
    @Override
    public void addInterceptors(InterceptorRegistry registry) {
        registry.addInterceptor(new FirstInterceptor()).addPathPatterns("/**");
```



##### SpringBoot 中的视图控制器 -- 定义全局视图

在当前项目中，由客户端**只要是发出/main请求**，就**返回main.html视图页面** 

多个服务请求同一个页面 所以定义一个全局的视图 进行重定向

```java
//配置视图控制器
@Override
public void addViewControllers(ViewControllerRegistry registry) {
    registry.addViewController("/main").setViewName("/main.html");
}
```

```java
@RequestMapping("sec")
public String sec() {
    return "redirect:/main";
}

@RequestMapping("third")
public String third() {
    return "redirect:/main";
}
```

##### SpringBoot 中的页面

需求：**数据传递** 与 **页面模板**

页面模板 不同的商品详情、不同的新闻详情 都是类似的模板。

**模板引擎/网页静态化技术 Thymeleaf、Freemarker**

**template文件夹是受保护的，不能直接访问，为了前端页面先渲染时有数据，必然要用同步方案。**

模板引擎工作原理图

![image-20210730211745080](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210730211745080.png)

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>入门案例</title>
</head>
<body>
<p>模板引擎入门案例</p>
<p th:text="${name}"></p>
</body>
</html>
```

```yaml
# 禁用 thymeleaf缓存的设置
spring:
  thymeleaf:
    cache: false
```

+ 实体类对象的解析

  ```html
  <p>实体类对象如何解析</p>
  <p>
      <span th:text="${user.uid}"></span>-
      <span th:text="${user.uname}"></span>-
      <span th:text="${user.upwd}"></span>
  </p>
  ```

+ 集合对象的解析

  ```html
  <!-- c:foreach items="" var="" varStatus=""下标-->
  <p>集合对象如何解析：集合的遍历</p>
  <p th:each="user,iterStat : ${list}">
      <!-- INDEX 绝对的下标 从 0-->
      <span th:text="${iterStat.index}"></span>-
      <!-- count 从 1 开始计数-->
      <span th:text="${iterStat.count}"></span>-
      <span th:text="${user.uid}"></span>-
      <span th:text="${user.uname}"></span>-
      <span th:text="${user.upwd}"></span>
  </p>
  ```

+ 如何处理图片

  ```html
  <p>如何处理图片</p>
  <img th:src="${imageUrl}">
  <p>如何处理超链接</p>
  <a th:href="${url}">百度</a>
  ```

+ 如何处理字符串

  ```html
  <p>如何处理字符串片段</p>
  <p th:text="'字符串片段' + ${str}"></p>
  <p th:text="|字符串片段${str}|"></p>
  <!-- 格式错误 只能以上两种-->
  <!--<p th:text="字符串片段${str}"></p>-->
  ```

+ 网页内容分割片段

  头部 header 定义 相当于 id

  ```html
  <p>头部页面片段</p>
  <h3 th:fragment="headerH3">头部共用部分</h3>
  ```

  三种引入方式

  ```html
  <!-- 页面片段引入-->
  <!-- 三种 引入方式-->
  <!-- inser 插入 整个内容往里添加 div>h3>文字-->
  <div th:insert="~{header ::headerH3}"></div>
  <!-- replace 替换 没有div了 h3>文字-->
  <div th:replace="~{header ::headerH3}"></div>
  <!-- include 包含 没有了h3 只有文字 div>文字-->
  <div th:include="~{header ::headerH3}"></div>
  ```

+ 模板判断选择

  ```html
  <p>选择结构</p>
  <!-- 条件成立-->
  <span th:if="${sex == 1}">男</span>
  <!-- 条件不成立-->
  <span th:unless="${sex == 1}">男</span>
  <!-- 多向判断-->
  <p th:switch="${score}">
      <span th:case="60">及格</span>
      <span th:case="70">中等</span>
      <span th:case="80">良好</span>
      <span th:case="90">优秀</span>
  </p>
  ```

+ 内置函数

  ```html
  <p>内置函数</p>
  <p th:text="${date}"></p>
  <p th:text="${#dates.format(date,'yyyy-MM-dd')}"></p>
  <p th:text="${#dates.year(date)}"></p>
  <hr>
  <p>数字操作</p>
  <p th:text="${num}"></p>
  <p th:text="${dou}"></p>
  <!-- 格式化 小数点前凑够5位，后保留两位 进位-->
  <p th:text="${#numbers.formatDecimal(dou,5,2)}"></p>
  <!-- 生成序列 1到10-->
  <p th:text="${#numbers.sequence(1,10)}"></p>
  <p th:each="seq : ${#numbers.sequence(1,10)}">
      <span th:text="${seq}"></span><br>
  </p>
  <hr>
  <p>字符串操作</p>
  <p th:text="${str}"></p>
  <!-- 省略多余的字符-->
  <p th:text="${#strings.abbreviate(str,30)}"></p>
  ```

+ 渲染 css、js 路径

  同时配置 href/src 与 th:href/src 路径正确 并且提示正常

  ```html
  <link rel="stylesheet" type="text/css" href="main.css" th:href="@{/main.css}">
      <script type="text/javascript" src="jquery.js" th:src="@{/jquery.js}"></script>
  ```

##### SpringBoot 整合 单元测试

还是去主启动器启动 **加入测试启动器**、**注解换SpringBootTest**

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>
```

```java
@SpringBootTest
class Springboot03Thymeleaf2ApplicationTests {
    @Autowired
    private User user;

    @Test
    void contextLoads() {
        System.out.println(user);
    }
}
```

##### SpringBoot整合 mybatis

mybatis 整合启动器

mysql 驱动

```xml
<dependency>
    <groupId>org.mybatis.spring.boot</groupId>
    <artifactId>mybatis-spring-boot-starter</artifactId>
    <version>2.1.4</version>
</dependency>

<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <scope>runtime</scope>
</dependency>
```

配置文件

```yaml
#数据源配置
spring:
  datasource:
    driver-class-name: com.mysql.jdbc.Driver
    url: jdbc:mysql:///mybatis?characterEncoding=utf8
    username: root
    password: admin

#配置mybatis规则
mybatis:
  mapper-locations: classpath:mappers/*.xml # sql映射文件位置
  type-aliases-package: com.bh.pojo # 配置了实体的别名
  configuration:
    map-underscore-to-camel-case: true # 开启驼峰命名法 不写全局 配置文件在 configuretion 对象中
    #该配置项就是指将带有下划线的表字段映射为驼峰格式的实体类属性。
```

生成代理对象

局部配置 Mapper注解 获取持久层代理对象 

```java
// 局部配置 -- 获取持久层代理对象
@Mapper
public interface UserDao {
    List<User> selectAll();
}
```

全局配置 主启动器上 MapperScan(basePackages = "com.bh.dao")

```java
@SpringBootApplication
// 全局配置 -- 获取持久层代理对象
@MapperScan(basePackages = "com.bh.dao")
public class Springboot04MybatisApplication {

    public static void main(String[] args) {
        SpringApplication.run(Springboot04MybatisApplication.class, args);
    }

}
```

##### SpringBoot 整合 Redis

开启Redis

```shell
# 进入bin目录
cd /usr/app/software/redis/bin
# 后台启动 redis
./redis-server redis-conf
# 查看 redis 进程
ps -aux | grep redis
# 进入 redis 客户端 -a 密码 123
./redis-cli -a 123
# 清空所有库中的所有数据
flushall
```



加入 启动器

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-redis</artifactId>
</dependency>
```

配置文件 application.yml 端口默认6379

```yaml
spring:
  redis:
    host: 192.168.159.128
    password: 123
```

注入操作Redis的模板

RedisTemplate、StringRedisTemplate两种模板

```java
// 注入 redis 模板对象 保存键值对数据 区别
// RedisTemplate 模板会自动给 key、value 加入序列化数据，显示十六进制编码
// StringRedisTemplate模板不会自动给 key、value 加入序列化数据，中文显示
@Autowired
private RedisTemplate redisTemplate;

@Autowired
private StringRedisTemplate stringRedisTemplate;
```

**主启动类排除数据源 自动添加**

 **exclude ={DataSourceAutoConfiguration.class}**

![image-20210730225444619](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210730225444619.png)

**RedisTemplate 模板会自动给 key、value 加入序列化数据，显示十六进制编码**

**StringRedisTemplate模板不会自动给 key、value 加入序列化数据，中文显示**

**不能混着用 用哪个操作哪个对象**

方法如下：

`redisTemplate.boundValueOps().set/get`

```java
// 测试 -- 向库中添加数据 -- string类型
// set
@Test
public void testSaveString() {

    redisTemplate.boundValueOps("name1").set("张飞");
    // 设置有效时间 TimeUnit 泛型的值为单位
    redisTemplate.expire("name1",1, TimeUnit.MINUTES);

}

// get
@Test
public void testGetString() {
    String name1 = (String) redisTemplate.boundValueOps("name1").get();
    System.out.println(name1);
}

// set
@Test
public void testSaveString2() {

    stringRedisTemplate.boundValueOps("name2").set("李炳汉");

}

// get
@Test
public void testGetString2() {
    String name1 = (String) stringRedisTemplate.boundValueOps("name2").get();
    System.out.println(name1);
}

// 删除数据
// del
@Test
public void testDelString() {
    redisTemplate.delete("name1");
}

// 列表类型的操作
// lpush
@Test
public void testSaveList() {
    redisTemplate.boundListOps("list1").leftPushAll("aaa","bbb","ccc","ddd","aaa");
}

// lrange
@Test
public void testGetList() {
    List list1 = redisTemplate.boundListOps("list1").range(1, -1);
    System.out.println(list1);
}

// lindex
@Test
public void testIndex() {
    String list1 = (String) redisTemplate.boundListOps("list1").index(1);
    System.out.println(list1);
}

// lrem
@Test
public void remove() {
    redisTemplate.boundListOps("list1").remove(1,"aaa");
}

// set 集合操作 无序
// sadd
@Test
public void testSaveSet() {
    redisTemplate.boundSetOps("set1").add("aaa","bbb","ccc","ddd");
}

// smembers
@Test
public void testGetSet() {
    Set set1 = redisTemplate.boundSetOps("set1").members();
    System.out.println(set1);
}

// srem
@Test
public void testDeleteSet() {
    redisTemplate.boundSetOps("set1").remove("aaa");
}

// 散列结构操作

// hmset
@Test
public void testSaveHash() {
    Map<String,Object> map = new HashMap<>();
    map.put("name","张飞");
    map.put("age",30);
    map.put("bir",new Date());
    redisTemplate.boundHashOps("hash1").putAll(map);
}

// hkeys、hget 结合使用
@Test
public void testGetHash() {
    Set<String> keys = redisTemplate.boundHashOps("hash1").keys();
    for (String key : keys) {
        Object value = redisTemplate.boundHashOps("hash1").get(key);
        System.out.println(key+"--"+value);
    }
}

// hdel
@Test
public void testDeleteHash() {
    redisTemplate.boundHashOps("hash1").delete("name");
}
```



下周 Dubbo 整合 Mybaits-Plus **简化开发是目的**

### Day21

#### 回顾

1. 静态化技术--模板引擎
2. 整合 Redis、mybatis、junit

#### 内容

##### SpringBoot 整合 Dubbo -- <font color="red">重点</font>

+ Zookee

1. 启动 Zookeeper

   `./zkServer.sh start`

   `ps -aux | grep zookeeper`

2. 打开 dubbo-admin

3. 先准备提供者、在准备消费者

   1）导入 jar、web 项目

   ```xml
   <!-- zookeeper 客户端-->
   <dependency>
       <groupId>com.101tec</groupId>
       <artifactId>zkclient</artifactId>
       <version>0.9</version>
   </dependency>
   <!-- 整合 dubbo 启动器-->
   <dependency>
       <groupId>com.alibaba.spring.boot</groupId>
       <artifactId>dubbo-spring-boot-starter</artifactId>
       <version>2.0.0</version>
   </dependency>
   ```
   
   2）对外提供功能、远程调用功能
   
   需要两个注解 因为 使用了 SpringBoot 大容器套小容器
   
   Component（Ioc 容器管理对象） 和 
   
   Service（Dubbo 容器管理对象） 注解都加上
   
   远程调用功能需要先造接口一模一样
   
   3）yml配置文件
   
   名称、端口、注册中心地址、注册哪些服务
   
   ```yaml
   spring:
     dubbo:
       application:
         name: provider
       registry:
         address: zookeeper://192.168.159.128:2181
       scan: con.bh.service
       protocol:
         name: dubbo
   
   #tomcat端口
   server:
     port: 8000
   ```
   
   主启动器 开启 EnableDubboConfiguration
   
   thymeleaf 也需要启动器！！！
   
   4）结果
   
   ![image-20210802210422865](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210802210422865.png)

##### MyBatis-Plus

1. 简介

   [MyBatis-Plus](https://github.com/baomidou/mybatis-plus)（简称 MP）是一个 [MyBati](http://www.mybatis.org/mybatis-3/)的增强工具，在 MyBatis 的基础上只做增强不做改变，为简化开发、提高效率而生。

2. 特性

   - **无侵入**：只做增强不做改变，引入它不会对现有工程产生影响，如丝般顺滑
   - **损耗小**：启动即会自动注入基本 CURD，性能基本无损耗，直接面向对象操作
   - **强大的 CRUD 操作**：内置通用 Mapper、通用 Service，仅仅通过少量配置即可实现单表大部分 CRUD 操作，更有强大的条件构造器，满足各类使用需求
   - **支持 Lambda 形式调用**：通过 Lambda 表达式，方便的编写各类查询条件，无需再担心字段写错
   - **支持主键自动生成**：支持多达 4 种主键策略（内含分布式唯一 ID 生成器 - Sequence），可自由配置，完美解决主键问题
   - **支持 ActiveRecord 模式**：支持 ActiveRecord 形式调用，实体类只需继承 Model 类即可进行强大的 CRUD 操作
   - **支持自定义全局通用操作**：支持全局通用方法注入（ Write once, use anywhere ）
   - **内置代码生成器**：采用代码或者 Maven 插件可快速生成 Mapper 、 Model 、 Service 、 Controller 层代码，支持模板引擎，更有超多自定义配置等您来使用
   - **内置分页插件**：基于 MyBatis 物理分页，开发者无需关心具体操作，配置好插件之后，写分页等同于普通 List 查询
   - **分页插件支持多种数据库**：支持 MySQL、MariaDB、Oracle、DB2、H2、HSQL、SQLite、Postgre、SQLServer 等多种数据库
   - **内置性能分析插件**：可输出 Sql 语句以及其执行时间，建议开发测试时启用该功能，能快速揪出慢查询
   - **内置全局拦截插件**：提供全表 delete 、 update 操作智能分析阻断，也可自定义拦截规则，预防误操作

3. 框架结构

   ![image-20210802104511689](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210802104511689.png)

##### MyBatis-Plus CRUD Mapper 接口使用

yml 配置文件

```yaml
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql:///mybatis?characterEncoding=utf8
    username: root
    password: admin

# 在控制台显示 SQL
logging:
  level:
    com:
      bh:
        mybatis:
        dao: debug
```

dao 接口 继承 BaseMapper<实体类> mp 封装好的 方法接口

有特殊需求 自己追加 方法

主启动类增加 MapperScan 扫描注解

pojo 对象 需要 指定 映射表 主键字段

```java
@TableName(value = "t_user")// 匹配表名和实体类名不一致
public class User implements Serializable {
    @TableId(type = IdType.AUTO)// 主键和主属性对应匹配 必须配置 mybatis是auto_increment，mp是 雪花算法
    private Integer uid;
    // @TableField // 非主键和非主属性匹配
    private String uname;
    private String upwd;
}
```

接近全 ORM 的实现

插入操作

```java
// 插入操作 -- 获取id
@Test
void contextLoads() {

    User user = new User(0,"炳汉","0022");

    userDao.insert(user);

    System.out.println(user.getUid());
}
```

删除操作

```java
// 删除操作 -- 一组 id 删除
@Test
void delBtIds() {
    // 方式一
    // userDao.deleteBatchIds(Arrays.asList(20,19));
    // 方式二
    List<Integer> list = new ArrayList<>();
    list.add(19);
    list.add(20);
    userDao.deleteBatchIds(list);
}
```

修改操作

```java
	// 修改操作 -- 主键修改
   @Test
   void updateByPrimaryKey() {

       User user = new User(18,"卧龙先生","5577");

       userDao.updateById(user);
}
```

查询操作

```java
// 查询操作 -- 三大类 实体类对象封装、 统计个数、 Map 对象封装 （以及带分页，封装条件有Map 和 queryWrapper）

// 一组 id 查询
@Test
void selectByIds() {
    List<User> users = userDao.selectBatchIds(Arrays.asList(16, 17, 18));
    System.out.println(users);
}

// 使用 Map 封装查询条件 -- 精确查询 不支持模糊查询 =
@Test
void selectByMap() {
    Map<String,Object> map = new HashMap<>();
    map.put("uname","张三");
    List<User> users = userDao.selectByMap(map);
    System.out.println(users);
}

// 使用 queryWrapper 封装查询条件 -- 查询一个结果
@Test
void selectByWrapper() {
    QueryWrapper<User> wrapper = new QueryWrapper<>();
    wrapper.eq("uid",18);
    wrapper.eq("upwd","5577");
    User user = userDao.selectOne(wrapper);
    System.out.println(user);
}

// 查询 -- 统计个数\
@Test
void selectByCount() {
    QueryWrapper<User> wrapper = new QueryWrapper<>();
    // 模糊查询
    // 全模糊
    // wrapper.like("uname","张");
    // 右模糊
    wrapper.likeRight("uname","张");
    // 或者
    wrapper.or();
    wrapper.likeRight("uname","孙");
    // 方法连用也支持 方法 返回值就是本类对象
    // wrapper.likeRight("uname","张").or().likeRight("uname","孙");
    Integer integer = userDao.selectCount(wrapper);
    System.out.println(integer);
}


// 查询操作 -- 排序
@Test
void order() {
    QueryWrapper<User> wrapper = new QueryWrapper<>();
    wrapper.orderByDesc("upwd","uname");
    List<User> users = userDao.selectList(wrapper);
    System.out.println(users);
}

// 向 Map 集合保存数据
@Test
void selectToMap() {
    List<Map<String, Object>> maps = userDao.selectMaps(null);
    System.out.println(maps);
}
```

> 不管是向Map还是对象封装数据对于前端来说格式都是通过字符串传输转回的对象，无本质区别，使用都是xx.xx

Page 分页 

分页操作

```java
// 分页测试
@Test
void Page() {
    Page<User> page = new Page<>(1,5);// 页码 和 页容量
    Page<User> userPage = userDao.selectPage(page, null);
    System.out.println("当前页号"+userPage.getCurrent());
    System.out.println("总页数"+userPage.getPages());
    System.out.println("总行数"+userPage.getTotal());
    System.out.println("当前页数据:");
    List<User> records = userPage.getRecords();
    System.out.println(records);
}
```

因为没有配置文件了 所以需要配置类

需要配置分页拦截器 MybatisPlusInterceptor

放到哪个位置都可以 只要IoC容器管理即可

```java
// 分页拦截器
@Bean
public MybatisPlusInterceptor mybatisPlusInterceptor() {
    MybatisPlusInterceptor interceptor = new MybatisPlusInterceptor();
    interceptor.addInnerInterceptor(new PaginationInnerInterceptor(DbType.MYSQL));
    return interceptor;
}
```

Object 接收数据

```java
// 采用 Object 接收数据
@Test
void selectToObject() {
    QueryWrapper<User> wrapper = new QueryWrapper<>();
    wrapper.select("uname");
    List<Object> objects = userDao.selectObjs(wrapper);
    System.out.println(objects);
}
```

需要自定义的 增加即可 不影响

##### MyBatis-Plus CRUD Service 接口使用

业务层 也通过继承封装好的实现了 npmp

接口：UserService

extends IService

```java
public interface UserService extends IService<User> {
}
```

接口实现类：UserServiceImpl

extends ServiceImpl<userDao,User>

implement UserService

```java
@Service
public class UserServiceImpl extends ServiceImpl<UserDao, User> implements UserService {
}
```

只针对单表 多表需要自己根据业务添加

测试

```java
@SpringBootTest
public class ServiceTest {

    @Autowired
    private UserService userService;

    // 测试增加操作
    @Test
    public void testSave() {
        userService.save(new User(0,"天使","983"));
    }

    // 测试修改操作
    @Test
    public void testUpdate() {
        userService.updateById(new User(21,"白天使","987"));
    }

    // 测试查询操作
    @Test
    public void testSelect() {
        QueryWrapper<User> wrapper = new QueryWrapper<>();
        wrapper.likeRight("uname","张");
        List<User> list = userService.list(wrapper);
        System.out.println(list);
    }
}
```

##### 后续

> ES -- Elasticsearch 
> 全文检索 实现搜索功能（数据不一定从数据库搜）（数据库 模糊查询 效率慢）
> Vue -- Es6

项目

##### MyBatis-Plus 代码生成器使用

+ pom 依赖

  ```xml
  <dependencies>
      <dependency>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-starter-web</artifactId>
      </dependency>
  
      <dependency>
          <groupId>mysql</groupId>
          <artifactId>mysql-connector-java</artifactId>
          <scope>runtime</scope>
      </dependency>
      <dependency>
          <groupId>org.projectlombok</groupId>
          <artifactId>lombok</artifactId>
          <optional>true</optional>
      </dependency>
      <!-- mp 的 pom 包米豆的 若只需要mp 则mybatis的启动器可以不用-->
      <dependency>
          <groupId>com.baomidou</groupId>
          <artifactId>mybatis-plus-boot-starter</artifactId>
          <version>3.4.2</version>
      </dependency>
      <!-- 代码生成器包-->
      <dependency>
          <groupId>com.baomidou</groupId>
          <artifactId>mybatis-plus-generator</artifactId>
          <version>3.2.0</version>
      </dependency>
      <!-- 基于 Java 的模板引擎 velocity 可以实现彻底的前后端-->
      <dependency>
          <groupId>org.apache.velocity</groupId>
          <artifactId>velocity-engine-core</artifactId>
          <version>2.3</version>
      </dependency>
      <dependency>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-starter-test</artifactId>
          <scope>test</scope>
      </dependency>
  </dependencies>
  ```

+ 全局配置 项目路径、作者

  getSwagger 相当于浏览器请求测试（相当于Postman）

+ 数据源配置

+ 指定生成位置的路径

+ 生成内容的策略配置

```java
@Test
void contextLoads() {
    // 代码生成
    // 全局配置 项目路径、作者

    // 代码生成器
    AutoGenerator mpg = new AutoGenerator();

    // 全局配置
    GlobalConfig gc = new GlobalConfig();
    // 项目路径
    String projectPath = System.getProperty("user.dir");
    // 生成内容全局路径
    gc.setOutputDir(projectPath+"/src/main/java");
    gc.setAuthor("lbh");// 设置作者
    gc.setOpen(false);// 生成后是否打开资源管理器
    gc.setFileOverride(false);// 重新生成文件是否覆盖
    // 业务层接口名称 格式为去掉下划线改为大写
    gc.setServiceName("%sService");
    // gc.setSwagger2(true); 实体属性 Swagger2 注解

    mpg.setGlobalConfig(gc);

    //数据源配置
    DataSourceConfig dsc = new DataSourceConfig();
    dsc.setUrl("jdbc:mysql://localhost:3306/mybatis?useUnicode=true&useSSL=false&characterEncoding=utf8");
    // dsc.setSchemaName("public");
    dsc.setDriverName("com.mysql.cj.jdbc.Driver");
    dsc.setUsername("root");
    dsc.setPassword("admin");
    //指定哪种数据库
    dsc.setDbType(DbType.MYSQL);

    mpg.setDataSource(dsc);

    //指定生成内容的路径
    // 包配置
    PackageConfig pc = new PackageConfig();
    pc.setModuleName(null);
    pc.setParent("com.bh");
    pc.setController("controller");
    pc.setEntity("pojo");
    pc.setService("service");
    pc.setMapper("dao");
    mpg.setPackageInfo(pc);

    //生成内容的根据
    //策略配置
    StrategyConfig strategy = new StrategyConfig();
    strategy.setInclude("t_user","t_user_base");//对那一张表生成代码
    strategy.setNaming(NamingStrategy.underline_to_camel);//数据库表映射到实体的命名策略 下换线2驼峰
    strategy.setTablePrefix(pc.getModuleName() + "_"); //生成实体时去掉表前缀

    strategy.setColumnNaming(NamingStrategy.underline_to_camel);//数据库表字段映射到实体的命名策略
    strategy.setEntityLombokModel(true); // lombok 模型 @Accessors(chain = true) setter链式操作

    strategy.setRestControllerStyle(true); //restful api风格控制器
    strategy.setControllerMappingHyphenStyle(true); //url中驼峰转连字符

    mpg.setStrategy(strategy);

    //执行生成操作
    mpg.execute();
}
```



**注意： 不要用 SpringBootTest 整合测试 单独运行**

### Day22

#### 回顾

1. SpringBoot 和 Dubbo 整合 -- <font color="red">重点</font>

   + Zookeeper 客户端端口：2181、服务端口： 2888:3888 ；20880 远程调用功能端口

   + 服务提供方（可以配置端口）

     1）相关 jar 包

     2）相关配置

     3）相关的对外提供功能

   + 服务消费方（无需提供端口）

     1）相关 jar 包

     2）相关配置

     3）远程调用功能

2. Mybatis-Plus

   + 封装持久层

     BaseMapper

   + 封装业务层

     IService、ServiceImpl

   + 代码生成器

#### 内容

##### ES -- ElasticSearch 介绍

- 全文检索工具、搜索平台、提供搜索功能的服务系统，致力于解决海量数据的搜索功能，当数据量比较多的时候，如果使用 MySQL 等数据库进行模糊查询，那么数据库的索引会失效，不能达到快速查找的目的，那么采用 es 等搜索平台解决此问题，另外当使用模糊查询的时候，不能够有效的实现分词的效果（把短语、句子、文章进行分词汇），因此此问题的解决采用 ES 等搜索平台实现解决（Solr 等）

+ 内存存储的缺陷 容量不及硬盘

  MySQL like 模糊查找 

  增加索引 快速查找 

  什么情况下才能用到索引 

  在使用他们作为条件的时候 where 关键词后面 用到他们作条件 提高查询速度 性能明显提高 提速10倍 几十倍 

  只要用到了 与所以无关的字段 就没有索引的功能 

  设置了模糊查询、函数、空值等 索引失去作用

  1.有or必全有索引;
  2.复合索引未用左列字段;
  3.like以%开头;
  4.需要类型转换;
  5.where中索引列有运算;
  6.where中索引列使用了函数;
  7.如果mysql觉得全表扫描更快时（数据少）;

  如：uname like '%翼德大能%' 

  有其中分别几个就能查出来的 分词查询

  正则表达式 实现也较为复杂

  京东搜索：先分词、在搜索、取并集、有排序

+ **倒排索引** -- Solr 和 ES 都是

  首先从句子或者段落或者文章中分词，然后根据这些词汇创建索引（一个词汇对应一个或者多个地址），最后通过词汇作为搜索关键字，在搜索时先通过索引找到地址，再通过地址找到内容。 

  本身有一个分词数据库进行分词查找

  ![image-20210803100947091](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210803100947091.png)

  solr 和 es 都是基于 Lucene 的 原生态的东西 jdbc 和 mybatis 的关系 

  分布式、高扩展、高实时的搜索与数据分析引擎

  基于Restful web 接口

  ES 是 Java语言开发的

  Apache 许可条款下开源

+ 应用场景

  搜索：海量数据的查询

  日志数据分析

  实时数据分析

##### ES -- ElasticSearch 安装

官方地址：https://www.elastic.co/cn/

+ 配置 五项 config/elasticsearch.yml

  集群名字 ：cluster.name

  节点名字：node.name

  ip 配置：network.host 类似Redis 改0.0.0.0

  默认端口 9200：http.port

  集群主节点：cluster.initial_master_nodes：["",...]

把当前虚拟机的内存调大 否则ES 启动不起来

+ 系统配置 文件 三个

  修改文件数大小

  etc/security/limits.conf

  ```shell
  #===最大可创建文件数太小=======
  vim /etc/security/limits.conf 
  
  # 在文件末尾中增加下面内容
  bh soft nofile 65536
  bh hard nofile 65536
  ```

  etc/security/limits.d/20-nproc.conf

  ```shell
  #===========
  vim /etc/security/limits.d/20-nproc.conf
  # 在文件末尾中增加下面内容
  bh soft nofile 65536
  bh hard nofile 65536
  *  hard    nproc     4096
  # 注：* 代表Linux所有用户名称
  ```

  修改内存大小

  etc/sysctl.conf

  ```shell
  #===最大虚拟内存太小=======
  vim /etc/sysctl.conf
  # 在文件中增加下面内容
  vm.max_map_count=655360
  # 重新加载，输入下面命令：
  sysctl -p
  ```

  执行 `sysctl -p`

+ ES 默认不支持 root 用户启动

  创建用户

  `useradd bh`

  `passwd bh`

  授权、改变es文件的所有者 bh 组 bh

  `chown -R bh:bh elasticsearch/`

  切换登录用户

  `su bh`

  `cd bin/`

  前端启动方式

  `./elasticsearch`

  显示started 启动成功

  ![image-20210803205628497](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210803205628497.png)

+ 端口关闭 或者防火墙释放

  因为启动会退步出来，另起一个远程连接

  释放 9200端口 或者关闭防火墙

  `systemctl stop firewalld.service`

  浏览器进去 ip:9200 返回信息 安装启动成功

  <img src="https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210803210648032.png" alt="image-20210803210648032"  />

##### ES -- ElasticSearch 客户端

Postman 或者 Kibana

官网：https://www.elastic.co/cn/kibana/

和 ES 版本配套 

+ 配置 conf/kibana.yml

  server.port：5601

  server.host："0.0.0.0"

  server.name："kibana-bh"

  elasticsearch.hosts：["http://localhost:9200"]（因为安装同一个虚拟机，所以localhost 即可）

  elasticsearch.requestTimeout：99999（milliseconds）

+ 启动 kibana

  `cd bin`

  由于不建议 root 用户启动 所以需要加上参数

  `./kibana --allow-root`

  释放 防火墙 5601

  `systemctl stop firewalld.service`

  浏览器进进入 ip"5601 进入即可

  显示连接成功

  Dev Tools -- Console 可以搜索数据

  DashBoard 仪表盘

  **ES 是 http 协议**

  一套增删改查操作

##### ES 数据结构的介绍

索引、映射、文档

+ 索引（index）

  存储数据的地方，相当于（MySQL）数据库

+ 映射（mapping）

  定义了每个字段的类型、字段所使用的分词器等，相当于表

+ 文档（document）

  最小数据单元，常以 json 格式显示，相当于一行数据

+ 倒排索引

  由文档中所有**不重复词的列表构成**，对于其中每个词，对应一个文档 id 列表

+ 类型（type）

  一种type就像**一类表**。如用户表、角色等。

  在 ES7.x 默认为 type_doc（5.x 多种 type，6.x 一种 type 不确定）

##### ES 操作索引

使用 Postman 或者 Kibana（Dev Tools）

四种 Restful 请求方式

+ 创建索引：PUT 请求方式 

  Postman：ip:9200/索引名称（创建数据库的操作）

  Kibana：put 索引名称

+ 查询索引：GET 请求方式

  Postman：ip:9200/索引名称（查询数据库的操作）

  查询回来的 JSON 串 

  **ip:9200/_all 查询所有索引** 自带 2827 行索引

  Kibana：get 索引名称 get _all

+ 删除索引：DELETE 请求方式 

  Postman：ip:9200/索引名称（删除数据库的操作） 返回 acknowledge：true

##### ES 数据类型

+ 简单数据类型

  字符串：text 会分词 keyword 不会分词

  数值：byte、short、integer、long、float、double

  布尔：boolean

  范围类型：integer_range,float_range,double_range,date_range

  日期：date

+ 复杂数据类型

  数组：[] nested

  对象：{} object

##### ES 操作映射

+ 直接建立映射/表中添加新的字段

  **PUT 请求** ip:9200/索引名称/_mapping

  put 索引+json串

  Kibana 中好写 json 串

  Postman 中 Body-raw-JSON

  ```json
  {
      "properties":{
          "name":{
             "type":"text"
          },
          "sex":{
              "type":"integer"
          }
      }
  }
  ```

+ 建索引时候建立映射

  **PUT 请求** ip:9200/索引名称

  ```json
  {
      "mappings":{
          "properties":{
              "name":{
                 "type":"text"
              },
              "sex":{
                  "type":"integer"
              }
          }
  	}
  }
  ```

**注意：映射类似表结构，但是表明没有，整体类型是_doc**

##### ES 操作文档

+ 增加/修改

  **POST 方式（PUT也行）** ip:9200/索引/_doc/编号

  不带编号的是增加 只能 POST

  Postman 字符串转日期操作不了

  ```json
  {
      "name":"张飞",
      "sex":1,
      "bir":"",
      "address":"昌平"
  }
  ```

  返回 20x都可以 4xxx客户端 5xx 服务器端

+ 查询

  GET 方式 

  查指定：ip:9200/索引/_doc/编号 

  查所有：ip:9200/索引/_search

+ 删除

  DELETE 方式

  ip:9200/索引/_doc/编号 

##### ES 的分词器 -- IK 分词器安装 中文分词

ik 分词器、结巴分词器、中科院NLPIR、ansj、哈工大LTP、庖丁解牛

词库 新版本 

需要maven ES 内置了 JDK

+ JDK 环境变量配置 

  /etc/profile 设置 JAVA_HOME

  ```shell
  vim /etc/profile
  # 在profile文件末尾添加
  #java environment
  export JAVA_HOME=/usr/app/software/es/elasticsearch-7.4.0/jdk
  export PATH=$PATH:${JAVA_HOME}/bin
  
  # 保存退出后，重新加载profile
  source /etc/profile
  ```

+ maven 环境变量配置 

  下载 maven 安装包

  安装 wget

  `yum install wget`

  `wget https://archive.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz`

  解压 maven 安装包

  `tar -zvxf apache-maven-3.6.0-bin.tar.gz -C software/`

  /etc/profile 设置 MAVEN_HOME

  ```shell
  export MAVEN_HOME=/usr/app/software/maven
  export PATH=${MAVEN_HOME}/bin:${PATH} 
  # 保存退出后，重新加载profile
  source /etc/profile
  ```

  建造本地仓库 resp

  `mkdir resp`

  配置 settings.xml

  localRepository

  mirror

  profile

+ 安装 ik 分词器

  `wget https://github.com/medcl/elasticsearch-analysis-ik/archive/v7.10.0.zip`

  `yum install zip unzip`

  ` uzip elasticsearch-analysis-ik-7.10.0.zip `

  **打包之前 分词器版本兼容 es7.4.0 需要修改 pom.xml es 版本**

  打包：`mvn package`

  jar 包移动：移动到 es/plugins下 建立目录 analysis-ik

  `mkdir analysis-ik`

  `cp -R /usr/app/elasticsearch-analysis-ik-7.10.0/target/releases/elasticsearch-analysis-ik-7.10.0.zip ./`

  解压 拷贝完成的压缩包

  `unzip elasticsearch-analysis-ik-7.10.0.zip`

  拷贝词典 复制打包之前解压的 ik/config/.. 到 elasticssearch/config

  ctrl+c 停掉进程 在重启 es 与 kibana

##### ES 的分词器 -- IK 分词器使用

和哪个字段添加分词 添加分词策略 

当插入该字段数据 自动分词的同时 建立索引

**查询的时候 用 带了分词的字段作条件 倒排索引**

GET 请求：ip:9200/_analyze

细粒度分词 ik_max_word

```json
{
    "analyzer":"ik_max_word",
    "text":"乒乓球明年总冠军"
}
```

粗粒度分词 ik_smart 

分的没那么细

GET 请求查询：ip:9200/索引名/_doc/编号  

增加分词策略  

增加字段 analyzer

PUT 请求：ip:9200/索引名/_mapping

```json
{
    "properties":{
        "address":{
           "type":"text",
            "analyzer":"ik_max_word"
        },
    }
}
```

POST 请求 添加数据

ip:9200/索引名/_doc/编号

```json
{
    "name":"张飞",
    "sex":1,
    "address":"北京昌平桃源村"
}
```

使用分词查询

GET 请求 查询分词效果

ip:9200/索引名/_search

不带分词 term

```json
{
    "query":{
        "term":{
            "address":{
                "value":"北京桃源"
            }
        }
    }
}
```

带分词 match 先分词 在查询 取并集

```json
{
    "query":{
        "match":{
            "address":"北京桃源"   
        }
    }
}
```

##### SpringBoot 整合 ElasticSearch

引入 es 的坐标 三个 高级客户端 普通客户端 和 驱动

```xml
<!--引入es的坐标-->
<dependency>
    <groupId>org.elasticsearch.client</groupId>
    <artifactId>elasticsearch-rest-high-level-client</artifactId>
    <version>7.10.0</version>
</dependency>
<dependency>
    <groupId>org.elasticsearch.client</groupId>
    <artifactId>elasticsearch-rest-client</artifactId>
    <version>7.10.0</version>
</dependency>
<dependency>
    <groupId>org.elasticsearch</groupId>
    <artifactId>elasticsearch</artifactId>
    <version>7.10.0</version>
</dependency>
```

配置文件

```yaml
# 自定义的没提示
elasticsearch:
  hostname: 192.168.126.20
  port: 9200
```



> Http-client 爬虫...

初始化客户端

 配置文件 注入 Bean

```java
@Configuration
@ConfigurationProperties(prefix="elasticsearch")
public class ElasticSearchConfig {

    private String host;
    private int port;

    @Bean
    public RestHighLevelClient client(){
        return new RestHighLevelClient(RestClient.builder(
                new HttpHost(host,port,"http")
        ));
    }  
    
    public String getHost() {
        return host;
    }

    public void setHost(String host) {
        this.host = host;
    }

    public int getPort() {
        return port;
    }

    public void setPort(int port) {
        this.port = port;
    }
}
```

### Day23

#### 回顾

1. Es -- 搜索引擎、平台 检索工具 支持快速查找 减轻MySQL 压力 基于原生 Lucence 齐名的 Solr、支持分布式的项目架构、搜索原理倒排索引、启动需要切换用户  
2. 分词器：ik、结巴、NLPIR、庖丁解牛
3. 测试：Postman（url 都可测试）、Kibana（测试 ES 和消息中间件）、Swagger（需要在表现层加接口）
4. 索引、映射、文档操作

#### 内容

##### ES 的 Java 操作

1. 索引操作

   ```java
   // 创建索引的操作
   @Test
   public void testCreateIndex() throws Exception {
   
       // 通过高级客户端获取一般客户端
       IndicesClient indices = restHighLevelClient.indices();
   
       // 创建添加索引的请求
       CreateIndexRequest request = new CreateIndexRequest("persons4");
   
   
       // 发送请求 -- 获取响应
       CreateIndexResponse response = indices.create(request, RequestOptions.DEFAULT);
   
       // 根据响应、知道请求是否成功
       System.out.println(response);
   }
   
   // 查询索引
   @Test
   public void queryIndex() throws IOException {
       //1:使用client获取操作索引的对象
       IndicesClient indices = restHighLevelClient.indices();
       //2:获得对象，执行具体的操作
       //2.1 创建获取索引的请求对象，设置索引名称
       GetIndexRequest request = new GetIndexRequest("persons4");
       //2.2 执行查询，获得返回值
       GetIndexResponse response = indices.get(request, RequestOptions.DEFAULT);
       //3：获取结果,遍历
       Map<String, Settings> settings = response.getSettings();
       System.out.println(settings);
   }
   
   // 删除索引
   @Test
   public void testDeleteIndex() throws Exception{
       //1:使用client获取操作索引的对象
       IndicesClient indices = restHighLevelClient.indices();
       //2:获得对象，执行具体的操作
       //2.1 创建获取索引的请求对象，设置索引名称
       DeleteIndexRequest request = new DeleteIndexRequest("persons4");
       //2.2 执行查询，获得返回值
       AcknowledgedResponse response = indices.delete(request, RequestOptions.DEFAULT);
       System.out.println(response.isAcknowledged());
   }
   
   // 判断索引是否存在
   @Test
   public void testIndexExists() throws Exception{
       IndicesClient indices = restHighLevelClient.indices();
       GetIndexRequest request = new GetIndexRequest("persons2");
       boolean response = indices.exists(request,RequestOptions.DEFAULT);
       System.out.println(response);
   }
   ```

2. 映射操作

   ```java
   //创建索引同时创建映射
       @Test
       public void testCreateIndexAndMapping()throws Exception{
           //通过高级客户端获取一般客户端
           IndicesClient indices = highLevelClient.indices();
   
           //创建添加索引的请求
           CreateIndexRequest request = new CreateIndexRequest("persons4");
           String mapping = "{\n" +
                   "    \"properties\": {\n" +
                   "      \"name\":{\n" +
                   "        \"type\":\"text\"\n" +
                   "      },\n" +
                   "      \"age\":{\n" +
                   "        \"type\": \"integer\"\n" +
                   "      }\n" +
                   "    }\n" +
                   "  }";
           request.mapping(mapping, XContentType.JSON);
           //发送请求 -- 获取响应
           CreateIndexResponse response = indices.create(request, RequestOptions.DEFAULT);
   
           //根据响应、知道请求是否成功
           System.out.println(response);
       }
   ```

3. 文档操作

   ```java
   //添加文档数据
   @Test
   public void testAddDoc()throws Exception{
       //准备数据 -- Map
       Map map = new HashMap();
       map.put("name","张飞");
       map.put("age",30);
   
       //请求 -- 添加数据的请求
       IndexRequest request = new IndexRequest("persons4").id("1").source(map);
   
       //执行添加 -- 获取响应
       IndexResponse response = highLevelClient.index(request, RequestOptions.DEFAULT);
   
       //打印响应
       System.out.println(response);
   }
   ```

   ```java
   //添加文档数据 -- 采用实体类对象封装数据 -- id存在则实现修改操作   id不存在则实现添加操作
   @Test
   public void testAddDoc2()throws Exception{
       //准备数据 -- Map
       Person person = new Person(2,"关云长",32);
       //转json串
       String json = JSON.toJSONString(person);
   
       //请求 -- 添加数据的请求
       IndexRequest request = new IndexRequest("persons4").id(person.getPid()+"").source(json,XContentType.JSON);
   
       //执行添加 -- 获取响应
       IndexResponse response = highLevelClient.index(request, RequestOptions.DEFAULT);
   
       //打印响应
       System.out.println(response);
   }
   ```

   ```java
   //根据id查询数据
   @Test
   public void testGetDocId() throws Exception{
       GetRequest request = new GetRequest("persons4").id("2");
       GetResponse response = highLevelClient.get(request, RequestOptions.DEFAULT);
       //Map<String, Object> map = response.getSourceAsMap();
       //System.out.println(map);
   
       String json = response.getSourceAsString();
       System.out.println(json);
       //json串转回对象
       Person person = JSON.parseObject(json, Person.class);
       System.out.println(person);
   }
   ```

   ```java
   //删除数据-- 根据id
   @Test
   public void testDeleteId()throws Exception{
       DeleteRequest request = new DeleteRequest("persons4").id("1");
       DeleteResponse response = highLevelClient.delete(request, RequestOptions.DEFAULT);
       System.out.println(response);
   }
   ```

4. 高级操作

   ES 的 批量操作 bulk

   ```java
   //批量操作
   @Test
   public void testBulk()throws Exception{
       //批量操作请求
       BulkRequest bulkRequest = new BulkRequest();
   
       //批量操作添加到请求中
       DeleteRequest deleteRequest = new DeleteRequest("persons4").id("3");
       bulkRequest.add(deleteRequest);
   
   
       Map map = new HashMap();
       map.put("name","刘备");
       map.put("age",33);
       IndexRequest indexRequest = new IndexRequest("persons4").id("2").source(map);
       bulkRequest.add(indexRequest);
   
       Map map2 = new HashMap();
       map2.put("name","曹操");
       map2.put("age",35);
       UpdateRequest updateRequest = new UpdateRequest("persons4","1").doc(map2);
       bulkRequest.add(updateRequest);
   
       //指定批量操作 -- 获取响应
       BulkResponse response = highLevelClient.bulk(bulkRequest,RequestOptions.DEFAULT);
   
       //打印响应
       System.out.println(response);
   }
   ```

   

##### 数据批量添加 ES

列表 ES 详情 MySQL

商家录入商品 保存两个地方 MySQL 和 ES

增加 MP 依赖

字段保存 JSON 串，Map<String,Object>接收，但先排除

```java
@TableField("spec")
private String specStr;
//排除 不能和表中同名字段对应
@TableField(exist = false)
private Map<String,Object>spec;

​```java
//从数据库查询数据 -- 把数据库中数据批量导入到es中
@Test
public void  testAll()throws Exception{
    List<Item> list = itemDao.selectList(null);
    BulkRequest request = new BulkRequest();
    for(Item item : list){
        System.out.println(item);

        String specStr = item.getSpecStr();
        Map<String,Object> map = JSON.parseObject(specStr, Map.class);
        item.setSpec(map);

        String json = JSON.toJSONString(item);
        IndexRequest indexRequest = new IndexRequest("items").id(item.getId() + "").source(json, XContentType.JSON);
        request.add(indexRequest);
    }
    BulkResponse response = highLevelClient.bulk(request, RequestOptions.DEFAULT);
    System.out.println(response);
}
```

##### ES 的高级操作

```java
//查询所有 -- 默认显示前10条
@Test
public void testSelectAll()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //追加条件 -- 没有条件
    MatchAllQueryBuilder query = QueryBuilders.matchAllQuery();//没有条件

    //把条件添加到构造器
    searchSourceBuilder.query(query);
    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }
}
```

```java
//带条件查询 -- 显示前20条 -- 不分词
@Test
public void testSelectConTerm()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //追加条件 
    TermQueryBuilder query = QueryBuilders.termQuery("title", "三星小米");

    //把条件添加到构造器
    searchSourceBuilder.query(query);
    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }
}
```

```java
//带条件查询 -- 显示前20条 -- 分词
@Test
public void testSelectConMatch()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //追加条件 -- 没有条件
    MatchQueryBuilder query = QueryBuilders.matchQuery("title", "三星小米");

    //把条件添加到构造器
    searchSourceBuilder.query(query);
    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }
}
```

```java
//带条件查询 -- 显示前20条 -- 实现模糊查询
@Test
public void testSelectLike()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //模糊
    WildcardQueryBuilder query = QueryBuilders.wildcardQuery("title", "小*");

    //把条件添加到构造器
    searchSourceBuilder.query(query);
    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }
}
```

```java
//带条件查询 -- 显示前20条 -- 实现范围查询
@Test
public void testSelectBetween()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //范围查询
    RangeQueryBuilder query = QueryBuilders.rangeQuery("price");
    query.gte(1);
    query.lte(100);

    //把条件添加到构造器
    searchSourceBuilder.query(query);
    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);
    searchSourceBuilder.sort("price", SortOrder.DESC);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }
}
```

```java
//带条件查询 -- 显示前20条 -- 多条件查询 -- 好几个字段同时查询
@Test
public void testSelectManyCon()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //多条件
    QueryStringQueryBuilder query = QueryBuilders.queryStringQuery("华为小米").field("categoryName").field("brandName").field("title");

    //把条件添加到构造器
    searchSourceBuilder.query(query);
    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);
    searchSourceBuilder.sort("price", SortOrder.DESC);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }
}
```

```java
//带条件查询 -- 显示前20条 -- 指标聚合 -- 查询最大值
@Test
public void testSelectMax()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //指标聚合 -- 取价格最大值
    MatchQueryBuilder query = QueryBuilders.matchQuery("title", "手机");
    //把条件添加到构造器
    searchSourceBuilder.query(query);

    //max_price=299000.00
    MaxAggregationBuilder price = AggregationBuilders.max("max_price").field("price");
    searchSourceBuilder.aggregation(price);

    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);
    searchSourceBuilder.sort("price", SortOrder.DESC);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }

    //获取价格最大值
    Aggregations aggregations = response.getAggregations();
    Map<String, Aggregation> stringAggregationMap = aggregations.asMap();
    Max max = (Max) stringAggregationMap.get("max_price");
    double value1 = max.getValue();
    System.out.println(value1);
}
```

```java
//带条件查询 -- 显示前20条 -- 桶聚合 -- 分组 -- 使用品牌分组brandName
@Test
public void testSelectGroup()throws Exception{
    //搜索请求
    SearchRequest searchRequest = new SearchRequest("items");

    //条件构造器
    SearchSourceBuilder searchSourceBuilder = new SearchSourceBuilder();

    //指标聚合 -- 取价格最大值
    MatchQueryBuilder query = QueryBuilders.matchQuery("title", "手机");
    //把条件添加到构造器
    searchSourceBuilder.query(query);

    //使用品牌分组
    TermsAggregationBuilder field = AggregationBuilders.terms("goods_brands").field("brandName");
    searchSourceBuilder.aggregation(field);

    //下标从0开始计数，实现显示
    //searchSourceBuilder.from(10);//816448
    //改变页容量
    searchSourceBuilder.size(20);
    searchSourceBuilder.sort("price", SortOrder.DESC);

    //把构造器添加到搜索请求
    searchRequest.source(searchSourceBuilder);

    //执行查找操作
    SearchResponse response = highLevelClient.search(searchRequest, RequestOptions.DEFAULT);

    //获取默认查到的10条数据
    SearchHits hits = response.getHits();
    //总行数
    TotalHits totalHits = hits.getTotalHits();
    long value = totalHits.value;
    System.out.println("总行数："+value);
    SearchHit[] hits1 = hits.getHits();
    for(SearchHit hit : hits1){
        String source = hit.getSourceAsString();
        System.out.println(source);
    }

    //获取分组数据
    Aggregations aggregations = response.getAggregations();
    Map<String, Aggregation> stringAggregationMap = aggregations.asMap();
    Terms terms = (Terms) stringAggregationMap.get("goods_brands");
    List<? extends Terms.Bucket> buckets = terms.getBuckets();
    for(Terms.Bucket bucket : buckets){
        Object key = bucket.getKey();
        System.out.println(key);
    }
}
```

##### ECMAScript6 语法 

1. let 变量 局部作用域

   1）var 声明的变量没有局部作用域 

   2）同一个作用域 var 可以声明多次，let 只能声明一次

   3）var 会变量提升 let 不存在

2. const 常量

3. 解构赋值

   ```javascript
   // 定义多个变量 类似数组
   let [x,y,z] = [1,2,3];
   console.log(x+"-"+y+"-"+z);
   // 定义对象变量 JSON 对象
   let user = {'name':'张飞','sex':1}; 
   console.log(user.name);
   console.log(user.sex);
   // 这样可省略 user 直接输出 name、sex
   let {name,sex} = user;
   console.log(name);
   console.log(sex);
   // JSON 字符串
   let str = "{'name':'张飞','sex':1}"
   // var parse = JSON.parse(str) JSON类型转换
   // 查类型
   console.log(typeof(user));
   ```

4. 模板字符串

   定义字符串使用反引号、多行、变量、表达式

   ```javascript
   let str = `abc \n bcd ${name}`;
   ```

5. 声明对象简写 -- 简化对象变量的定义方案

   ```javascript
   let uname = '关羽';
   let usex = 1;
   let user2 = {uname,usex};
   console.log(user2.uname);
   console.log(user2.usex);
   ```

6. 对象变量的复制、合并

   ```javascript
   let user3 = {...user};
   console.log(user3.name);
   console.log(user3.sex);
   let user4 = {...user,...user2};
   console.log(user4.name);
   console.log(user4.sex);
   console.log(user4.uname);
   console.log(user4.usex);
   ```

7. 简化函数定义

   ```javascript
   // 传统写法
   function add(a,b) {
       return a+b;
   }
   let o = add(10,20)
   console.log(o);
   // 函数定义 -- 类中
   User1 = {
       add:function(a,b) {
       	return a+b;     
       }
   }
   let p = User1.add(21,31);
   // 函数定义 -- 类中
   User2 = {
       odd(a,b) {
           return a-b;
       }
   }
   let q = User2.odd(30,20);
   console.log(q);
   ```

8. 带默认值的函数、可变形参、箭头函数

   ```javascript
   // 定义一个 普通函数 -- 没有在类中 -- 设置默认值
   function method1(a=10,b=11) {
       console.log(a);
       console.log(b);
   }
   method1(10,20);
   // 定义一个 普通函数 -- 没有在类中 -- 定义可变形参 类似JavaSE 的可变形参 类型没Java严格
   function method2(...params) {
       console.log(params);
   }
   console.log(1,'liubei',new Date());
   // 箭头函数
   var method = () => {
       console.log('箭头函数')
   }
   ```

9. 总结 三个知识点

   变量操作：一般变量、对象变量

   类中的函数、方法

   一般的函数、箭头函数、可变形参、带默认值

Vue -- 尤与溪

### Day24

#### 回顾

Es -- Elasticsearch

索引、映射、高级

ES6 -- ECMAScript6

#### 内容

##### Vue 介绍

![img](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/clip_image002.jpg)

1. 由来
2. 如何使用
3. 高级部分 -- 异步操作

渐进式框架、只关注视图层、自底向上增量开发的设计

目标 简单 API 实现响应的数据绑定和组合的视图组件

2013 年底开始开发 目前3.0版本 https://cn.vuejs.org/

Angular/React/Vue 框架

+ 最大程度上解放了 DOM 操作
+ 单页 web 项目开发（一个页面集成多种功能）iframe 内联框架、frameset 框架集
+ 传统网站开发

##### Vue 的核心概念

1. 解耦视图与数据，前后端分离（异步操作）（后端测试Postman、Swagger；前端测试 读 json数据 文件）

2. M-V-VM 模型 关注模型和视图

   M：即 Model，模型（数据），包括数据和一些基本操作

   V：即 View，视图，页面渲染结果

   VM：即 View-Model，模型和视图间的双向操作

3. 双向数据绑定

1）MVVM 之前

DOM 操作 Model 渲染 View 

DOM 获取 View 同步 Model

2）MVVM 之后

DOM 操作封装

M V 双向绑定

把开发人员从繁琐的 DOM 操作中解放，把关注点放在如何操作 Model 上

##### Vue 入门

1. 下载安装

   1）CDN 在线引入

   ```html
   <!-- 开发环境版本，包含了用帮助的命令行警告 -->
   <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
   或
   <!-- 生产环境版本，优化了尺寸和速度 -->
   <script src="https://cdn.jsdelivr.net/npm/vue"></script>
   
   ```

   2）下载后离线使用

   开发版本: https://vuejs.org/js/vue.js

   生产版本: https://vuejs.org/js/vue.min.js

   `<script src="js/vue.min.js"></script>`

2. 入门案例

   + 使用CDN或离线引入方式将vue.js文件引入到html页面中
   + 在html页面中创建挂载点
   + 在script标签中创建Vue实例，并定义数据。

   ```html
   // 显示数据
   <div id="app">
       <!-- 显示数据-->
       {{msg}}
   </div>
   // 定义对象 -- vue
   var app = new Vue({
   // 对谁进行 vue 修饰 -- 用 vue 操作的目标是谁 -- 块 --
   // 通过 id 选择器找到元素,元素中的内容可以被vue识别或操作
   el: '#app',
   // 通过 data 属性在内部设置键值对
   data:{
   msg:'vue入门案例'
   }
   
   });
   ```

##### Vue 常用指令

(1) v-text和v-html

类似innerText text()和innerHTML  html()，给页面中带文本节点元素绑定数据

+ v-text：更新标签中的内容，不会识别内容中的标签
+  v-html：更新标签中的内容/标签，会解析内容包含的标签

(2) v-if和v-show

根据表达式的boolean值进行判断是否渲染该元素（与元素的显示和隐藏有关）boolean值为true表示显示，false表示隐藏。

+ v-if:隐藏元素的时候，直接删除dom元素

+ v-show:隐藏元素内容，通过display属性控制，dom元素依然存在
+ 需要频繁切换用v-show，不需要频繁切换用v-if

(3) v-on

作用：使用 v-on 指令绑定 DOM 事件，并在事件被触发时执行一些 JavaScript 代码。

语法：

+ v-on:事件名 = "methods中的方法名";
+ v-on的简写方法: @事件名 = "methods中的方法名";

(4) v-for

作用：列表渲染,当遇到相似的标签结构时,就用v-for去渲染

格式：

+ (item,index) in 数组或集合 

  参数item:数组中的每个元素 

  参数index:数组中元素的下标

+ (value, key, index) in 对象 

  参数index:对象中每对key-value的索引 从0开始 

  参数key:键 

  参数value:值

(5) v-bind

作用: 可以给标签上的任何属性绑定值

格式：v-bind:属性="值"

简写格式：:属性="值"

属性值一部分进行替换的格式：:属性="'常量值' + vue对象data中的数据"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue入门</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>
<div id="app">
    <!-- 显示数据-->
    {{msg}}
    <hr>
    <p v-text="msg"></p>
    <p v-html="msg"></p>
    <p v-if="flag">是否显示--由flag值决定，如果值为true则显示，如果值为false则不显示</p>
    <p v-show="flag">是否显示--由flag值决定，如果值为true则显示，如果值为false则不显示</p>
    <hr>
    <button v-on:click="method1()">提交</button><br>
    <button @click="method1()">提交</button><br>
    <hr>
    <p v-for="(num,index) in list">{{num}} -- {{index}}</p>
    <hr>
    <p>{{user.name}} -- {{user.sex}} -- {{user.age}}</p>
    <hr>
    <p v-for="(ue,inde) in users">{{ue.name}} -- {{ue.sex}} -- {{ue.age}}</p>
    <hr>
    <!-- 字符串拼接-->
    <p v-text="'我们是'+str"></p>
    <p v-text="`我们是${str}`"></p>
    <hr>
    <a v-bind:href="url">百度</a>
    <a :href="url">百度</a>
    <hr>
    <img v-bind:src="imgUrl">
    <img :src="imgUrl">

</div>
<div></div>
<script type="text/javascript">
    // 定义对象 -- vue
    var app = new Vue({
        // 对谁进行 vue 修饰 -- 用 vue 操作的目标是谁 -- 块 --
        // 通过 id 选择器找到元素,元素中的内容可以被vue识别或操作
        el: '#app',
        // 通过 data 属性在内部设置键值对
        data:{
            msg:'<h3>vue入门案例</h3>',
            flag:false,
            list:[10,11,12,13,14],
            user:{'name':'张飞','sex':0,'age':30},
            users:[{'name':'张飞1','sex':0,'age':30},{'name':'张飞2','sex':0,'age':30},{'name':'张飞3','sex':0,'age':30}],
            str:'社会主义好青年',
            url:'http://www.baidu.com',
            imgUrl:'imgs/1.jpg'
        },
        methods:{
            // 可以定义多个函数
            method1() {
                alert('123')
            },
            method2() {

            }
        }

    });
</script>
</body>
</html>
```

(6) v-model

1. 作用：表单元素的绑定
2. 特点：双向数据绑定

​     （1）vue对象中的数据发生变化可以更新到界面

​     （2）通过界面可以更改vue对象中数据

​     （3）v-model 会忽略所有表单元素的 value、 checked 、 selected 特性的初始值而总是将 Vue 实例的数据作为数据来源。应该在data选项中声明初始值。

3. v-model修饰符：

   .lazy

   在默认情况下， v-model 在 input 事件中同步输入框的值与数据，但你可以添加一个修饰符 lazy ，从而转变为在 change 事件中同步

   .number

   如果想自动将用户的输入值转为 Number 类型（如果原值的转换结果为 NaN 则返回原值），可以添加一个修饰符 number 给 v-model 来处理输入值

   .trim

   如果要自动过滤用户输入的首尾空格，可以添加 trim 修饰符到 v-model 上过滤输入

(7) computed

在插值表达式中使用js表达式是非常方便的，而且也经常被用到。

但是如果表达式的内容很长，就会显得不够优雅，而且后期维护起来也不方便

计算属性可以简化表达式

例如：

1. 将一个字符串反转后显示

2. 获取系统当前时间并拼接指定的格式输出

(8) watch

watch可以让我们监控一个值的变化。从而做出相应的反应。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>测试双向绑定</title>
        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<body>
<div id="app">
    <input type="text" v-model="uname">{{uname}}
    <input v-model="user.upwd">{{user.upwd}}
    <input v-model="user.uage">{{user.uage}}
    <hr>
    {{today}}
    <hr>
    {{strlen}}
    <hr>
    <input v-model="usex">
    <select v-model="ucity">
        <option value="1">海淀</option>
        <option value="2">昌平</option>
        <option value="3">延庆</option>
        <option value="4">房山</option>
    </select>
</div>
<script type="text/javascript">
    var app = new Vue({
       el:'#app',
       data:{
           uname:'',
           user:{
               upwd:'',
               uage:''
           },
           usex: '',
           ucity:''
       },
        computed:{
           today() {
               return new Date();
           },
            strlen() {
               return 'abcdef'.substr(0,3);
            }
        },
        watch:{
           usex(newVal,oldVal) {
               console.log(newVal + "---" + oldVal);
           },
           ucity(newVal,oldVal) {
               console.log(newVal + "---" + oldVal);
           }

        }
    });
</script>
</body>
</html>
```

##### Vue 生命周期

1. 概念

   Vue实例从创建到销毁的过程，就是生命周期。

   详细来说也就是从开始创建、初始化数据、编译模板、挂载Dom、**渲染→更新→渲染**、卸载等一系列过程。

   同时在这个过程中也会运行一些叫做**生命周期钩子的函数**，这给了用户在不同阶段添加自己的代码的机会。

   在vue整个的生命周期中提供了**八个钩子函数**：

   beforeCreate 创建前

   created 创建结束 

   beforeMount挂载前

   mounted挂载结束

   beforeUpdate修改前

   updated修改后

   beforeDestroy销毁前

   destroyed销毁后

2. 图示

   ![image-20210805141607994](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210805141607994.png)

   ![image-20210805141644482](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210805141644482.png)

##### console.log支持的格式标志有

alert 显示信息不全 

**console** 显示信息全

| 占位符 | 描述        |
| ------ | ----------- |
| %s     | 字符串      |
| %d/%i  | 整数        |
| %f     | 浮点数      |
| %o/%O  | object 对象 |
| %c     | css 样式    |

##### Vue 高级部分 -- 异步操作

Vue 的 Ajax

**一般使用 axios**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>测试异步操作</title>
    <script type="text/javascript" src="js/vue.js"></script>
    <script type="text/javascript" src="js/axios.min.js"></script>
</head>
<body>
<div id="app">
    {{flag}}
    <hr>
    <button @click="method1()">发出get异步请求的按钮1</button>
    <hr>
    <button @click="method2()">发出post异步请求的按钮2</button>
    <hr>
    <button @click="method3()">发出post异步请求的按钮3</button>
    <hr>
    <button @click="method4()">发出post异步请求的按钮4</button>

    <span v-text="user.id"></span>
    <span v-text="user.name"></span>
    <span v-text="user.sex"></span>
    <hr>
    <p v-for="ue in userList">{{ue.id}} -- {{ue.name}} -- {{ue.sex}}</p>

</div>
<script type="text/javascript">
    var app = new Vue({
        el:"#app",
        data:{
            flag:'',
            user:{},
            userList:[]
        },
        methods:{
            method1() {
                //alert(123)
                axios.get('user/first?id=1001&name=zhangfei&sex=1').then((response) =>{
                    console.log(response);
                    console.log(response.data.flag);
                    console.log(response.status);
                    this.flag = response.data.flag;
                });
            },
            method2() {
                axios.post('user/sec',{'id':1002,'name':'关羽','sex':1}).then((res) => {
                    console.log(res);
                    this.user = res.data
                });
            },
            method3() {
                axios.post('user/third').then((res) => {
                    console.log(res);
                this.userList = res.data
            });
            },
            method4() {
                axios({
                    url:'user/forth',
                    method:'post', // get、put、delete 都可以
                    data:{
                        'id':1004,
                        'name':'caocao',
                        'sex':1
                    },
                    responseType:'json'
                }).then((res) => {
                    console.log(res.data);
                });// .catah(error => {}) 处理异常
            }
        }

    });
</script>
</body>
</html>
```

ELementui 介绍、下周项目

### Day25

#### 回顾

Vue

#### 内容

##### ELementUI 介绍

官网：https://element.eleme.cn

ElementUI，一套为开发者、设计师和产品经理准备的基于 Vue 2.0 的桌面端组件库。

是**基于Vue的一个UI框架**，该框架基于Vue开发了很多相关组件，方便我们快速开发页面。

**饿了么前端团队**基于Vue进行开发并开源，提供了**封装好的组件**。内部封装了HTML+CSS+JS。

##### ElementUI 下载安装

+ 方式一：CDN引入

  CDN在线引入时需要**锁定版本**

  ```html
  <!-- 引入样式 -->
  <link rel="stylesheet" 
  href="https://unpkg.com/browse/element-ui@2.15.1/lib/theme-chalk/index.css">
  <!-- 引入组件库 -->
  <script src="https://unpkg.com/element-ui@2.15.1/lib/index.js"></script>
  ```

+ 方式二：下载本地

  ```html
  <!-- 引入 elementUI 样式 -->
  <link rel="stylesheet" href="./element-ui-2.13.0/lib/theme-chalk/index.css">
  <!-- 引入elementUI 组件库 -->
  <script src="./element-ui-2.13.0/lib/index.js"></script>
  ```

##### ElementUI 常用组件

###### 消息弹窗 Message

说明：用于主动操作后的反馈提示

常用参数介绍：

| message   | 消息文字                              | string/VNode | -                          | -     |
| --------- | ------------------------------------- | ------------ | -------------------------- | ----- |
| type      | 主题                                  | string       | success/warning/info/error | info  |
| showClose | 是否显示关闭按钮                      | boolean      | -                          | false |
| center    | 文字是否居中                          | boolean      | -                          | false |
| duration  | 显示时间，毫秒，设置为0则不会自动关闭 | number       | -                          | 3000  |

```html
// 消息弹框
this.$message({
	message: '恭喜你，这是一条成功消息',
	type: 'success'
});
this.$message.error('错了哦，这是一条错误消息');

// 确定取消弹框
this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
	confirmButtonText: '确定',
	cancelButtonText: '取消',
	type: 'warning'
}).then(() => {
	this.$message({
	type: 'success',
	message: '删除成功!'
});
}).catch(() => {
	this.$message({
	type: 'info',
	message: '已取消删除'
});
});

// 带输入的弹框 
this.$prompt('请输入邮箱', '提示', {
    confirmButtonText: '确定',
    cancelButtonText: '取消',
    inputPattern: /[\w!#$%&'*+/=?^_`{|}~-]+(?:\.[\w!#$%&'*+/=?^_`{|}~-]+)*@(?:[\w](?:[\w-]*[\w])?\.)+[\w](?:[\w-]*[\w])?/,
    inputErrorMessage: '邮箱格式不正确'
}).then(({ value }) => {
    this.$message({
    type: 'success',
    message: '你的邮箱是: ' + value
});
}).catch(() => {
this.$message({
    type: 'info',
    message: '取消输入'
});
});
```

###### 表格 Table

说明：用于展示多条结构类似的数据，可对数据进行排序、筛选、对比或其他自定义操作。

1）el-table元素中

data表示绑定的表格数据

stripe 隔行变色

border 带边框的表格

2）el-table-column中

prop属性来对应对象中的属性值

label属性来定义表格的列名

width属性来定义列宽

type设置 selection 则显示多选

@selection-change="handleSelectionChange"

3）修改删除事件参数：

scope.$index当前行索引 

scope.row当前行对象

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>elementui 的入门案例</title>
    <!-- 引入样式 -->
    <link rel="stylesheet" type="text/css"
          href="css/elementui.css">
    <!-- 引入组件库 -->
    <script type="text/javascript" src="js/vue.js"></script>
    <script type="text/javascript" src="js/elementui.js"></script>
</head>
<body>
<div id="app">

    <el-table
            :data="list"
            stripe
            style="width: 100%">
        <el-table-column
                prop="id"
                label="编号"
                width="180">
        </el-table-column>
        <el-table-column
                prop="name"
                label="姓名"
                width="180">
        </el-table-column>
        <el-table-column
                prop="sex"
                label="性别">
        </el-table-column>
    </el-table>
</div>

<script type="text/javascript">
    var app = new Vue({
        el:'#app',
        data:{
            list:[{'id':1001,'name':'张飞1','sex':1},{'id':1002,'name':'张飞2','sex':2},{'id':1003,'name':'张飞3','sex':3}]
        },
        methods:{
        }
    });
</script>
</body>
</html>
```

###### 分页 Pagination

说明：当页面数据量过多时，使用分页分解数据。

属性说明：

layout 表示需要显示的内容，用逗号分隔，布局元素会依次显示

total表示总条目数

prev 上一页

next 下一页

pager表示页码列表

jumper表示跳页元素

sizes 用于设置每页显示的页码数量

prev-text 替代图标显示的上一页文字

next-text替代图标显示的下一页文字

事件说明：

size-change页码大小发生改变时触发

current-change当前页变动时候触发

```html
<el-pagination layout="prev,pager,next" :total="total"></el-pagination>
```

###### 对话框 Dialog

说明：在保留当前页面状态的情况下，告知用户并承载相关操作。

参数说明：

title 对话框标题

width 对话框宽度

fullscreen 是否全屏显示，默认false

:visible.sync="dialogVisible" 是否显示对话框，根据boolean值显示

事件说明：

:before-close="handleClose" 关闭对话框之前触发

```html
<div id="app">
    <el-button @click="showDialog()">打开对话框</el-button>
    <el-dialog title="测试" :visible.sync="dialogFormVisiable">
        <div>对话框内容。。。</div>
    </el-dialog>
</div>

<script type="text/javascript">
    var app = new Vue({
        el:'#app',
        data:{
            dialogFormVisiable:false
        },
        methods:{
            showDialog() {
                this.dialogFormVisiable = true;
            }
        }
    });
</script>
```

###### Upload 上传

```html
<div id="app">
    <el-upload
            class="avatar-uploader"
            action="upload"
            name="filename"
            :show-file-list="false"
            :on-success="handleAvatarSuccess"
            :before-upload="beforeAvatarUpload">
        <img v-if="flag" :src="imageUrl" class="avatar">
        <i v-else class="el-icon-plus avatar-uploader-icon"></i>
    </el-upload>
</div>
<script type="text/javascript">
    var app = new Vue({
        el:'#app',
        data:{
            imageUrl:'',
            flag:false
        },
        methods:{
            handleAvatarSuccess(res, filename) {
                console.log(res)
                this.flag = true;
                this.imageUrl = res.url;
            },
            beforeAvatarUpload(filename) {
                const isJPG = filename.type === 'image/jpeg';
                const isLt2M = filename.size / 1024 / 1024 < 2;

                if (!isJPG) {
                    this.$message.error('上传头像图片只能是 JPG 格式!');
                }
                if (!isLt2M) {
                    this.$message.error('上传头像图片大小不能超过 2MB!');
                }
                return isJPG && isLt2M;
            }
        }
    });
</script>
```

###### 表单 Form

###### Icon 图标

###### 按钮 Button

等等详情 https://element.eleme.io/#/zh-CN/component/upload

##### 医疗管家 项目 概述

###### 项目背景

随着疫情的逐步结束，国民对于个人的身体健康越来越重视，对健康认识不断提高，对健康的需求也在不断增加，健康检查作为防患于未然的主动预防措施在人们思想中已有很深的认识，医疗管家管理系统 致力于建立一座健康管理机构和会员之间的灵活沟通的桥梁，医疗管家管理平台利用计算机对体检工作流程、结果收集、结论汇总、健康评估、会员管理等多种信息进行数字化管理，给会员提供定制化的健康体检方案，并持续追踪会员的健康状态，为会员的健康提供终身的服务。

###### 原型展示

静态原型

###### 技术架构

![img](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/1.png)

###### 功能架构

![image-20210806160443946](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210806160443946.png)

###### 软件开发流程

架构师 灵魂 CTO

项目经理（项目有明确的客户）实干 工作任务分配 开小会 

产品经理（项目没有明确的客户）**专门与客户沟通** 懂一定技术

+ 需求分析

  ```html
  1.相关系统分析员向用户初步了解需求，然后用相关的工具软件列出要开发的系统的大功能模块，每个大功能模块有哪些小功能模块，对于有些需求比较明确相关的界面时，在这一步里面可以初步定义好少量的界面。
  2.系统分析员深入了解和分析需求，根据自己的经验和需求用WORD或相关的工具再做出一份文档系统的功能需求文档。这次的文档会清楚列出系统大致的大功能模块，大功能模块有哪些小功能模块，并且还列出相关的界面和界面功能。
  3.系统分析员向用户再次确认需求。
  ```

+ 概要设计

  ```html
  首先，开发者需要对软件系统进行概要设计，即系统设计。概要设计需要对软件系统的设计进行考虑，包括系统的基本处理流程、系统的组织结构、模块划分、功能分配、接口设计、运行设计、数据结构设计和出错处理设计等，为软件的详细设计提供基础
  ```

+ 详细设计

  ```html
  在概要设计的基础上，开发者需要进行软件系统的详细设计。在详细设计中，描述实现具体模块所涉及到的主要算法、数据结构、类的层次结构及调用关系，需要说明软件系统各个层次中的每一个程序(每个模块或子程序)的设计考虑，以便进行编码和测试。应当保证软件的需求完全分配给整个软件。详细设计应当足够详细，能够根据详细设计报告进行编码
  ```

+ 编码

  ```html
  在软件编码阶段，开发者根据《软件系统详细设计报告》中对数据结构、算法分析和模块实现等方面的设计要求，开始具体的编写程序工作，分别实现各模块的功能，从而实现对目标系统的功能、性能、接口、界面等方面的要求。在规范化的研发流程中，编码工作在整个项目流程里最多不会超过1/2，通常在1/3的时间，所谓磨刀不误砍柴功，设计过程完成的好，编码效率就会极大提高，编码时不同模块之间的进度协调和协作是最需要小心的，也许一个小模块的问题就可能影响了整体进度，让很多程序员因此被迫停下工作等待，这种问题在很多研发过程中都出现过。编码时的相互沟通和应急的解决手段都是相当重要的，对于程序员而言，bug永远存在，你必须永远面对这个问题
  ```

+ 测试

  ```html
  测试编写好的系统。交给用户使用，用户使用后一个一个的确认每个功能。软件测试有很多种：按照测试执行方，可以分为内部测试和外部测试；按照测试范围，可以分为模块测试和整体联调；按照测试条件，可以分为正常操作情况测试和异常情况测试；按照测试的输入范围，可以分为全覆盖测试和抽样测试。以上都很好理解，不再解释。总之，测试同样是项目研发中一个相当重要的步骤，对于一个大型软件，3个月到1年的外部测试都是正常的，因为永远都会有不可预料的问题存在。完成测试后，完成验收并完成最后的一些帮助文档，整体项目才算告一段落，当然日后少不了升级，修补等等工作，只要不是想通过一锤子买卖骗钱，就要不停的跟踪软件的运营状况并持续修补升级，直到这个软件被彻底淘汰为止
  ```

+ 交付

  ```html
  在软件测试证明软件达到要求后，软件开发者应向用户提交开发的目标安装程序、数据库的数据字典、《用户安装手册》、《用户使用指南》、需求报告、设计报告、测试报告等双方合同约定的产物。
  《用户安装手册》应详细介绍安装软件对运行环境的要求、安装软件的定义和内容、在客户端、服务器端及中间件的具体安装步骤、安装后的系统配置。
  《用户使用指南》应包括软件各项功能的使用流程、操作步骤、相应业务介绍、特殊提示和注意事项等方面的内容，在需要时还应举例说明。
  ```

+ 验收

  ```html
  用户验收。
  ```

+ 维护

  ```html
  根据用户需求的变化或环境的变化，对应用程序进行全部或部分的修改
  ```

##### 医疗管家 项目 环境搭建

###### 项目结构

```html
本项目采用maven分模块开发方式，即对整个项目拆分为几个maven工程,父工程提供统一的依赖规范，其余的每个maven 工程存放特定类型的代码,具体如下：
```

![image-20210806163109145](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210806163109145.png)

各模块职责定位： 

```html
offcnpe_parent：父工程，打包方式为pom，统一锁定依赖的版本，同时聚合其他子模块 便于统一执行maven命令

offcnpe_pojo 数据模型，打包方式为jar，存放项目中使用到表对应的数据模型

offcnpe_interface：打包方式为jar，存放服务接口。 

offcnpe_provider：Dubbo服务模块，打包方式为war，存放服务实现类、Dao接 口、Mapper映射文件等，作为服务提供方，需要部署到tomcat运行。

offcnpe_controller：小U健康管理后台，打包方式为war，作为Dubbo服务消费方，存放 Controller、HTML页面、js、css、spring配置文件等，需要部署到tomcat运行

offcnpe_mobile：移动端前台，打包方式为war，作为Dubbo服务消费方，存放 Controller、HTML页面、js、css、spring配置文件等，需要部署到tomcat运行.

offcnpe_util: 工具模块，打包方式为jar，存放项目中使用到的一些工具类、返回结果和常量类
```

### Day26

#### 回顾

1. MyBatis-Plus

   + 是什么
   + 作用

2. ElasticSearch

   + 是什么
   + 原理
   + 底层实现
   + 数据结构

3. es6

   

4. vue

5. elementui

#### 内容

##### 医疗管家项目 工程搭建

###### 1：bhpe_parent 父工程，打包方式为pom，用于统一管理依赖版本

通过前面的项目功能架构图可以知道本项目分为小U健康管理后台和小U健康前台(移动端)

建立父项目 注意类型为 Maven POMa

![image-20210809202409267](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210809202409267.png)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <packaging>pom</packaging>
    <modules>
        <module>bhpe_pojo</module>
        <module>bhpe_util</module>
        <module>bhpe_interface</module>
        <module>bhpe_provider</module>
    </modules>
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.4.9</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>com.bh</groupId>
    <artifactId>bhpe_parent</artifactId>
    <version>1.0</version>
    <name>bhpe_parent</name>
    <description>Demo project for Spring Boot</description>
    <properties>
        <java.version>1.8</java.version>
        <!-- jar 包版本统一管理-->
        <!--mybatis plus-->
        <baomidou-mybatisplus.version>3.4.2</baomidou-mybatisplus.version>
        <!--mybatis plus 生成-->
        <baomidou-mybatisplus-generator.version>3.4.1</baomidou-mybatisplus-generator.version>
        <!--dubbo-->
        <alibaba-dubbo.version>2.7.6</alibaba-dubbo.version>
        <!--poi-->
        <apache-poi.version>3.17</apache-poi.version>
        <!--lombok-->
        <lombok.version>1.18.20</lombok.version>
        <!-- msql驱动-->
        <mysql-connector.version>5.1.49</mysql-connector.version>
    </properties>
    <!-- 项目 jar 包统一管理，不同子项目继承的 jar 包不同-->
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-data-redis</artifactId>
            </dependency>
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-web</artifactId>
            </dependency>

            <dependency>
                <groupId>mysql</groupId>
                <artifactId>mysql-connector-java</artifactId>
                <scope>runtime</scope>
                <version>${mysql-connector.version}</version>
            </dependency>
            <dependency>
                <groupId>org.projectlombok</groupId>
                <artifactId>lombok</artifactId>
                <optional>true</optional>
                <version>${lombok.version}</version>
            </dependency>

            <!-- mybatisplus-->
            <dependency>
                <groupId>com.baomidou</groupId>
                <artifactId>mybatis-plus-boot-starter</artifactId>
                <version>${baomidou-mybatisplus.version}</version>
            </dependency>

            <!-- mybatisplus 代码生成器包 -->
            <dependency>
                <groupId>com.baomidou</groupId>
                <artifactId>mybatis-plus-generator</artifactId>
                <version>${baomidou-mybatisplus-generator.version}</version>
            </dependency>

            <!-- dubbo-->
            <dependency>
                <groupId>org.apache.dubbo</groupId>
                <artifactId>dubbo-spring-boot-starter</artifactId>
                <version>${alibaba-dubbo.version}</version>
            </dependency>

            <!-- poi:实现 excel 操作的-->
            <dependency>
                <groupId>org.apache.poi</groupId>
                <artifactId>poi-ooxml</artifactId>
                <version>${apache-poi.version}</version>
            </dependency>

            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-test</artifactId>
                <scope>test</scope>

            </dependency>
        </dependencies>
    </dependencyManagement>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <configuration>
                    <excludes>
                        <exclude>
                            <groupId>org.projectlombok</groupId>
                            <artifactId>lombok</artifactId>
                        </exclude>
                    </excludes>
                </configuration>
            </plugin>
        </plugins>
    </build>

</project>
```

问题

![cts-210809141720375](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/cts-210809141720375.png)

###### 2: bhpe_pojo 数据模型，打包方式为jar，存放项目中使用到表对应的数据模型

建立 maven 项目 设置父项目和父模块都是

```xml
    <dependencies>
        <!-- boot-starter启动器-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter</artifactId>
        </dependency>
        <!-- web-starter-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
            <version>2.4.9</version>
        </dependency>
        <!-- lombok-->
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <optional>true</optional>
        </dependency>
        <!-- mybatisplus-->
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>mybatis-plus-boot-starter</artifactId>
        </dependency>
        <!-- poi-->
        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-ooxml</artifactId>
        </dependency>
    </dependencies>
```

###### 3：offcnpe_util: 工具模块，打包方式为jar，存放项目中使用到的一些工具类、返回结果和常量类

```xml
<dependencies>
    <!-- pojo-->
    <dependency>
        <groupId>com.bh</groupId>
        <artifactId>bhpe_pojo</artifactId>
        <version>1.0</version>
    </dependency>
    <dependency>
        <groupId>com.baomidou</groupId>
        <artifactId>mybatis-plus-generator</artifactId>
    </dependency>
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
    </dependency>
    <dependency>
        <groupId>org.apache.velocity</groupId>
        <artifactId>velocity-engine-core</artifactId>
        <version>2.0</version>
    </dependency>
</dependencies>
```

###### 4: offcnpe_interface：打包方式为jar，存放服务接口

```xml
<dependencies>
    <!-- util-->
    <dependency>
        <artifactId>bhpe_util</artifactId>
        <groupId>com.bh</groupId>
        <version>1.0</version>
    </dependency>
</dependencies>
```

###### 5: offcnpe_provider Dubbo服务模块

(1)pom.xml文件内容

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <version>2.4.9</version>
    </dependency>
    <!-- dubbo的依赖 -->
    <dependency>
        <groupId>org.apache.dubbo</groupId>
        <artifactId>dubbo-spring-boot-starter</artifactId>
    </dependency>
    <!-- zookeeper 客户端-->
    <dependency>
        <groupId>org.apache.curator</groupId>
        <artifactId>curator-recipes</artifactId>
        <version>2.8.0</version>
    </dependency>
    <!-- interface-->
    <dependency>
        <groupId>com.bh</groupId>
        <artifactId>bhpe_interface</artifactId>
        <version>1.0</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-redis</artifactId>
        <version>2.4.9</version>
    </dependency>
    <dependency>
        <groupId>com.alibaba</groupId>
        <artifactId>druid</artifactId>
        <version>1.1.20</version>
    </dependency>
</dependencies>
```

(2)application.yml配置文件内容

```yaml
#端口  访问路径
server:
  port: 9001
  servlet:
    context-path: /

#spring应用名称
spring:
  application:
    name: bhpe_provider
    #数据源配置
  datasource:
    driver-class-name: com.mysql.jdbc.Driver
    url: jdbc:mysql:///offcnpe?characterEncoding=utf8
    username: root
    password: damin
    type: com.alibaba.druid.pool.DruidDataSource

 #mybatis-plus
mybatis-plus:
  configuration:
    #开启驼峰标识
    map-underscore-to-camel-case: true
    #控制台显示sql语句
    log-impl: org.apache.ibatis.logging.stdout.StdOutImpl
  global-config:
    #逻辑删除
    db-config:
      logic-not-delete-value: 1
      logic-delete-value: 0
      #加载我们的xml文件
  mapper-locations: classpath:/mappers/*.xml
  type-aliases-package: com.bh.pojo
#dubbo端口和名称
dubbo:
  protocol:
    name: bhpe_provider
    port: 20880
  registry:
    address: zookeeper://192.168.159.128:2181
    timeout: 10000
  #扫描我们service注解
  scan:
    base-packages: com.bh.service
```

(3)构建springboot启动类

```java
package com.bh;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
@SpringBootApplication
public class PeControllerApplication {
    public static void main(String[] args) {
        SpringApplication.run(PeControllerApplication.class,args);
    }
}
```

###### 6：offcnpe_controller健康管家管理后台工程

(1)pom.xml文件内容

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <version>2.4.9</version>
    </dependency>
    <!-- dubbo的依赖 -->
    <dependency>
        <groupId>org.apache.dubbo</groupId>
        <artifactId>dubbo-spring-boot-starter</artifactId>
    </dependency>
    <!-- zookeeper 客户端-->
    <dependency>
        <groupId>org.apache.curator</groupId>
        <artifactId>curator-recipes</artifactId>
        <version>2.8.0</version>
    </dependency>
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
    </dependency>
    <!-- interface-->
    <dependency>
        <groupId>com.bh</groupId>
        <artifactId>bhpe_interface</artifactId>
        <version>1.0</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-redis</artifactId>
        <version>2.4.9</version>
    </dependency>
    <dependency>
        <groupId>com.alibaba</groupId>
        <artifactId>druid</artifactId>
        <version>1.1.20</version>
    </dependency>
    <dependency>
        <groupId>com.alibaba</groupId>
        <artifactId>fastjson</artifactId>
        <version>1.2.68</version>
    </dependency>
</dependencies>

```

(2)application.yml文件内容

```
server:
  servlet:
    context-path: /
  port: 8001

spring:
  application:
    name: bhpe_controller
  datasource:
    driver-class-name: com.mysql.jdbc.Driver
    url: jdbc:mysql:///offcnpe?characterEncoding=utf8
    username: root
    password: root
    type: com.alibaba.druid.pool.DruidDataSource
  devtools:
    restart:
      enabled: true
      additional-paths: src/main/java
  redis:
    host: 192.168.159.128
    port: 6379
    password: 123456
dubbo:
  protocol:
    name: bhpe_controller
    port: 20881
  registry:
    address: zookeeper://192.168.159.128:2181
    timeout: 10000
```

(3)构建springboot启动类

```java
package com.bh;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
@SpringBootApplication
public class PeControllerApplication {
    public static void main(String[] args) {
        SpringApplication.run(PeControllerApplication.class,args);
    }
}
```

###### 7：offcnpe_mobile移动端前台工程

(1)pom文件内容

```xml
<dependencies>
    <!--web 启动器-->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
        <version>2.4.9</version>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-redis</artifactId>
        <version>2.4.9</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <scope>runtime</scope>
        <optional>true</optional>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <version>2.4.9</version>
    </dependency>
    <!-- dubbo的依赖 -->
    <dependency>
        <groupId>org.apache.dubbo</groupId>
        <artifactId>dubbo-spring-boot-starter</artifactId>
    </dependency>
    <!-- zookeeper 客户端-->
    <dependency>
        <groupId>org.apache.curator</groupId>
        <artifactId>curator-recipes</artifactId>
        <version>2.8.0</version>
    </dependency>
    <!-- interface-->
    <dependency>
        <groupId>com.bh</groupId>
        <artifactId>bhpe_interface</artifactId>
        <version>1.0</version>
    </dependency>
    <dependency>
        <groupId>com.alibaba</groupId>
        <artifactId>druid</artifactId>
        <version>1.1.20</version>
    </dependency>
    <dependency>
        <groupId>com.alibaba</groupId>
        <artifactId>fastjson</artifactId>
        <version>1.2.68</version>
    </dependency>
</dependencies>
```

(2)application.yml文件内容

```yaml
server:
  servlet:
    context-path: /
  port: 8002

spring:
  application:
    name: bhpe_mobile
  datasource:
    driver-class-name: com.mysql.jdbc.Driver
    url: jdbc:mysql:///offcnpe?characterEncoding=uft8
    username: root
    password: admin
    type: com.alibaba.druid.pool.DruidDataSource
dubbo:
  protocol:
    name: bhpe_mobile
    port: 20881
  registry:
    address: zookeeper://192.168.159.128:2181
    timeout: 10000
```

View -- Tools Window 没有 Services 选项          打开.idea workspace.xml  加入

```xml
<component name="RunDashboard">
    <option name="configurationTypes">
        <set>
            <option value="SpringBootApplicationConfigurationType" />
        </set>
    </option>
    <option name="ruleStates">
        <list>
            <RuleState>
                <option name="name" value="ConfigurationTypeDashboardGroupingRule" />
            </RuleState>
            <RuleState>
                <option name="name" value="StatusDashboardGroupingRule" />
            </RuleState>
        </list>
    </option>
</component>
```

权限验证框架 ：一般5张表即可 本项目7张 表的增删改查操作

##### 医疗管家项目 预约管理-检查项管理

###### (一)需求分析

```
本章节完成的功能开发是预约管理功能，包括检查项管理、检查组管理、体检套餐管理、预约设置等。预约管理属于系统的基础功能，主要就是管理一些体检的基础数据。
```

###### (二)基础环境搭建 

1: 创建数据库offcnpe

```
create  database offcnpe
```

2: 导入数据表

```
sqlyong 中执行sql脚本
```

3: 导入项目所需工具资源 

(1)返回消息常量类MessageConstant，放到offcnpe_util工程中

```java
项目开发过程中一般会提供一些公共资源，供多个模块或者系统来使用。 本章节我们导入的公共资源有
/**
 * 消息常量
 */
public class MessageConstant {
    public static final String DELETE_CHECKITEM_FAIL = "删除检查项失败";
    public static final String DELETE_CHECKITEM_SUCCESS = "删除检查项成功";
    public static final String ADD_CHECKITEM_SUCCESS = "新增检查项成功";
    public static final String ADD_CHECKITEM_FAIL = "新增检查项失败";
    public static final String EDIT_CHECKITEM_FAIL = "编辑检查项失败";
    public static final String EDIT_CHECKITEM_SUCCESS = "编辑检查项成功";
    public static final String QUERY_CHECKITEM_SUCCESS = "查询检查项成功";
    public static final String QUERY_CHECKITEM_FAIL = "查询检查项失败";
    public static final String UPLOAD_SUCCESS = "上传成功";
    public static final String ADD_CHECKGROUP_FAIL = "新增检查组失败";
    public static final String ADD_CHECKGROUP_SUCCESS = "新增检查组成功";
    public static final String DELETE_CHECKGROUP_FAIL = "删除检查组失败";
    public static final String DELETE_CHECKGROUP_SUCCESS = "删除检查组成功";
    public static final String QUERY_CHECKGROUP_SUCCESS = "查询检查组成功";
    public static final String QUERY_CHECKGROUP_FAIL = "查询检查组失败";
    public static final String EDIT_CHECKGROUP_FAIL = "编辑检查组失败";
    public static final String EDIT_CHECKGROUP_SUCCESS = "编辑检查组成功";
    public static final String PIC_UPLOAD_SUCCESS = "图片上传成功";
    public static final String PIC_UPLOAD_FAIL = "图片上传失败";
    public static final String ADD_SETMEAL_FAIL = "新增套餐失败";
    public static final String ADD_SETMEAL_SUCCESS = "新增套餐成功";
    public static final String IMPORT_ORDERSETTING_FAIL = "批量导入预约设置数据失败";
    public static final String IMPORT_ORDERSETTING_SUCCESS = "批量导入预约设置数据成功";
    public static final String GET_ORDERSETTING_SUCCESS = "获取预约设置数据成功";
    public static final String GET_ORDERSETTING_FAIL = "获取预约设置数据失败";
    public static final String ORDERSETTING_SUCCESS = "预约设置成功";
    public static final String ORDERSETTING_FAIL = "预约设置失败";
    public static final String ADD_MEMBER_FAIL = "新增会员失败";
    public static final String ADD_MEMBER_SUCCESS = "新增会员成功";
    public static final String DELETE_MEMBER_FAIL = "删除会员失败";
    public static final String DELETE_MEMBER_SUCCESS = "删除会员成功";
    public static final String EDIT_MEMBER_FAIL = "编辑会员失败";
    public static final String EDIT_MEMBER_SUCCESS = "编辑会员成功";
    public static final String TELEPHONE_VALIDATECODE_NOTNULL = "手机号和验证码都不能为空";
    public static final String LOGIN_SUCCESS = "登录成功";
    public static final String VALIDATECODE_ERROR = "验证码输入错误";
    public static final String QUERY_ORDER_SUCCESS = "查询预约信息成功";
    public static final String QUERY_ORDER_FAIL = "查询预约信息失败";
    public static final String QUERY_SETMEALLIST_SUCCESS = "查询套餐列表数据成功";
    public static final String QUERY_SETMEALLIST_FAIL = "查询套餐列表数据失败";
    public static final String QUERY_SETMEAL_SUCCESS = "查询套餐数据成功";
    public static final String QUERY_SETMEAL_FAIL = "查询套餐数据失败";
    public static final String SEND_VALIDATECODE_FAIL = "验证码发送失败";
    public static final String SEND_VALIDATECODE_SUCCESS = "验证码发送成功";
    public static final String SELECTED_DATE_CANNOT_ORDER = "所选日期不能进行体检预约";
    public static final String ORDER_FULL = "预约已满";
    public static final String HAS_ORDERED = "已经完成预约，不能重复预约";
    public static final String ORDER_SUCCESS = "预约成功";
    public static final String GET_USERNAME_SUCCESS = "获取当前登录用户名称成功";
    public static final String GET_USERNAME_FAIL = "获取当前登录用户名称失败";
    public static final String GET_MENU_SUCCESS = "获取当前登录用户菜单成功";
    public static final String GET_MENU_FAIL = "获取当前登录用户菜单失败";
    public static final String GET_MEMBER_NUMBER_REPORT_SUCCESS = "获取会员统计数据成功";
    public static final String GET_MEMBER_NUMBER_REPORT_FAIL = "获取会员统计数据失败";
    public static final String GET_SETMEAL_COUNT_REPORT_SUCCESS = "获取套餐统计数据成功";
    public static final String GET_SETMEAL_COUNT_REPORT_FAIL = "获取套餐统计数据失败";
    public static final String GET_BUSINESS_REPORT_SUCCESS = "获取运营统计数据成功";
    public static final String GET_BUSINESS_REPORT_FAIL = "获取运营统计数据失败";
    public static final String GET_SETMEAL_LIST_SUCCESS = "查询套餐列表数据成功";
    public static final String GET_SETMEAL_LIST_FAIL = "查询套餐列表数据失败";
}
```

(2)返回结果Result和PageResult类，放到offcnpe_util工程中

```java
public class Result implements Serializable{
    private boolean flag;//执行结果，true为执行成功 false为执行失败
    private String message;//返回结果信息，主要用于页面提示信息
    private Object data;//返回数据
    public Result(boolean flag, String message) {
        super();
        this.flag = flag;
        this.message = message;
    }

    public Result(boolean flag, String message, Object data) {
        this.flag = flag;
        this.message = message;
        this.data = data;
    }

    public boolean isFlag() {
        return flag;
    }
    public void setFlag(boolean flag) {
        this.flag = flag;
    }
    public String getMessage() {
        return message;
    }
    public void setMessage(String message) {
        this.message = message;
    }

    public Object getData() {
        return data;
    }

    public void setData(Object data) {
        this.data = data;
    }
}

/**
 * 分页结果封装对象
 */
public class PageResult implements Serializable{
    private Long total;//总记录数
    private List rows;//当前页结果
    public PageResult(Long total, List rows) {
        super();
        this.total = total;
        this.rows = rows;
    }
    public Long getTotal() {
        return total;
    }
    public void setTotal(Long total) {
        this.total = total;
    }
    public List getRows() {
        return rows;
    }
    public void setRows(List rows) {
        this.rows = rows;
    }
}
```

(3)封装查询条件的QueryPageBean类，放到offcnpe_util工程中

```java
/**
 * 封装查询条件
 */
public class QueryPageBean implements Serializable{
    private Integer currentPage;//页码
    private Integer pageSize;//每页记录数
    private String queryString;//查询条件

    public Integer getCurrentPage() {
        return currentPage;
    }

    public void setCurrentPage(Integer currentPage) {
        this.currentPage = currentPage;
    }

    public Integer getPageSize() {
        return pageSize;
    }

    public void setPageSize(Integer pageSize) {
        this.pageSize = pageSize;
    }

    public String getQueryString() {
        return queryString;
    }

    public void setQueryString(String queryString) {
        this.queryString = queryString;
    }
}
```

(4)html、js、css、图片等静态资源，放到offcnpe_controller工程中 

```java
注意：后续随着项目开发还会陆续导入其他一些公共资源。
```

(5)使用Mybatis-plus逆向工程生成基本文件

```java
在offcn_pe工程中执行逆向工程的代码：

public class MyBatisPlusGenerator {
    public static void main(String[] args) {
        // 代码生成器
        AutoGenerator mpg = new AutoGenerator();
        // 全局配置
        GlobalConfig gc = new GlobalConfig();
        //String projectPath = System.getProperty("user.dir");
        gc.setOutputDir("生成代码的路径");
        gc.setAuthor("zs");
        gc.setOpen(false);
        //实体属性 Swagger2 注解
        gc.setSwagger2(false);
        mpg.setGlobalConfig(gc);

        // 数据源配置
        DataSourceConfig dsc = new DataSourceConfig();
        //dsc.setUrl("jdbc:mysql://127.0.0.1:3306/demo?serverTimezone=UTC&useUnicode=true&characterEncoding=utf-8&zeroDateTimeBehavior=convertToNull&useSSL=false&allowPublicKeyRetrieval=true");
        dsc.setUrl("jdbc:mysql:///offcnpe");
        dsc.setDriverName("com.mysql.jdbc.Driver");
        dsc.setUsername("root");
        dsc.setPassword("admin");
        mpg.setDataSource(dsc);

        // 包配置
        PackageConfig pc = new PackageConfig();
        pc.setParent("com.offcn");
        pc.setEntity("pojo");
        pc.setMapper("mapper");
        pc.setServiceImpl("service.xml");
        mpg.setPackageInfo(pc);

        // 配置模板
        TemplateConfig templateConfig = new TemplateConfig();
        //默认关闭不需要的生成内容
        //templateConfig.setXml(null);
        templateConfig.setService(null);
        templateConfig.setServiceImpl(null);
        mpg.setTemplate(templateConfig);

        // 策略配置
        StrategyConfig strategy = new StrategyConfig();
        strategy.setNaming(NamingStrategy.underline_to_camel);
        strategy.setColumnNaming(NamingStrategy.underline_to_camel);
        strategy.setSuperEntityClass("com.baomidou.mybatisplus.extension.activerecord.Model");
        strategy.setEntityLombokModel(true);
        strategy.setRestControllerStyle(true);
        strategy.setEntityLombokModel(true);

        String tableNames="t_checkgroup,t_checkgroup_checkitem,t_checkitem,t_member,t_menu," +
                "t_order,t_ordersetting," +
                "t_permission,t_role,t_role_menu," +
                "t_role_permission,t_setmeal,t_setmeal_checkgroup,t_user,t_user_role";
        strategy.setInclude(tableNames.split(","));
        strategy.setControllerMappingHyphenStyle(true);
        strategy.setTablePrefix("t_");
        mpg.setStrategy(strategy);
        mpg.execute();
    }
}
```



###### (三)新增检查项功能实现

1：编写页面

(1)弹出新增窗口

```java
页面中已经提供了新增窗口，只是处于隐藏状态。只需要将控制展示状态的属性 dialogFormVisible改为true就可以显示出新增窗口。 新建按钮绑定的方法为handleCreate，所以在handleCreate方法中修改 dialogFormVisible属性的值为true即可。同时为了增加用户体验度，需要每次点击新建 按钮时清空表单输入项

// 重置表单 
resetForm() { 
    this.formData = {}; 
},
// 弹出添加窗口 
handleCreate() {
    this.resetForm(); 
    this.dialogFormVisible = true; 
}
```

(2)提交表单数据 

```java
点击新增窗口中的确定按钮时，触发handleAdd方法，所以需要在handleAdd方法中进行完善,因为表单中添加了校验，只有校验通过然后发送ajax请求发送数据，如果校验失败表单不能提交成功的。
/*
                *   获取表单对象,调用校验方法，使用钩子函数完成数据操作
                * */
                this.$refs['dataAddForm'].validate((valid) => {
                    //测试数据是否正常封装
                    //console.log(this.formData)
                    if(valid){
                         //校验成功
                        axios.post('/checkitem/add',this.formData,).then((res) => {
                             //res就是我们返回的offcnpe_util中的Result对象封装的结果,json数据格式
                            //关闭新增窗口(不管什么情况都需要关闭窗口)
                            this.dialogFormVisible = false;
                             if(res.data.flag){
                                 console.log('成功');
                                 //调用分页方法
                                 this.findPage();
                                 //弹出提示信息
                                 this.$message({
                                     message : res.data.message,
                                     type : 'success'
                                 });
                             }else{
                                 console.log('失败');
                                 //弹出失败信息
                                 this.message().error(res.data.message);
                             }
                        });
                    }else{
                         //校验失败
                        this.message().error('数据校验失败,请检查执行');
                        return ;
                    }
                });
            },

```

2：后台代码

(1)控制器方法 在offcnpe_controller中的CheckitemController添加方法

```java
    @RequestMapping("/add")
    @ResponseBody
    public Result add(@RequestBody Checkitem checkitem){
        System.out.println(checkitem);
        try {
            checkItemService.add(checkitem);
        }catch (Exception e){
            e.printStackTrace();
            return new Result(true, MessageConstant.ADD_CHECKITEM_SUCCESS);
        }
        return new Result(true,MessageConstant.ADD_CHECKITEM_FAIL);
    }
```

(2)服务接口 在offcnpe_interface 创建接口

```java
public interface CheckItemService {

    public void add(Checkitem checkitem);

}
```

(3) 服务实现类

```java
在offcnpe_service_provider中实现接口CheckItemService
@Service
public class CheckItemsServiceImpl implements CheckItemService {

    @Resource
    private CheckitemMapper checkitemMapper;

    @Override
    public void add(Checkitem checkitem) {
         checkitemMapper.insert(checkitem);
    }
}
```

###### (四)检查项分页功能

1：功能分析

```java
本项目所有分页功能都是基于ajax的异步请求来完成的，请求参数和后台响应数据格式都 使用json数据格式。 请求参数包括页码、每页显示记录数、查询条件。 
请求参数的json格式为：{currentPage:1,pageSize:10,queryString:''offcn''} 
后台响应数据包括总记录数、当前页需要展示的数据集合。 
响应数据的json格式为：{total:1000,rows:[]}
如下图所示：
```

2：编写页面

(1)定义分页相关模型数据 

```java
pagination: {//分页相关模型数据
     currentPage: 1,//当前页码
     pageSize:10,//每页显示的记录数
     total:0,//总记录数
     queryString:null//查询条件
},
dataList: [],//当前页要展示的分页列表数据
```

(2)利用vue的钩子函数执行分页方法

```java
在页面中提供了findPage方法用于分页查询，为了能够在checkitem.html页面加载后直 接可以展示分页数据，可以在VUE提供的钩子函数created中调用findPage方法

//钩子函数，VUE对象初始化完成后自动执行
created() {
     this.findPage();
},
```

(3)编辑分页方法

```java
//分页查询
findPage() {
   //封装查询参数
   var param = {
    //当前页
    currentPage: this.pagination.currentPage,
     //每页显示数据条数
     pageSize:  this.pagination.pageSize,
     //查询的条件字符串
     queryString: this.pagination.queryString
   };
   //ajax请求完成数据的请求和响应
   axios.post('/checkitem/pageQuery',param,).then((res) => {
      this.pagination.total=res.data.total; //查询的总条数
      this.dataList = res.data.rows; //当前页面展示的数据内容
   });
},
```

(4) 点击查询按钮和点击分页的页码依然需要进行分页查询操作

```java
a:
查询按钮绑定findPage方法
<el-button @click="findPage()" class="dalfBut">查询</el-button>

b：
点击页码执行findPage方法
  <el-pagination
       class="pagiantion"
       @current-change="handleCurrentChange"
       :current-page="pagination.currentPage"
       :page-size="pagination.pageSize"
       layout="total, prev, pager, next, jumper"
       :total="pagination.total">
  </el-pagination>
  
@current-change="handleCurrentChange" UI框架给我们提供的点击页码自动回调的函数

编写方法handleCurrentChange：
 //切换页码
  handleCurrentChange(currentPage) {
      //将点击的页码给我们的当前页从新赋值
      this.pagination.currentPage = currentPage;
      //调用分页查询方法
      this.findPage();
  },
```

3：后台代码实现

(1)CheckitemController增加方法findPage

```java
 @RequestMapping("/findPage")
    @ResponseBody
    public PageResult findPage(@RequestBody QueryPageBean queryPageBean){
        PageResult pageResult = checkItemService.findPage(queryPageBean);
        return pageResult;
    }
```

(2)在CheckItemService服务接口中扩展分页查询方法

```java
 PageResult findPage(QueryPageBean queryPageBean);
```

(3)在CheckItemServiceImpl服务实现类中实现分页查询方法，基于Mybatis-Plus分页助手插件实现分页

```java
 //分页查询检查项所有的数据内容
    @Override
    public PageResult findPage(QueryPageBean queryPageBean) {
        //构建分页page对象
        Page<Checkitem> page1 = new Page<>(queryPageBean.getCurrentPage(),queryPageBean.getPageSize());
        //构建查询条件对象
        QueryWrapper<Checkitem> wrapper = new QueryWrapper<>();
        if(queryPageBean.getQueryString()!=null &&queryPageBean.getQueryString().length()>0){
            wrapper.like("name",queryPageBean.getQueryString());
            wrapper.or();
            wrapper.like("code",queryPageBean.getQueryString());
        }
        //分页查询数据
        Page<Checkitem> checkitemPage = checkitemMapper.selectPage(page1, wrapper);
        return new PageResult(checkitemPage.getTotal(),checkitemPage.getRecords());
    }
```

(4)offcnpe_util项目中添加分页工具类

```java
@Configuration
public class MyBatisPlusConfig {
    /**
     *分页插件
     */
    @Bean
    public MybatisPlusInterceptor mybatisPlusInterceptor() {
        MybatisPlusInterceptor mybatisPlusInterceptor=new MybatisPlusInterceptor();
        PaginationInnerInterceptor innerInterceptor=new PaginationInnerInterceptor();
        innerInterceptor.setDbType(DbType.MYSQL);
        innerInterceptor.setOverflow(true);
        mybatisPlusInterceptor.addInnerInterceptor(innerInterceptor);
        return mybatisPlusInterceptor;
    }
}
```

![列表功能思路分析图示](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/列表功能思路分析图示.jpg)

### Day27



添加事务导致服务消费者无法获取到服务提供者 需要在实现类上添加dubbo的Service(InterfaceClass= 接口.class)，

助记码helpCode方便查询搜索 数据库查询忽略大小写

![image-20210810140535558](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210810140535558.png)

#### 检查项-添加操作

Html

```javascript
//添加检查项
handleAdd () {
//校验
this.$refs["dataAddForm"].validate((val) => {
	if(val){
	axios.post('../checkitem/add',this.formData).then((res) => {
		console.log(res.data);
	if(res.data.flag){
	//提示
	this.$message({
		type:'success',
		message:res.data.message
	});
	//页面刷新
	//location.reload();
	this.dialogFormVisible = false;
	this.findPage();
	}else{
		this.$message.error(res.data.message);
	}
	});
	}else{	
	this.$message.error('有必填项需要填写');
	}
});
```

Controller

```java
//添加功能
@PostMapping("add")
public Result add(@RequestBody TCheckitem checkitem){
    try{
        tCheckitemService.add(checkitem);
        return new Result(true,MessageConstant.ADD_CHECKITEM_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.ADD_CHECKITEM_FAIL,null);
    }
}
```

ServiceImpl

```java
//添加操作 -- 可以没有事务切入
@Override
public void add(TCheckitem checkitem) {
    tCheckitemMapper.insert(checkitem);
}
```

图示

![image-20210810170432204](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210810170432204.png)

#### 检查项-修改操作

Html

```javascript
//弹出编辑窗口
            handleUpdate(row) {
               console.log(row);
               axios.get('../checkitem/findById?id='+row.id).then((res) => {
                   console.log(res.data);
                   if(res.data.flag){
                       this.formData = res.data.obj;
                   }else{
                       this.$message.error(res.data.message);
                   }
               });
               this.dialogFormVisible4Edit = true;
            }
//编辑检查项
handleEdit() {
    //校验
    this.$refs["dataEditForm"].validate((val) => {
        if(val){
            axios.post('../checkitem/update',this.formData).then((res) => {
                console.log(res.data);
                if(res.data.flag){
                    //提示
                    this.$message({
                        type:'success',
                        message:res.data.message
                    });
                    //页面刷新
                    //location.reload();
                    this.dialogFormVisible4Edit = false;
                    this.findPage();
                }else{
                    this.$message.error(res.data.message);
                }
            });
        }else{
            this.$message.error('有必填项需要填写');
        }
    });
}
```

Controller

```java
//修改时数据回显
@GetMapping("findById")
public Result findById(int id){
    try{
        TCheckitem checkitem = tCheckitemService.fildById(id);
        return new Result(true,MessageConstant.QUERY_CHECKITEM_SUCCESS,checkitem);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_CHECKITEM_FAIL,null);
    }
}

//修改功能
@PostMapping("update")
public Result update(@RequestBody TCheckitem checkitem){
    try{
        tCheckitemService.update(checkitem);
        return new Result(true,MessageConstant.EDIT_CHECKITEM_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.EDIT_CHECKITEM_FAIL,null);
    }
}
```

ServiceImpl

```java
//主键查询
@Override
public TCheckitem fildById(int id) {
    return tCheckitemMapper.selectById(id);
}

//修改功能
@Override
public void update(TCheckitem checkitem) {
    tCheckitemMapper.updateById(checkitem);
}
```

图示

![image-20210810170529302](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210810170529302.png)

#### 检查项-删除操作

Html

```javascript
// 删除检查项
handleDelete(row) {
	//提示
	this.$confirm('要删除此项吗？','删除',{type:'info'}).then(() => {
	axios.get('../checkitem/delete?id='+row.id).then((res) => {
		if(res.data.flag){
			this.$message({
			type:'success',
			message:res.data.message
		});
		this.findPage();
		}else{
			this.$message.error(res.data.message);
		}
	});
	}).catch(() => {
		this.$message({
		type:'info',
			message:'取消了删除操作！'
	});
	});
}
```

Controller

```java
//删除功能
@GetMapping("delete")
public Result delete(int id){
    try{
        tCheckitemService.delete(id);
        return new Result(true,MessageConstant.DELETE_CHECKITEM_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.DELETE_CHECKITEM_FAIL,null);
    }
}
```

ServiceImpl

```java
//删除功能
@Override
@Transactional
public void delete(int id) {
    //多条SQL
    //先操作外键表
    QueryWrapper<TCheckgroupCheckitem> wrapper = new QueryWrapper<>();
    wrapper.eq("checkitem_id",id);
    checkgroupCheckitemMapper.delete(wrapper);
    //再操作主键表
    tCheckitemMapper.deleteById(id);
}
```

图示

![image-20210810170605583](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210810170605583.png)

![image-20210810213744733](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210810213744733.png)

#### 检查组-查询操作

Html

```javascript
//分页查询
findPage() {
    //异步请求 -- 参数
    axios.post('../checkgroup/findPage',this.pagination).then((res) => {
        console.log(res.data);
        this.pagination.total = res.data.obj.total;
        this.dataList = res.data.obj.list;
    });
},
```

Controller

```java
//分页查询
@PostMapping("findPage")
public Result findPage(@RequestBody QueryPageBean pageBean){
    try{
        PageResult pageResult = tcheckgroupService.findPage(pageBean);
        return new Result(true, MessageConstant.QUERY_CHECKGROUP_SUCCESS,pageResult);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false, MessageConstant.QUERY_CHECKGROUP_FAIL,null);
    }
}
```

ServiceImpl

```java
//分页查询
@Override
public PageResult findPage(QueryPageBean pageBean) {
    Page<TCheckgroup>page = new Page<>(pageBean.getCurrentPage(),pageBean.getPageSize());
    QueryWrapper<TCheckgroup>wrapper = new QueryWrapper<>();
    if(StringUtils.isNotEmpty(pageBean.getQueryString())){
        wrapper.eq("code",pageBean.getQueryString());
        wrapper.or();
        wrapper.like("name",pageBean.getQueryString());
        wrapper.or();
        wrapper.like("helpCode",pageBean.getQueryString());
    }
    Page<TCheckgroup> checkgroupPage = tCheckgroupMapper.selectPage(page, wrapper);
    return new PageResult(checkgroupPage.getTotal(),checkgroupPage.getRecords());
}
```

### Day28

#### 检查组-新增检查组

打开对话框（清空对话框信息）、初始化（双向绑定数据）、默认显示标签页第一个选项卡、检查组包含检查项信息列表

axios.post( ).then(res => { }) .catch(err => { }) .finally(()=>{ })

Html

```javascript
//弹出添加窗口
handleCreate() {
    //显示对话框
    this.dialogFormVisible = true;
    //初始化数据
    this.formData = {};
    this.checkitemIds = [];
    //默认选择第一个选项卡
    this.activeName = 'first';
    //检查项列表展示
    axios.get('../checkitem/findAll').then((res) => {
        console.log(res.data);
        if(res.data.flag){
            this.tableData = res.data.obj;
        }else{
            this.$message.error(res.data.message);
        }
    });
},
```

```javascript
//添加
handleAdd () {
    axios.post('../checkgroup/add?checkitemIds='+this.checkitemIds,this.formData).then((res) => {
        if(res.data.flag){
            this.$message({
                type:'success',
                message:res.data.message
            });
            this.findPage();
        }else{
            this.$message.error(res.data.message);
        }
    }).finally(() => {
        this.dialogFormVisible = false;
    });
}
```

Controller

```java
//查询所有
@GetMapping("findAll")
public Result findAll(){
    try{
        List<TCheckitem> list = tCheckitemService.findAll();
        return new Result(true,MessageConstant.QUERY_CHECKITEM_SUCCESS,list);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_CHECKITEM_FAIL,null);
    }
}
//添加功能
@PostMapping("add")
public Result add(int[]checkitemIds, @RequestBody TCheckgroup checkgroup){
    try{
        tcheckgroupService.add(checkitemIds,checkgroup);
        return new Result(true,MessageConstant.ADD_CHECKGROUP_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.ADD_CHECKGROUP_FAIL,null);
    }
}
```

ServiceImpl

```java
//查询所有
@Override
public List<TCheckitem> findAll() {
    return tCheckitemMapper.selectList(null);
}
//添加检查组数据  添加中间表
@Override
@Transactional
public void add(int[] checkitemIds, TCheckgroup checkgroup) {
    String name = checkgroup.getName();
    String helpCode = ChineseCharToEn.getAllFirstLetter(name);
    checkgroup.setHelpCode(helpCode.toUpperCase());

    tCheckgroupMapper.insert(checkgroup);
    Integer checkgroupId = checkgroup.getId();
    for(int itemId : checkitemIds){
        TCheckgroupCheckitem checkgroupCheckitem = new TCheckgroupCheckitem();
        checkgroupCheckitem.setCheckgroupId(checkgroupId);
        checkgroupCheckitem.setCheckitemId(itemId);
        tCheckgroupCheckitemMapper.insert(checkgroupCheckitem);
    }
}
```

**获取助记码 使用现成的轮子**

#### 检查组-编辑检查组

弹框显示、检查项列表显示、回显数据（新增VO对象存储检查组和检查项两个对象信息，可以继承检查组，增加检查项id数组）

前端逻辑双向绑定 checkItemIds 绑定的数组 就是勾选

LambdaQueryWrapper 查询 

wrapper.eq(TCheckroupCheckitem::getCheckgroupId,id) 条件表达式 ::在java8中的作用就是获得方法

wrapper.select((TCheckroupCheckitem::getCheckitemId)筛选

selectObjs(wrapper)

List Object --- List Map String,Object --- Integer

![image-20210811105216221](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210811105216221.png)

工具类 Spring-beans 同名属性复制 BeanUtils.copyProperties(tCheckgroup,vo)

检查项信息 先删除再添加（变化不一定，先删除在添加简单）

Html

```html
//
// 弹出编辑窗口
handleUpdate(row) {
	//弹框显示
	this.dialogFormVisible4Edit = true;
	//默认选择第一个选项卡
	this.activeName = 'first';
	//检查项列表展示
	axios.get('../checkitem/findAll').then((res) => {
		console.log(res.data);
		if(res.data.flag){
			this.tableData = res.data.obj;
		}else{
			this.$message.error(res.data.message);
		}
	});
	//回显数据 -- 检查组基本信息和被包含的检查项的id-ids
	axios.get('../checkgroup/findById?id='+row.id).then((res) => {
		if(res.data.flag){
			this.formData = res.data.obj;
			this.checkitemIds = res.data.obj.checkitemIds;
		}else{
			this.$message.error(res.data.message);
		}
	});
}
//编辑检查组
handleEdit() {
	axios.post('../checkgroup/update?checkitemIds='+this.checkitemIds,this.formData).then((res) => {
		if(res.data.flag){
			this.$message({
				type:'success',
				message:res.data.message
			});
			this.findPage();
		}else{
			this.$message.error(res.data.message);
		}
	}).finally(() => {
		this.dialogFormVisible4Edit = false;
	});
}
```

Controller

```java
//查询所有
@GetMapping("findAll")
public Result findAll(){
    try{
        List<TCheckitem> list = tCheckitemService.findAll();
        return new Result(true,MessageConstant.QUERY_CHECKITEM_SUCCESS,list);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_CHECKITEM_FAIL,null);
    }
}
//检查组数据回显
@GetMapping("findById")
public Result findById(int id){
    try{
        TCheckgroupVo vo = tcheckgroupService.findById(id);
        return new Result(true,MessageConstant.QUERY_CHECKGROUP_SUCCESS,vo);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_CHECKGROUP_FAIL,null);
    }
}
//修改功能
@PostMapping("update")
public Result update(int[]checkitemIds,@RequestBody TCheckgroup checkgroup){
    try{
        tcheckgroupService.update(checkitemIds,checkgroup);
        return new Result(true,MessageConstant.EDIT_CHECKGROUP_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.EDIT_CHECKGROUP_FAIL,null);
    }
}
```

ServiceImpl

```java
//查询所有
@Override
public List<TCheckitem> findAll() {
    return tCheckitemMapper.selectList(null);
}
//回显检查组数据 -- 包含当前组包括的检查项(id)
@Override
public TCheckgroupVo findById(int id) {
    //检查组
    TCheckgroup tCheckgroup = tCheckgroupMapper.selectById(id);

    //对应的检查项 -- ids
    LambdaQueryWrapper<TCheckgroupCheckitem>wrapper = new LambdaQueryWrapper<>();
    //设置条件 checkgroup_id = id
    wrapper.eq(TCheckgroupCheckitem::getCheckgroupId,id);
    //筛选 -- 只需要检查项字段
    wrapper.select(TCheckgroupCheckitem::getCheckitemId);

    //List4<Object> == List<Map<String,Object>> == List<Integer>
    List<Integer> itemIds = tCheckgroupCheckitemMapper.selectObjs(wrapper).stream().map(o -> (Integer) o).collect(Collectors.toList());

    TCheckgroupVo vo = new TCheckgroupVo();
    vo.setCheckitemIds(itemIds);
    BeanUtils.copyProperties(tCheckgroup,vo);

    return vo;
}
//修改 -- 修改检查组和所包含的检查项(中间表修改)
@Override
@Transactional
public void update(int[] checkitemIds, TCheckgroup checkgroup) {
    String name = checkgroup.getName();	
    String helpCode = ChineseCharToEn.getAllFirstLetter(name);
    checkgroup.setHelpCode(helpCode.toUpperCase());
    tCheckgroupMapper.updateById(checkgroup);

    Integer checkgroupId = checkgroup.getId();
    //先删除 -- yoga组id做条件
    QueryWrapper<TCheckgroupCheckitem>wrapper = new QueryWrapper<>();
    wrapper.eq("checkgroup_id",checkgroupId);
    tCheckgroupCheckitemMapper.delete(wrapper);

    //再添加
    for(int itemId : checkitemIds){
        TCheckgroupCheckitem checkgroupCheckitem = new TCheckgroupCheckitem();
        checkgroupCheckitem.setCheckgroupId(checkgroupId);
        checkgroupCheckitem.setCheckitemId(itemId);
        tCheckgroupCheckitemMapper.insert(checkgroupCheckitem);
    }
}
```

#### 检查组-删除检查组

先删除外键表、再删除主键表

联合主键（加起来唯一、一块做主键约束）

Html

```javascript
// 删除
handleDelete(row) {
    this.$confirm('是否要删除当前组','删除',{type:'warning'}).then(() => {
        axios.get('../checkgroup/delete?id='+row.id).then((res) => {
            if(res.data.flag){
                this.$message({
                    type:'success',
                    message:res.data.message
                });
                this.findPage();
            }else{
                this.$message.error(res.data.message);
            }
        });
    }).catch(() => {
        this.$message({
            type:'info',
            message:'取消了删除操作'
        });
    });
}
```

Controller

```java
//删除操作
@GetMapping("delete")
public Result delete(int id){
    try{
        tcheckgroupService.delete(id);
        return new Result(true,MessageConstant.DELETE_CHECKGROUP_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.DELETE_CHECKGROUP_FAIL,null);
    }
}
```

ServiceImpl

```java
@Override
@Transactional
public void delete(int id) {
    //先删除外键表
    QueryWrapper<TCheckgroupCheckitem>wrapper = new QueryWrapper<>();
    wrapper.eq("checkgroup_id",id);
    tCheckgroupCheckitemMapper.delete(wrapper);
    //再删除主键表
    tCheckgroupMapper.deleteById(id);
}
```

#### 套餐列表-列表展示

Html

```javascript
//分页查询
findPage() {
    axios.post('../setmeal/findPage',this.pagination).then((res) => {
        if(res.data.flag){
            this.pagination.total = res.data.obj.total;
            this.dataList = res.data.obj.list;
        }else{
            this.$message.error(res.data.message);
        }
    });
}
```

Controller

```java
//分页列表查询
@PostMapping("findPage")
public Result findPage(@RequestBody QueryPageBean pageBean){
    try{
        PageResult pageResult = tsetmealService.findPage(pageBean);
        return new Result(true, MessageConstant.QUERY_SETMEAL_SUCCESS,pageResult);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false, MessageConstant.QUERY_SETMEAL_FAIL,null);
    }
}
```

Service

```java
//分页查询
@Override
public PageResult findPage(QueryPageBean pageBean) {
    Page<TSetmeal>page = new Page<>(pageBean.getCurrentPage(),pageBean.getPageSize());
    QueryWrapper<TSetmeal>wrapper = new QueryWrapper<>();
    if(StringUtils.isNotEmpty(pageBean.getQueryString())){
        wrapper.like("code",pageBean.getQueryString());
        wrapper.or();
        wrapper.like("name",pageBean.getQueryString());
        wrapper.or();
        wrapper.like("helpCode",pageBean.getQueryString());
    }
    Page<TSetmeal> setmealPage = tSetmealMapper.selectPage(page, wrapper);
    return new PageResult(setmealPage.getTotal(),setmealPage.getRecords());
}
```

### Day29

#### 套餐列表-套餐添加

##### 检查组列表

Html

```javascript
// 弹出添加窗口
handleCreate() {
    this.formData = {};
    this.imageUrl = '';
    this.checkgroupIds = [];
    this.activeName = 'first';
    this.dialogFormVisible = true;
    axios.get('../checkgroup/findAll').then((res) => {
        if(res.data.flag){
            this.tableData = res.data.obj;
        }else{
            this.$message.error(res.data.message);
        }
    });
}
```

Controller

```java
//查询所有列表
@GetMapping("findAll")
public Result findAll(){
    try{
        List<TCheckgroup> list = tcheckgroupService.findAll();
        return new Result(true,MessageConstant.QUERY_CHECKGROUP_SUCCESS,list);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_CHECKGROUP_FAIL,null);
    }
}
```

ServiceImpl

```java
//查询所有
    @Override
    public List<TCheckgroup> findAll() {
        return tCheckgroupMapper.selectList(null);
    }
```

##### 页面图片上传

Html

```javascript
//文件上传成功后的钩子，response为服务端返回的值，file为当前上传的文件封装成的js对象
handleAvatarSuccess(response, file) {
    //获取到后台送回来的图片信息--路径和名称--给img标签
    console.log(response)
    this.imageUrl = '../' + response.obj;//<img src='../2.jpg'>
    this.formData.img = response.obj;
},
```

Controller

```java
//上传功能
@PostMapping("upload")
public Result upload(MultipartFile imgFile){
    try {
        if (imgFile != null && !imgFile.isEmpty()) {
            String originalFilename = imgFile.getOriginalFilename();
            System.out.println(originalFilename);
            int indexOf = originalFilename.lastIndexOf(".");
            String extName = originalFilename.substring(indexOf);
            String newName = UUID.randomUUID().toString().replaceAll("-", "") + extName;

            String path = "C:\\Users\\Administrator\\Desktop\\offcnpe";
            File file = new File(path, newName);
            imgFile.transferTo(file);
            //向redis中存文件名称 -- 上传成功时的文件名
            redisTemplate.boundSetOps(RedisConstant.UPLOAD_KEY).add(newName);
            return new Result(true, MessageConstant.UPLOAD_SUCCESS, newName);
        }
    }catch (Exception e){
        e.printStackTrace();
    }
    return new Result(false,MessageConstant.PIC_UPLOAD_FAIL,null);
}
```

配置静态资源保存位置

```yaml
web:
    resources:
      static-locations: classpath:/META-INFO/resources/,classpath:/static/,classpath:/public/,classpath:/resources/,file:///C:\Users\Administrator\Desktop\offcnpe

```

##### 添加实现

先加 本表 在加中间表

Html

```javascript
//添加
handleAdd () {
    axios.post('../setmeal/add?checkgroupIds='+this.checkgroupIds,this.formData).then((res) => {
        if(res.data.flag){
            this.$message({
                type:'success',
                message:res.data.message
            })
            this.dialogFormVisible = false;
            this.findPage();
        }else{
            this.$message.error(res.data.message);
        }
    })
```

Controller

```java
//添加功能
@PostMapping("add")
public Result add(int[]checkgroupIds, @RequestBody TSetmeal setmeal){
    try{
        tsetmealService.add(checkgroupIds,setmeal);
        //向redis中添加文件名 -- 在向数据库添加数据成功时
        String img = setmeal.getImg();
        redisTemplate.boundSetOps(RedisConstant.ADD_KEY).add(img);
        return new Result(true,MessageConstant.ADD_SETMEAL_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.ADD_SETMEAL_FAIL,null);
    }
}
```

ServiceImpl

```java
//添加功能
@Transactional
@Override
public void add(int[] checkgroupIds, TSetmeal setmeal) {
    tSetmealMapper.insert(setmeal);
    Integer setmealId = setmeal.getId();
    for(int groupId : checkgroupIds){
        TSetmealCheckgroup setmealCheckgroup = new TSetmealCheckgroup();
        setmealCheckgroup.setSetmealId(setmealId);
        setmealCheckgroup.setCheckgroupId(groupId);
        tSetmealCheckgroupMapper.insert(setmealCheckgroup);
    }
}
```

##### 可能有多余的上传文件，删除文件的分析和准备

Redis 缓存 使用 Set 数据结构 有求差的操作

图片每上传成功一次 Redis 缓存一次文件的名字；

每保存数据库成功一次 Redis 缓存一次文件的名字

![image-20210812213819520](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210812213819520.png)

配置 并 启动Redis

```yaml
redis:
  host: 192.168.159.128
  port: 6379
  password: 123
```

sh 脚本启动文件

![image-20210812214850114](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210812214850114.png)

增加执行权限

![image-20210812215005089](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210812215005089.png)

##### Redis 缓存图片名称

RedisConstant 

存储 Redis库中的 key 名称

```java
package com.offcn.util;

public class RedisConstant {
    public final static String UPLOAD_KEY = "upload_";
    public final static String ADD_KEY = "add_";
}
```

使用 StringRedisTemplate 模板 不会加入序列化数据存入

```java
@Autowired
private StringRedisTemplate redisTemplate;
```

```java
//向redis中存文件名称 -- 上传成功时的文件名
redisTemplate.boundSetOps(RedisConstant.UPLOAD_KEY).add(newName);
```

```java
//向redis中添加文件名 -- 在向数据库添加数据成功时
String img = setmeal.getImg();
redisTemplate.boundSetOps(RedisConstant.ADD_KEY).add(img);
```

##### 作业调度框架介绍

定时删除多余的图片

Quartz（石英）

**Quartz 核心概念**

------

 我们需要明白 Quartz 的几个核心概念，这样理解起 Quartz 的原理就会变得简单了。

1. Job 

   表示一个工作，要执行的具体内容。此接口中只有一个方法，如下：

   ```
   void execute(JobExecutionContext context) 
   ```

2. **JobDetail** 表示一个具体的可执行的调度程序，Job 是这个可执行程调度程序所要执行的内容，另外 JobDetail 还包含了这个任务调度的方案和策略。

3. **Trigger** 代表一个调度参数的配置，什么时候去调。

4. **Scheduler** 代表一个调度容器，一个调度容器中可以注册多个 JobDetail 和 Trigger。当 Trigger 与 JobDetail 组合，就可以被 Scheduler 容器调度了。

#### 定时任务框架quartz介绍

```
Quartz是OpenSymphony开源组织在Job scheduling领域又一个开源项目，完全由Java开发，可以用来执行定时任务，类似于java.util.Timer。但是相较于Timer， Quartz增加了很多功能：
持久性作业 - 就是保持调度定时的状态;
作业管理 - 对调度作业进行有效的管理;
大部分公司都会用到定时任务这个功能。
拿火车票购票来说，当你下单后，后台就会插入一条待支付的task(job)，一般是30分钟，超过30min后就会执行这个job，去判断你是否支付，未支付就会取消此次订单；当你支付完成之后，后台拿到支付回调后就会再插入一条待消费的task（job），Job触发日期为火车票上的出发日期，超过这个时间就会执行这个job，判断是否使用等。
在我们实际的项目中，当Job过多的时候，肯定不能人工去操作，这时候就需要一个任务调度框架，帮我们自动去执行这些程序。那么该如何实现这个功能呢？
```

#### 重要组件介绍

#####     （1） job组件

```
 首先我们需要定义实现一个定时功能的接口，我们可以称之为Task（或Job），如定时发送邮件的task（Job），重启机器的task（Job），优惠券到期发送短信提醒的task（Job），实现接口如下：
```

![image-20210812224305954](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210812224305954.png)

##### （2） 触发器组件Trigger

```
有了任务之后，还需要一个能够实现触发任务去执行的触发器，触发器Trigger最基本的功能是指定Job的执行时间，执行间隔，运行次数等。
```

![Trigger](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/2.png)

##### （3）调度器组件

```
有了Job和Trigger后，怎么样将两者结合起来呢？即怎样指定Trigger去执行指定的Job呢？这时需要一个Schedule，来负责这个功能的实现
```

![Scheduler](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/3.png)

#### 定时任务框架quartz入门案例

```xml
<dependency>
    <groupId>org.quartz-scheduler</groupId>
    <artifactId>quartz</artifactId>
    <version>2.3.2</version>
</dependency>
```

```java
public class CustomJob implements Job {
    @Override
    public void execute(JobExecutionContext jobExecutionContext) throws JobExecutionException {
        System.out.println(System.currentTimeMillis());
        try {
            Object name1 = jobExecutionContext.getScheduler().getContext().get("name1");
            System.out.println(name1);
        }catch (Exception e){
            e.printStackTrace();
        }
        Object name2 = jobExecutionContext.getJobDetail().getJobDataMap().get("name2");
        System.out.println(name2);
        Object name3 = jobExecutionContext.getTrigger().getJobDataMap().get("name3");
        System.out.println(name3);
        System.out.println("============");
    }
}
```

```java
public static void main(String[]args)throws Exception{
        //容器
        Scheduler scheduler = StdSchedulerFactory.getDefaultScheduler();
        scheduler.getContext().put("name1","scheduler中放数据");
        //调度
        JobDetail jobDetail = JobBuilder.newJob(CustomJob.class)
                                        .withIdentity("myjob", "mygroup")
                                        .build();
        jobDetail.getJobDataMap().put("name2","jobdetail中放数据");
        long l = System.currentTimeMillis() + 5000;
        //触发
        Trigger trigger = TriggerBuilder.newTrigger()
                                        .withIdentity("trigger1", "group1")
                                        //.withSchedule(SimpleScheduleBuilder.simpleSchedule().withIntervalInSeconds(3).repeatForever())
                                        //.startAt(new Date(l))
                                        .withSchedule(CronScheduleBuilder.cronSchedule("0/3 * * * * ? "))
                                        .build();
        trigger.getJobDataMap().put("name3","trigger中放数据");
        //结合
        scheduler.scheduleJob(jobDetail,trigger);

        //执行
        scheduler.start();
}
```

任务调度框架

容器、调度、触发

都可以传递数据

Simple Trigger

**CronTrigger 更加灵活**

cron 谷物 linux 中调度控制

Cron-Expressions用于配置CronTrigger的实例。Cron Expressions是由**七个子表达式**组成的字符串，用于描述日程表的各个细节。这些子表达式用空格分隔，并表示：

1. Seconds
2. Minutes
3. Hours
4. Day-of-Month
5. Month
6. Day-of-Week
7. Year (optional field)

在线生成器地址：

https://www.bejson.com/othertools/cron/

#### 项目中添加任务调度功能

job 模块 定时清理文件

三个依赖 不用加 quartz 依赖 springboot 封装了

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-redis</artifactId>
        <version>2.4.9</version>
    </dependency>
    <dependency>
        <groupId>com.offcn</groupId>
        <artifactId>offcnpe_util</artifactId>
        <version>1.0</version>
    </dependency>
</dependencies>
```

Spring 家族的 Task 和 Quartz 都是任务调度框架 

exclude 没有数据源

注解 EnableScheduling

```java
@SpringBootApplication(exclude = DataSourceAutoConfiguration.class)
@EnableScheduling
public class JobApplication {
    public static void main(String[] args) {
        SpringApplication.run(JobApplication.class,args);
    }
}
```

任务任意方法 不用实现

任务 -- 执行删除多余文件操作

求差 -- 找出多余文件的名称

到指定文件路径按照多余文件名称删除文件

Redis upload、add 缓存也需要更新

注解 Scheduled（cron=表达式）

```java
//任务 -- 执行删除多余文件工作8dfd059e72d64b2f90d3faf473c2b26f.jpg   3fffcf67a16f43feb51bcb93f753145e.jpg
@Component
public class FileDeleteJob{

    @Autowired
    private StringRedisTemplate redisTemplate;

    //@Scheduled(cron = "0 59 23 * * ? ")
    @Scheduled(cron = "0/10 * * * * ? ")
    public void deleteFile(){
        //求差 -- 找出多余文件的名称
        Set<String> names = redisTemplate.opsForSet().difference(RedisConstant.UPLOAD_KEY, RedisConstant.ADD_KEY);
        //到指定路径按照多余文件的名称删除文件
        for(String name : names){
            String path = "C:\\Users\\Administrator\\Desktop\\offcnpe";
            File file = new File(path,name);
            file.delete();
            //redis的集合更新
            redisTemplate.boundSetOps(RedisConstant.UPLOAD_KEY).remove(name);
        }
    }
```

#### 套餐列表-套餐修改

##### 数据回显

Html

```javascript
//弹层修改窗口
handleUpdate(row){
    this.activeName = 'first';
    this.dialogFormVisible4Edit = true;
    axios.get('../checkgroup/findAll').then((res) => {
        if(res.data.flag){
            this.tableData = res.data.obj;
        }else{
            this.$message.error(res.data.message);
        }
    });
    axios.get('../setmeal/findById?id='+row.id).then((res) => {
        if(res.data.flag){
            this.formData = res.data.obj;
            this.imageUrl = '../' + res.data.obj.img;
            this.checkgroupIds = res.data.obj.checkgroupIds;
        }else{
            this.$message.error(res.data.message);
        }
    });
}
```

创建 VO 套餐包含检查组列表

```java
@Data
@EqualsAndHashCode(callSuper = true)
public class TSetmealVo extends TSetmeal {

    private List<Integer> checkgroupIds;
}
```

Controller

```java
//数据回显
@GetMapping("findById")
public Result findById(int id){
    try{
        TSetmealVo vo = tsetmealService.findById(id);
        return new Result(true,MessageConstant.QUERY_SETMEALLIST_SUCCESS,vo);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_SETMEALLIST_FAIL,null);
    }
}
```

ServiceImpl

```java
//主键查询
@Override
public TSetmealVo findById(int id) {
    TSetmeal tSetmeal = tSetmealMapper.selectById(id);

    LambdaQueryWrapper<TSetmealCheckgroup>wrapper = new LambdaQueryWrapper<>();
    wrapper.eq(TSetmealCheckgroup::getSetmealId,id);
    wrapper.select(TSetmealCheckgroup::getCheckgroupId);
    List<Integer> collect = tSetmealCheckgroupMapper.selectObjs(wrapper).stream().map(o -> (Integer) o).collect(Collectors.toList());

    TSetmealVo vo = new TSetmealVo();
    BeanUtils.copyProperties(tSetmeal,vo);
    vo.setCheckgroupIds(collect);

    return vo;
}
```

##### 添加实现实现

需要添加 缓存 因为是set 所以不论改还是没改 都完成功能

Html

```javascript
//添加
handleAdd () {
    axios.post('../setmeal/add?checkgroupIds='+this.checkgroupIds,this.formData).then((res) => {
        if(res.data.flag){
            this.$message({
                type:'success',
                message:res.data.message
            })
            this.dialogFormVisible = false;
            this.findPage();
        }else{
            this.$message.error(res.data.message);
        }
    });
}
```

Controller

```java
//修改功能
@PostMapping("update")
public Result update(int[] checkgroupIds,@RequestBody TSetmeal setmeal){
    try{
        tsetmealService.update(checkgroupIds,setmeal);
        redisTemplate.boundSetOps(RedisConstant.ADD_KEY).add(setmeal.getImg());
        return new Result(true,MessageConstant.EDIT_SETMEAL_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.EDIT_SETMEAL_FAIL,null);
    }
}
```

ServiceImpl

```java
//修改功能
@Transactional
@Override
public void update(int[] checkgroupIds, TSetmeal setmeal) {
    Integer setmealId = setmeal.getId();
    TSetmeal tSetmeal = tSetmealMapper.selectById(setmealId);
    //判断文件名是否修改了，如果修改了，则删除旧文件
    String front = setmeal.getImg();
    String db = tSetmeal.getImg();
    if(!front.equals(db)){
        String path = "C:\\Users\\Administrator\\Desktop\\offcnpe";
        File file = new File(path,db);
        file.delete();
    }
    //修改套餐数据
    tSetmealMapper.updateById(setmeal);
    //先删除中间表数据
    QueryWrapper<TSetmealCheckgroup>wrapper = new QueryWrapper<>();
    wrapper.eq("setmeal_id",setmealId);
    tSetmealCheckgroupMapper.delete(wrapper);

    //再添加中间表数据
    for(int checkgroupid : checkgroupIds){
        TSetmealCheckgroup setmealCheckgroup = new TSetmealCheckgroup();
        setmealCheckgroup.setSetmealId(setmealId);
        setmealCheckgroup.setCheckgroupId(checkgroupid);

        tSetmealCheckgroupMapper.insert(setmealCheckgroup);
    }
}
```

#### 套餐列表-套餐删除

Html

```javascript
handleDelete(row){
    this.$confirm('是否要删除当前数据','删除',{type:'warning'}).then(() => {
        axios.get('../setmeal/delete?id='+row.id).then((res) => {
            if(res.data.flag){
                this.$message({
                    type:'success',
                    message:res.data.message
                })
                this.findPage();
            }else{
                this.$message.error(res.data.message);
            }
        });
    }).catch(() =>{
        this.$message.error('取消了删除操作');
    });
}
```

Controller

```java
//删除操作
@GetMapping("delete")
public Result delete(int id){
    try{
        tsetmealService.delete(id);
        return new Result(true,MessageConstant.DELETE_SETMEAL_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        System.out.println(e.getMessage());
        return new Result(false,MessageConstant.DELETE_SETMEAL_FAIL+";"+e.getMessage(),null);
    }
}

ServiceImpl

​```java
//删除套餐
@Transactional
@Override
public void delete(int id) {
    //判断订单表中是否有相关的套餐，如果有则不删除，没有则删除
    QueryWrapper<TOrder>wrapper = new QueryWrapper<>();
    wrapper.eq("setmeal_id",id);
    Integer count = tOrderMapper.selectCount(wrapper);
    if(count > 0){
        throw new RuntimeException("订单表中有相关套餐，套餐不能删除");
    }
    //先删除中间表
    QueryWrapper<TSetmealCheckgroup>wrapper2 = new QueryWrapper<>();
    wrapper2.eq("setmeal_id",id);
    tSetmealCheckgroupMapper.delete(wrapper2);
    //再删除主键表
    tSetmealMapper.deleteById(id);
}
```

### Day30

#### 预约条件设置

可预约 与 与 已预约 的信息

设置点击修改当天的可预约人数（一天一天的设置累死了）

模板下载 与 上传文件（Excel 文件 日期与可预约数量）

下载 Excel 表的格式，填写上传，程序解析 Excel MySQL 填充数据

#### 文件下载

文件链接下载 和 一个头 两个流 的下载文件方式

```java
//下载模板文件
downloadTemplate(){
    window.location.href="../template/ordersetting_template.xlsx";
},
```

#### 文件上传

#### POI

如何 读取 如何 存储

poi 操作 office

```xml
<dependency>
  <groupId>org.apache.poi</groupId>
  <artifactId>poi-ooxml</artifactId>
  <version>3.17</version>
</dependency>
```

![image-20210813094946089](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210813094946089.png)

##### 读取文档内容

创建工作簿对象

从工作簿对象中获取 sheet 表 -- 表对象

从表中获取行 -- 行对象

从行中获取单元格 -- 单元格对象

从单元格中获取值 -- 单元格对象

```java
//读取Excel文档内容 -- 导入
@Test
public void testRead()throws Exception{
    //获取工作簿 -- 创建工作簿对象
    //Workbook workbook = new XSSFWorkbook("C:\\Users\\Administrator\\Desktop\\工作表.xlsx");//针对xlsx格式文件
    Workbook workbook = new HSSFWorkbook(new FileInputStream("C:\\Users\\Administrator\\Desktop\\工作表.xls"));//针对xlsx格式文件
    //从工作簿对象中获取sheet表 -- 表对象
    Iterator<Sheet> iterator = workbook.iterator();
    while(iterator.hasNext()){
        Sheet sheet = iterator.next();
        //从表中获取行 -- 行对象
        int firstRowNum = sheet.getFirstRowNum();
        int lastRowNum = sheet.getLastRowNum();
        for(int i = firstRowNum;i <= lastRowNum;i++){
            System.out.println("表内容：");
            //从行中获取单元格 -- 单元格对象
            Row row = sheet.getRow(i);
            if(row == null){
                continue;
            }
            //从单元格中获取值 -- 单元格对象
            short firstCellNum = row.getFirstCellNum();
            short lastCellNum = row.getLastCellNum();
            for(int j = firstCellNum;j <= lastCellNum;j++){
                System.out.println("行内容：");
                Cell cell = row.getCell(j);
                if(cell == null)continue;
                String value = cell.getStringCellValue();
                System.out.println(value);
                System.out.println("------------");
            }
            System.out.println("================");
        }
    }
}

```

##### 写出文档内容

工作簿对象 -- 对应一个未来的工作簿

创建 sheet 表对象 -- 对应一个未来的 sheet 表

创建行对象 -- 对应一个未来的行 -- 循环

创建单元格对象 -- 对应未来的单元格 -- 循环

给单元格设置内容

把内存内容写出 -- 写出到服务器本地、写出到用户端远程

释放资源 必须释放

```java
//写出Excel数据 -- 导出
@Test
public void testWrite()throws Exception{
    //工作簿对象 -- 对应一个未来的工作簿
    //Workbook workbook = new XSSFWorkbook();
    Workbook workbook = new HSSFWorkbook();
    //创建sheet表对象 -- 对应一个未来的sheet表
    Sheet sheet = workbook.createSheet("s1");
    //创建行对象 -- 对应一个未来的行 -- 循环
    Row row0 = sheet.createRow(0);
    //创建单元格对象 -- 对应未来的单元格 -- 循环
    Cell cell0 = row0.createCell(0);
    //给单元格设置内容
    cell0.setCellValue("opq");
    //把内存内容写出 -- 写出到服务器本地、写出到用户端远程
    //写出到本地
    OutputStream os = new FileOutputStream("C:\\Users\\Administrator\\Desktop\\1.xls");
    workbook.write(os);
    //释放资源
    os.flush();
    os.close();
    workbook.close();
}
```

#### 文件上传与读取

保证安全 防止不走前端 后端 验证

判断文件类型 endsWith

工具类 POIUtils

判断当前日期对应的数据是否存在

存在修改，不存在添加

LocalDate.parse 字符串日期转换

参数 DateTimeFormatter.ofPattern 

Html

```javascript
//上传成功提示
handleSuccess(response, file) {
    if(response.flag){
        this.$message({
            message: response.message,
            type: 'success'
        });
    }else{
        this.$message.error(response.message);
    }
}
```

Controller

```java
//上传Excel文档
    @PostMapping("uploadTempleate")
    public Result uploadTempleate(MultipartFile excelFile){
        try {
            List<String[]> list = POIUtils.readExcel(excelFile);
            tOrdersettingService.save(list);
            return new Result(true, MessageConstant.UPLOAD_SUCCESS,null);
        }catch (Exception e){
            e.printStackTrace();
            return new Result(false, MessageConstant.UPLOAD_FAIL + ":" + e.getMessage(),null);
        }
    }
```

ServiceImpl

```java
@Transactional
@Override
public void save(List<String[]> list) {
    for(String[] strs : list){
        String dateStr = strs[0];
        String numStr = strs[1];
        //判断当前日期的数据是否已经存在，如果存在则修改，如果不存在则添加
        QueryWrapper<TOrdersetting>wrapper = new QueryWrapper<>();
        wrapper.eq("orderDate",dateStr);
        TOrdersetting one = tOrdersettingMapper.selectOne(wrapper);
        if(one != null){
            //可以覆盖旧值，可以追加值
            one.setNumber(Integer.parseInt(numStr));
            tOrdersettingMapper.updateById(one);
        }else {
            TOrdersetting ordersetting = new TOrdersetting();
            ordersetting.setNumber(Integer.parseInt(numStr));
            ordersetting.setOrderDate(LocalDate.parse(dateStr, DateTimeFormatter.ofPattern("yyyy/MM/dd")));
            tOrdersettingMapper.insert(ordersetting);
        }
    }
}

```

#### 回显到页面

Html

```javascript
axios.get('../ordersetting/findByDate?currentYear='+this.currentYear+"&currentMonth="+this.currentMonth).then((res) => {
    if(res.data.flag){
        this.leftobj = res.data.obj;
    }else{
        this.$message.error(res.data.message);
    }
});
```

Controller

```java
//根据年和月实现页面数据展示
@GetMapping("findByDate")
public Result findByDate(String currentYear,String currentMonth){
    try{
        List<Map<String,Object>> list = tOrdersettingService.findByDate(currentYear, currentMonth);
        return new Result(true,MessageConstant.QUERY_ORDER_SUCCESS,list);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_ORDER_FAIL,null);
    }
}
```

ServiceImpl

```java
//按照日期查询预约数据，实现页面展示
@Override
public List<Map<String, Object>> findByDate(String currentYear, String currentMonth) {
    String start = currentYear + "-" + currentMonth + "-01";
    String end = currentYear + "-" + currentMonth + "-31";
    QueryWrapper<TOrdersetting>wrapper = new QueryWrapper<>();
    wrapper.between("orderDate",start,end);
    List<TOrdersetting> tOrdersettings = tOrdersettingMapper.selectList(wrapper);
    List<Map<String,Object>>list = new ArrayList<>();
    for(TOrdersetting ordersetting : tOrdersettings){
        Map<String,Object>map = new HashMap<>();
        LocalDate orderDate = ordersetting.getOrderDate();
        map.put("date",orderDate.getDayOfMonth());

        Integer number = ordersetting.getNumber();
        map.put("number",number);

        Integer reservations = ordersetting.getReservations();
        map.put("reservations",reservations);

        list.add(map);
    }
    return list;
}
```

#### 设置功能

Html

```javascript
//预约设置
handleOrderSet(day){
    //弹框--弹出--能够输入可预约人数数字--支持确定或者取消操作
    this.$prompt('请输入可预约人数', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        inputPattern: /[1-9][0-9]/,
        inputErrorMessage: '请输入数字'
    }).then(({value}) => {
        //alert(value);
        //alert(day);
        //var orderDate = this.formatDate(day);
        var formData = {
            'orderDate':day,
            'number':value
        };
        axios.post('../ordersetting/update',formData).then((res) => {
            if(res.data.flag){
                this.$message({
                    type:'success',
                    message:res.data.message
                })
                //修改之后初始化页面
                this.initData(null);
            }else{
                this.$message.error(res.data.message);
            }
        });
    }).catch(() => {
        this.$message({
            type:'info',
            message:'取消了修改设置操作'
        })
    });
},
```

Controller

```java
//按照日期修改预约数量
@PostMapping("update")
public Result update(@RequestBody TOrdersetting ordersetting){
    try{
        //System.out.println(ordersetting);
        tOrdersettingService.update(ordersetting);
        return new Result(true,MessageConstant.ORDERSETTING_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.ORDERSETTING_FAIL,null);
    }
}
```

ServiceImpl

```java
//按照日期修改可预约数量
@Override
public void update(TOrdersetting ordersetting) {
    QueryWrapper<TOrdersetting>wrapper = new QueryWrapper<>();
    wrapper.eq("orderDate",ordersetting.getOrderDate());
    tOrdersettingMapper.update(ordersetting,wrapper);
}
```

按照时间查询预约数据 封装显示

下周 前台系统 预约下单完成

### Day31

#### 内容

这周 前台系统 预约下单完成

#### 移动开发

![image-20210816092325304](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210816092325304.png)

![image-20210816092909826](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210816092909826.png)

商城 or 题库（人人网后台终端）

#### 套餐预约

判断当前预约日期是否可以预约

判断当前预约日期是否已满

判断当前是否是会员，如果不是则自动保存为会员信息 -- 使用电话号码或者身份证号码 或者两者同时，判断是否是会员

判断是否已经预约 -- 指定套餐、日期、预约人 

保存订单

LocalDate.parse(字符串,DateTimeFormatter.ofPattern("yyyy-MM-dd"))

更新已预约

##### 套餐列表

Html

```javascript
findPage(){
    axios.post("/setmealcli/getAllSetmeal",this.pagination).then((res)=>{
        if(res.data.flag){
            this.pagination.total = res.data.obj.total;
            this.setmealList = res.data.obj.list;
        }
    });
}
```

Controller

```java
//前台套餐列表
@PostMapping("getAllSetmeal")
public Result getAllSetmeal(@RequestBody QueryPageBean pageBean){
    try {
        PageResult page = tSetmealService.findPage(pageBean);
        return new Result(true, MessageConstant.QUERY_SETMEALLIST_SUCCESS,page);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false, MessageConstant.QUERY_SETMEALLIST_FAIL,null);
    }
}
```

分页

```html
<div class="pagination-container">
    <el-pagination
                   class="pagiantion"
                   @current-change="handleCurrentChange"
                   :current-page="pagination.currentPage"
                   :page-size="pagination.pageSize"
                   layout="total,prev, pager, next"
                   :total="pagination.total">
    </el-pagination>
</div>
```

```javascript
handleCurrentChange(currentPage) {
    this.pagination.currentPage = currentPage;
    this.findPage();
}
```

##### 套餐详情分析

Html

```javascript
findById(){
    axios.post("/setmealcli/findInfoById?id=" + id).then((res) => {
        if(res.data.flag){
            this.setmeal = res.data.obj;
            this.imgUrl = '../' + this.setmeal.img;
        }
    });
}
```

VO 套餐详情 -- 检查组 -- 检查项

```java
@Data
@EqualsAndHashCode(callSuper = true)
public class TSetmealVo extends TSetmeal {

    private List<Integer> checkgroupIds;

    private List<TCheckgroupVo>checkGroups;
}
```

Controller

```java
//套餐详情 -- 有套餐信息、检查组信息、检查项信息
@PostMapping("findInfoById")
public Result findInfoById(int id){
    try{
        TSetmealVo vo = tSetmealService.findById(id);
        return new Result(true,MessageConstant.QUERY_SETMEALLIST_SUCCESS,vo);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_SETMEALLIST_FAIL,null);
    }
}
```

ServiceImpl

```java
//主键查询
@Override
public TSetmealVo findById(int id) {
    TSetmeal tSetmeal = tSetmealMapper.selectById(id);

    LambdaQueryWrapper<TSetmealCheckgroup>wrapper = new LambdaQueryWrapper<>();
    wrapper.eq(TSetmealCheckgroup::getSetmealId,id);
    wrapper.select(TSetmealCheckgroup::getCheckgroupId);
    List<Integer> collect = tSetmealCheckgroupMapper.selectObjs(wrapper).stream().map(o -> (Integer) o).collect(Collectors.toList());

    TSetmealVo vo = new TSetmealVo();
    BeanUtils.copyProperties(tSetmeal,vo);
    vo.setCheckgroupIds(collect);

    //查询检查组、检查项
    List<TCheckgroupVo>vos = new ArrayList<>();

    List<TCheckgroup> tCheckgroups = tCheckgroupMapper.selectBatchIds(collect);
    for(TCheckgroup tCheckgroup : tCheckgroups){
        Integer checkgroupId = tCheckgroup.getId();
        LambdaQueryWrapper<TCheckgroupCheckitem>lambdaQueryWrapper = new LambdaQueryWrapper<>();
        lambdaQueryWrapper.eq(TCheckgroupCheckitem::getCheckgroupId,checkgroupId);
        lambdaQueryWrapper.select(TCheckgroupCheckitem::getCheckitemId);
        List<Integer> itemids = tCheckgroupCheckitemMapper.selectObjs(lambdaQueryWrapper).stream().map(o -> (Integer) o).collect(Collectors.toList());

        List<TCheckitem> tCheckitems = tCheckitemMapper.selectBatchIds(itemids);

        TCheckgroupVo checkgroupVo = new TCheckgroupVo();
        BeanUtils.copyProperties(tCheckgroup,checkgroupVo);
        checkgroupVo.setCheckItems(tCheckitems);

        vos.add(checkgroupVo);
    }

    vo.setCheckGroups(vos);
    return vo;
}
```

##### 预约下单

Html

```javascript
axios.post("/order/submitOrder",this.orderInfo).then((res) => {
    if(res.data.flag){
        window.location.href="orderSuccess.html?orderId="+res.data.obj
    }else{
        this.$message.error(res.data.message);
    }
});
```

Controller

```java
//预约下单
@PostMapping("submitOrder")
public Result submitOrder(@RequestBody Map<String,Object>map){
    Result result = orderService.save(map);
    return result;
}
```

ServiceImpl

```java
@Transactional
@Override
public Result save(Map<String, Object> map) {
    try {
        String orderDateStr = (String) map.get("orderDate");
        //判断当前预约日期是否可以预约
        QueryWrapper<TOrdersetting> ordersettingQueryWrapper = new QueryWrapper<>();
        ordersettingQueryWrapper.eq("orderDate", orderDateStr);
        TOrdersetting ordersetting = tOrdersettingMapper.selectOne(ordersettingQueryWrapper);
        if (ordersetting == null) {
            return new Result(false, MessageConstant.SELECTED_DATE_CANNOT_ORDER, null);
        }

        //判断当前预约日期是否已满
        Integer number = ordersetting.getNumber();
        Integer reservations = ordersetting.getReservations();
        if (number <= reservations) {
            return new Result(false, MessageConstant.ORDER_FULL, null);
        }

        //判断当前是否是会员，如果不是则自动保存称为会员信息 -- 使用电话号码或者身份号码或者两者同时，判断是否是会员
        String phone = (String) map.get("telephone");
        String setmealIdStr = (String) map.get("setmealId");
        int setmealId = Integer.parseInt(setmealIdStr);
        QueryWrapper<TMember> memberQueryWrapper = new QueryWrapper<>();
        memberQueryWrapper.eq("phoneNumber", phone);
        TMember member = tMemberMapper.selectOne(memberQueryWrapper);
        Integer memberId = null;
        //会员存在
        if (member != null) {
            memberId = member.getId();
            QueryWrapper<TOrder> orderQueryWrapper = new QueryWrapper<>();
            orderQueryWrapper.eq("member_id", memberId);
            orderQueryWrapper.eq("orderDate", orderDateStr);
            orderQueryWrapper.eq("setmeal_id", setmealId);
            TOrder order = tOrderMapper.selectOne(orderQueryWrapper);

            //判断是否已经预约 -- 指定套餐、日期、预约人
            if (order != null) {
                return new Result(false, MessageConstant.HAS_ORDERED, null);
            }
        } else {
            //会员不存在
            TMember tMember = new TMember();
            tMember.setName((String) map.get("name"));
            tMember.setSex((String) map.get("sex"));
            tMember.setPhoneNumber(phone);
            tMember.setIdCard((String) map.get("idCard"));
            tMember.setRegTime(LocalDate.now());

            tMemberMapper.insert(tMember);

            memberId = tMember.getId();
        }

        //保存订单
        TOrder tOrder = new TOrder();
        tOrder.setMemberId(memberId);
        tOrder.setOrderDate(LocalDate.parse(orderDateStr, DateTimeFormatter.ofPattern("yyyy-MM-dd")));
        tOrder.setOrderType("微信公众号");
        tOrder.setOrderStatus("未到诊");
        tOrder.setSetmealId(setmealId);
        tOrderMapper.insert(tOrder);

        //更新已预约人数
        reservations = reservations + 1;
        ordersetting.setReservations(reservations);
        tOrdersettingMapper.updateById(ordersetting);

        return new Result(true, MessageConstant.ORDER_SUCCESS, tOrder.getId());
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false, MessageConstant.ORDER_FAIL, null);
    }
}
```

**业务逻辑复杂 以后写项目主要还是业务层**

##### 预约成功

VO  订单 -- 预约人、预约套餐

```java
@Data
@EqualsAndHashCode(callSuper = true)
public class TOrderVo extends TOrder {
    private TMember member;
    private TSetmeal setmeal;
}
```

Html

```javascript
axios.post("/order/findOrderById?id=" + id).then((res) => {
    this.orderInfo = res.data.obj;
});
```

Controller

```java
//回显
@PostMapping("findOrderById")
public Result findOrderById(int id){
    try{
        TOrderVo vo = orderService.findOrderById(id);
        return new Result(true,MessageConstant.QUERY_ORDER_SUCCESS,vo);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.QUERY_ORDER_FAIL,null);
    }
}
```

ServiceImpl

```java
//主键查询
@Override
public TOrderVo findOrderById(int id) {
    TOrder tOrder = tOrderMapper.selectById(id);
    TOrderVo vo = new TOrderVo();
    BeanUtils.copyProperties(tOrder,vo);

    Integer memberId = tOrder.getMemberId();
    Integer setmealId = tOrder.getSetmealId();

    TMember tMember = tMemberMapper.selectById(memberId);
    vo.setMember(tMember);

    TSetmeal tSetmeal = tSetmealMapper.selectById(setmealId);
    vo.setSetmeal(tSetmeal);

    return vo;
}
```



#### 支付页面

微信、支付宝沙箱环境

https://opendocs.alipay.com/open/200/

### Day32

#### 内容

复杂业务逻辑分步骤 项目分层、简化逻辑。

前台 业务主要是查询显示

健康资讯 留言板功能 

实时聊天 WebSocket

#### 工作量统计

运营数据统计：会员数据统计、预约到诊、热门套餐；导出Excel

Dateutils 工具类

QueryWrapper 查询、原生 Mybatis 也可 limit 限制前几个 

![image-20210817111921639](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210817111921639.png)

Html

```javascript
axios.get("/report/getBusinessReportData").then((res)=>{
    this.reportData = res.data.obj;
});
```

Controller

```java
//统计页面展示 -- 需要相关统计数据
@GetMapping("getBusinessReportData")
@ResponseBody
public Result getBusinessReportData(){
    try{
        Map<String,Object>map = reportService.getBusinessReportData();
        return new Result(true, MessageConstant.GET_BUSINESS_REPORT_SUCCESS,map);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false, MessageConstant.GET_BUSINESS_REPORT_FAIL,null);
    }
}
```

ServiceImpl

```java
public Map<String, Object> getBusinessReportData() throws Exception{
    //当天 reportDate
    String reportDate = DateUtils.parseDate2String(new Date());
    //本周第一天
    String firstDayOfWeek = DateUtils.parseDate2String(DateUtils.getFirstDayOfWeek(new Date()));
    //本月第一天
    String firstDayOfMonth = DateUtils.parseDate2String(DateUtils.getFirstDay4ThisMonth());

    //当天新增会员数 todayNewMember
    QueryWrapper<TMember>wrapper = new QueryWrapper<>();
    wrapper.eq("regTime",reportDate);
    Integer todayNewMember = tMemberMapper.selectCount(wrapper);

    //本周新增会员数 thisWeekNewMember
    int thisWeekNewMember = tMemberMapper.selectCountByWeekOrMonth(firstDayOfWeek);
    //本月新增会员数 thisMonthNewMember
    int thisMonthNewMember = tMemberMapper.selectCountByWeekOrMonth(firstDayOfMonth);

    //总会员数 totalMember
    Integer totalMember = tMemberMapper.selectCount(null);

    //当天预约下单数 todayOrderNumber
    QueryWrapper<TOrder>orderQueryWrapper = new QueryWrapper<>();
    orderQueryWrapper.eq("orderDate",reportDate);
    Integer todayOrderNumber = tOrderMapper.selectCount(orderQueryWrapper);

    //本周预约下单数 thisWeekOrderNumber
    int thisWeekOrderNumber = tOrderMapper.selectCountByWeekOrMonth(firstDayOfWeek);
    //本月预约下单数 thisMonthOrderNumber
    int thisMonthOrderNumber = tOrderMapper.selectCountByWeekOrMonth(firstDayOfMonth);
    //当天到诊人数 todayVisitsNumber
    orderQueryWrapper.eq("orderStatus","已到诊");
    Integer todayVisitsNumber = tOrderMapper.selectCount(orderQueryWrapper);

    //本周到诊人数 thisWeekVisitsNumber
    int thisWeekVisitsNumber = tOrderMapper.selectCountByWeekOrMonthVisits(firstDayOfWeek, "已到诊");
    //本月到诊人数 thisMonthVisitsNumber
    int thisMonthVisitsNumber = tOrderMapper.selectCountByWeekOrMonthVisits(firstDayOfMonth, "已到诊");

    //热门套餐 hotSetmeal[{name,setmeal_count,proportion}]
    List<Map<String, Object>> hotSetmeal = tSetmealMapper.selectHotSetmealList();

    Map<String,Object> map = new HashMap<>();
    map.put("reportDate",reportDate);
    map.put("todayNewMember",todayNewMember);
    map.put("thisWeekNewMember",thisWeekNewMember);
    map.put("thisMonthNewMember",thisMonthNewMember);
    map.put("totalMember",totalMember);
    map.put("todayOrderNumber",todayOrderNumber);
    map.put("thisWeekOrderNumber",thisWeekOrderNumber);
    map.put("thisMonthOrderNumber",thisMonthOrderNumber);
    map.put("todayVisitsNumber",todayVisitsNumber);
    map.put("thisWeekVisitsNumber",thisWeekVisitsNumber);
    map.put("thisMonthVisitsNumber",thisMonthVisitsNumber);
    map.put("hotSetmeal",hotSetmeal);

    return map;
}
```

热门套餐

```xml
<select id="selectHotSetmealList" resultType="map">
    SELECT s.name,te.proportion,te.setmeal_count
    FROM
    (SELECT setmeal_id,COUNT(id) setmeal_count,COUNT(id)/(SELECT COUNT(id) FROM t_order) proportion
    FROM t_order
    GROUP BY setmeal_id
    ORDER BY setmeal_count DESC) te JOIN t_setmeal s
    ON te.setmeal_id = s.id LIMIT 5
</select>
```

**导出 Excel 下载只能是同步下载**

#### POI 导出 Excel 格式设置

**先有一个文件模板 样式弄好，导出时候填写新的值即可（比在程序中好操作）**

Html

```javascript
exportExcel(){
    window.location.href = '/report/exportBusinessReport';
}
```

Controller

```java
//导出Excel操作 -- 使用现成Excel表格文件
@GetMapping("exportBusinessReport")
public void exportBusinessReport(HttpServletResponse response){
    try {
        //准备数据
        Map<String, Object> map = reportService.getBusinessReportData();

        //获取模板文件
        //String path = "E:\\java95\\day32\\code\\offcnpe_parent\\offcnpe_controller\\src\\main\\resources\\static\\template\\report_template.xlsx";
        URL url = this.getClass().getResource("/static/template/report_template.xlsx");
        String path = url.getPath();
        path = path.replaceAll("%20", " ");
        Workbook workbook = new XSSFWorkbook(path);
        //对应单元格填充相关的值
        Sheet sheet = workbook.getSheet("sheet1");
        Row row2 = sheet.getRow(2);
        Cell reportDate = row2.getCell(5);
        reportDate.setCellValue((String) map.get("reportDate"));
        ////////////////////////////
        Row row4 = sheet.getRow(4);
        Cell todayNewMember = row4.getCell(5);
        todayNewMember.setCellValue((Integer) map.get("todayNewMember"));

        Cell totalMember = row4.getCell(7);
        totalMember.setCellValue((Integer) map.get("totalMember"));
        //////////////////
        Row row5 = sheet.getRow(5);
        Cell thisWeekNewMember = row5.getCell(5);
        thisWeekNewMember.setCellValue((Integer) map.get("thisWeekNewMember"));

        Cell thisMonthNewMember = row5.getCell(7);
        thisMonthNewMember.setCellValue((Integer) map.get("thisMonthNewMember"));
        //////////
        Row row7 = sheet.getRow(7);
        Cell todayOrderNumber = row7.getCell(5);
        todayOrderNumber.setCellValue((Integer) map.get("todayOrderNumber"));
        Cell todayVisitsNumber = row7.getCell(7);
        todayVisitsNumber.setCellValue((Integer) map.get("todayVisitsNumber"));

        Row row8 = sheet.getRow(8);
        Cell thisWeekOrderNumber = row8.getCell(5);
        thisWeekOrderNumber.setCellValue((Integer) map.get("thisWeekOrderNumber"));
        Cell thisWeekVisitsNumber = row8.getCell(7);
        thisWeekVisitsNumber.setCellValue((Integer) map.get("thisWeekVisitsNumber"));

        Row row9 = sheet.getRow(9);
        Cell thisMonthOrderNumber = row9.getCell(5);
        thisMonthOrderNumber.setCellValue((Integer) map.get("thisMonthOrderNumber"));
        Cell thisMonthVisitsNumber = row9.getCell(7);
        thisMonthVisitsNumber.setCellValue((Integer) map.get("thisMonthVisitsNumber"));

        //////
        int i = 12;
        List<Map<String, Object>> hotSetmeal = (List<Map<String, Object>>) map.get("hotSetmeal");
        for(Map<String,Object>hot : hotSetmeal){
            Row rowi = sheet.getRow(i);
            Cell name = rowi.getCell(4);
            name.setCellValue((String) hot.get("name"));
            Cell count = rowi.getCell(5);
            count.setCellValue((Long) hot.get("setmeal_count"));
            Cell pro = rowi.getCell(6);
            pro.setCellValue(((BigDecimal) hot.get("proportion")).toString());

            i++;
        }
        //把文件传输/下载到用户端
        OutputStream os = response.getOutputStream();
        response.setContentType("application/vnd.ms-excel");//代表的是Excel文件类型
        response.setHeader("content-Disposition", "attachment;filename=report.xlsx");//指定以附件形式进行下载
        workbook.write(os);
        //释放资源
        os.flush();
        os.close();
        workbook.close();
    }catch (Exception e){
        e.printStackTrace();
    }
}
```

### Day33

#### 内容

多思考

#### ECharts

ECharts是一款基于[JavaScript](https://baike.baidu.com/item/JavaScript/321142)的[数据可视化](https://baike.baidu.com/item/数据可视化/1252367)图表库，提供**直观，生动，可交互，可个性化定制**的数据可视化图表。ECharts最初由[百度](https://baike.baidu.com/item/百度/6699)团队开源，并于2018年初捐赠给[Apache](https://baike.baidu.com/item/Apache/6265)基金会，成为ASF孵化级项目。 [1] 

2021年1月26日晚，Apache基金会官方宣布ECharts项目正式毕业。1月28日，ECharts 5线上发布会举行。

> 使用

+ 引入 echarts.min.js 文件

+ 设置 div 容器

+ 初始化 ECharts 设置数据

> Demo

折线图

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>echarts测试</title>
    <script type="text/javascript" src="../js/echarts.js"></script>
</head>
<body>
<div id="main" style="width:600px;height:400px"></div>
<script type="text/javascript">
    //初始化
    var myecharts = echarts.init(document.getElementById("main"));
    //设置数据
    var options = {
        title: {
            text: 'ECharts 入门示例'
        },
        tooltip: {},
        legend: {
            data:['销量']
        },
        xAxis: {
            data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
        },
        yAxis: {},
        series: [{
            name: '销量',
            type: 'line',
            data: [5, 20, 36, 10, 10, 20]
        }]
    };
    //设置
    myecharts.setOption(options);
</script>
</body>
</html>
```

南丁格尔图

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>测试</title>
    <script type="text/javascript" src="../js/echarts.js"></script>
</head>
<body>
<div id="main" style="width:600px;height:400px"></div>
<script type="text/javascript">
    //初始化
    var myecharts = echarts.init(document.getElementById("main"));
    //设置数据
    var options = {
        backgroundColor: '#2c343c',
        series : [
            {
                name: '访问来源',
                type: 'pie',
                radius: '55%',
                roseType: 'angle',
                data:[
                    {value:235, name:'视频广告'},
                    {value:274, name:'联盟广告'},
                    {value:310, name:'邮件营销'},
                    {value:335, name:'直接访问'},
                    {value:400, name:'搜索引擎'}
                ],
                labelLine: {
                    lineStyle: {
                        color: 'rgba(255, 255, 255, 0.3)'
                    }
                }
            }
        ]
    };
    //设置
    myecharts.setOption(options);
</script>
</body>
</html>
```

#### 会员统计

echarts

```javascript
axios.get("/report/getMemberReport").then((res)=>{
    myChart1.setOption(
        {
            title: {
                text: '会员数量'
            },
            tooltip: {},
            legend: {
                data:['会员数量']
            },
            xAxis: {
                data: res.data.obj.months
            },
            yAxis: {
                type:'value'
            },
            series: [{
                name: '会员数量',
                type: 'line',
                data: res.data.obj.memberCount
            }]
        });
});
```

xml 格式 

第一种方法：
用转义字符把">"和"<"替换掉，就没有问题了。

```
附：XML转义字符

&lt;     	<   	小于号   
&gt;     	>   	大于号   
&amp;     	&   	和   
&apos;     	’   	单引号   
&quot;     	"   	双引号   
```

第二种方法：
因为这个是xml格式的，所以不允许出现类似">"这样的字符

```
<![CDATA[ ]]>符号进行说明，将此类符号不进行解析 

<![CDATA[ 这里写你的sql ]]>  
```

```xml
<!--统计会员数量：从指定日期向前统计-->
<select id="selectCountByMonth" parameterType="string" resultType="int">
    <![CDATA[
        SELECT COUNT(*) FROM t_member WHERE regTime <= #{value}
    ]]>
</select>
```

Controller

```java
//统计会员数量
@GetMapping("getMemberReport")
@ResponseBody
public Result getMemberReport(){
    try{
        Map<String,Object>map = reportService.getMemberReport();
        return new Result(true,MessageConstant.GET_MEMBER_NUMBER_REPORT_SUCCESS,map);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.GET_MEMBER_NUMBER_REPORT_FAIL,null);
    }
}
```

ServiceImpl

```java
//准备会员数量的相关数据
@Override
public Map<String, Object> getMemberReport() {
    Map<String,Object>map = new HashMap<>();
    //获取到当前系统时间，获取到月份，从当前月份，向前推12个月，找这12个月的月份作为x轴数组数据
    //获取当前系统时间
    Calendar calendar = Calendar.getInstance();
    calendar.add(Calendar.MONTH,-12);
    String[]months = new String[12];
    for(int i = 0;i < 12;i++){
        calendar.add(Calendar.MONTH,1);
        Date date = calendar.getTime();
        SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy.MM");
        String month = simpleDateFormat.format(date);
        months[i] = month;
    }
    map.put("months",months);

    //统计每个月的会员数量
    int[]memberCount = new int[12];
    for(int i = 0;i < 12;i++){
        String month = months[i];
        String day = month + ".31";//2021.8.31
        int count = tMemberMapper.selectCountByMonth(day);
        memberCount[i] = count;
    }
    map.put("memberCount",memberCount);

    return map;
}
```

#### 套餐统计

echarts

```html
axios.get("/report/getSetmealReport").then((res)=>{
            myChart1.setOption({
                title : {
                    text: '套餐预约占比',
                    subtext: '',
                    x:'center'
                },
                tooltip : {//提示框组件
                    trigger: 'item',//触发类型，在饼形图中为item
                    formatter: "{a} <br/>{b} : {c} ({d}%)"//提示内容格式
                },
                legend: {
                    orient: 'vertical',
                    left: 'left',
                    data: res.data.obj.setmealNames
                },
                series : [
                    {
                        name: '套餐预约占比',
                        type: 'pie',
                        radius : '55%',
                        center: ['50%', '60%'],
                        data:res.data.obj.setmealCount,
                        itemStyle: {
                            emphasis: {
                                shadowBlur: 10,
                                shadowOffsetX: 0,
                                shadowColor: 'rgba(0, 0, 0, 0.5)'
                            }
                        }
                    }
                ]
            });
});
```

Controller

```java
//统计套餐占比
@GetMapping("getSetmealReport")
@ResponseBody
public Result getSetmealReport(){
    try {
        Map<String,Object>map = reportService.getSetmealReport();
        return new Result(true,MessageConstant.GET_SETMEAL_COUNT_REPORT_SUCCESS,map);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,MessageConstant.GET_SETMEAL_COUNT_REPORT_FAIL,null);
    }
}
```

ServiceImpl

```java
//获取套餐名称和套餐的预约下单数量
@Override
public Map<String, Object> getSetmealReport() {
    Map<String,Object>reportMap = new HashMap<>();

    List<Map<String,Object>> list = tSetmealMapper.selectSetmealReport();

    //{name:xxx,value:xxx}
    List<String>names = new ArrayList<>();
    for(Map<String,Object> map : list){
        String name = (String) map.get("name");
        names.add(name);
    }

    reportMap.put("setmealNames",names);
    reportMap.put("setmealCount",list);

    return reportMap;
}
```

SQL

```xml
<!--套餐统计占比-->
<select id="selectSetmealReport" resultType="map">
    SELECT s.name,te.value
    FROM t_setmeal s
    JOIN (SELECT setmeal_id,COUNT(id) VALUE FROM t_order GROUP BY setmeal_id) te
    ON s.id = te.setmeal_id
</select>
```

#### 健康咨询

pojo

```java
@Data
@EqualsAndHashCode(callSuper = true)
@Accessors(chain = true)
@TableName("t_zixun")
public class Zixun extends Model {

    private static final long serialVersionUID=1L;

    @TableId(value = "id",type = IdType.AUTO)
    private Integer id;
    private String content;
    private LocalDate zdate;
    @TableField("member_id")
    private Integer memberId;
}
```

```java
@Data
@EqualsAndHashCode(callSuper = true)
@Accessors(chain = true)
@ToString
@TableName("t_replay")
public class Replay extends Model {
    private static final long serialVersionUID=1L;

    @TableId(value = "id",type = IdType.AUTO)
    private Integer id;
    private String content;
    private LocalDate rdate;
    @TableField("member_id")
    private Integer memberId;
    @TableField("user_id")
    private Integer userId;
    @TableField("z_fk")
    private String zFk;
}
```

##### 咨询

table zixun

```sql
CREATE TABLE t_zixun (
  id INT PRIMARY KEY AUTO_INCREMENT,
  content VARCHAR(300),
  zdate DATETIME,
  member_id INT
);
```

Html

```javascript
//提交预约
submitZixun(){
    axios.post('../zixun/add',this.info).then((res) => {
        if(res.data.flag){
            this.$message({
                type:'success',
                message:res.data.message
            });
            location.href = "index.html";
        }else{
            this.$message.error(res.data.message);
        }
    });
}
```

Controller

```java
//添加
@PostMapping("add")
public Result add(@RequestBody Map<String,Object>map){
    try{
        zixunService.add(map);
        return new Result(true, MessageConstant.ADD_ZIXUN_SUCCESS,null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false, MessageConstant.ADD_ZIXUN_FAIL,null);
    }
}
```

ServiceImpl

```java
@Override
@Transactional
public void add(Map<String, Object> map) {
    String telephone = (String) map.get("telephone");
    QueryWrapper<TMember>wrapper = new QueryWrapper<>();
    wrapper.eq("phoneNumber",telephone);
    TMember tMember = tMemberMapper.selectOne(wrapper);
    Integer mid = null;
    if(tMember != null){
        mid = tMember.getId();
    }else{
        TMember tMember1 = new TMember();
        tMember1.setRegTime(LocalDate.now());
        tMember1.setPhoneNumber(telephone);
        tMember1.setName((String) map.get("name"));
        tMember1.setSex((String) map.get("sex"));
        tMember1.setIdCard((String) map.get("idCard"));

        tMemberMapper.insert(tMember1);

        mid = tMember1.getId();
    }

    Zixun zixun = new Zixun();
    zixun.setMemberId(mid);
    zixun.setContent((String) map.get("content"));
    zixun.setZdate(LocalDate.now());
    zixunDao.insert(zixun);
}
```

ZixunDao

```java
public interface ZixunDao extends BaseMapper<Zixun> {

}
```

##### 回复

table replay

```sql
CREATE TABLE t_replay (
  id INT PRIMARY KEY AUTO_INCREMENT,
  content VARCHAR(100),
  rdate DATETIME,
  member_id INT,
  user_id INT,
  z_fk INT
)
```

Html

```javascript
//分页查询
findPage() {
    axios.post('../zixun/findPage',this.pagination).then((res) => {
        if(res.data.flag){
            this.pagination.total = res.data.obj.total;
            this.dataList = res.data.obj.list;
        }else{
            this.$message.error(res.data.message);
        }
    });
}
```

Controller

```java
@PostMapping("findPage")
public Result findPage(@RequestBody QueryPageBean pageBean){
    try{
        PageResult pageResult = zixunService.findPage(pageBean);
        return new Result(true,"查询咨询成功",pageResult);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,"查询咨询失败",null);
    }
}
```

ServiceImpl

```java
//查询咨询列表以及咨询人名称
@Override
public PageResult findPage(QueryPageBean pageBean) {
    Page<Zixun>page = new Page<>(pageBean.getCurrentPage(),pageBean.getPageSize());
    QueryWrapper<Zixun>wrapper = new QueryWrapper<>();
    if(StringUtils.isNotEmpty(pageBean.getQueryString())){
        wrapper.like("content",pageBean.getQueryString());
    }
    Page<Zixun> zixunPage = zixunDao.selectPage(page, wrapper);

    //需要咨询人的名称
    List<Map<String,Object>> list = new ArrayList<>();
    for(Zixun zixun : zixunPage.getRecords()){
        Integer memberId = zixun.getMemberId();
        TMember tMember = tMemberMapper.selectById(memberId);
        String name = tMember.getName();
        Map<String,Object>map = new HashMap<>();
        map.put("id",zixun.getId());
        map.put("content",zixun.getContent());
        map.put("zdate",zixun.getZdate());
        map.put("name",name);
        list.add(map);
    }

    PageResult pageResult = new PageResult(zixunPage.getTotal(),list);

    return pageResult;
}
```

Html

```html
// 弹出回复窗口
handleCreate(row) {
    //alert(row.id)
    this.formData.zFk = row.id;
    this.dialogFormVisible = true;
}
//添加
handleAdd () {
	axios.post('../replay/add?zFk='+this.formData.zFk,this.formData).then((res) => {
		if(res.data.flag){
			this.$message({
        	type:'success',
			message:res.data.message
		})
		this.dialogFormVisible = false;
		this.findPage();
		}else{
			this.$message.error(res.data.message);
		}
	});
}
```

Controller

```java
@PostMapping("add")
public Result add(String zFk,@RequestBody Replay replay){
    try {
        //System.out.println(zFk);
        //System.out.println(replay.getContent());
        replay.setZFk(zFk);
        replay.setRdate(LocalDate.now());
        replay.setUserId(1);//TODO 没有解决的问题，获取登录用户的id

        replayService.add(replay);
        return new Result(true,"回复成功",null);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,"回复失败",null);
    }
}
```

ServiceImpl

```java
@Override
public void add(Replay replay) {
    replayDao.insert(replay);
}
```



TODO 没有解决的问题，获取登录用户的id

在Project 中可以找到 TODO Idea 小技巧

### Day34

#### Spring Security 

安全认证框架

Spring Security 是一个功能强大且高度可定制的**身份验证**和**访问控制**框架。它是保护基于 Spring 的应用程序的事实上的标准。

Spring Security 是一个专注于为 Java 应用程序提供身份验证和授权的框架。与所有 Spring 项目一样，Spring Security 的真正强大之处在于它可以轻松扩展以满足自定义要求

**特征**

- 对身份验证和授权的全面且可扩展的支持
- 防止会话固定、点击劫持、跨站点请求伪造等攻击（防止恶意攻击，黑客拦截）
- Servlet API 集成
- 与 Spring Web MVC 的可选集成
- 多得多…

```
作为权限管理框架，其内部机制可分为两大部分，其一是认证授权authorization，其二是权限校验authentication。
认证授权authorization是指，根据用户提供的身份凭证，生成权限实体，并为之授予相应的权限。
权限校验authentication是指，用户请求访问被保护资源时，将被保护资源所需的权限和用户权限实体所拥护的权限二者进行比对，如果校验通过则用户可以访问被保护资源，否则拒绝访问。
```

认证授权、权限校验（身份验证）

```
Spring Security 简介
Spring 是一个非常流行和成功的 Java 应用开发框架。Spring Security 基于 Spring 框架，提供了一套 Web 应用安全性的完整解决方案。一般来说，Web 应用的安全性包括用户认证（Authentication）和用户授权（Authorization）两个部分。用户认证指的是验证某个用户是否为系统中的合法主体，也就是说用户能否访问该系统。用户认证一般要求用户提供用户名和密码。系统通过校验用户名和密码来完成认证过程。用户授权指的是验证某个用户是否有权限执行某个操作。在一个系统中，不同用户所具有的权限是不同的。比如对一个文件来说，有的用户只能进行读取，而有的用户可以进行修改。一般来说，系统会为不同的用户分配不同的角色，而每个角色则对应一系列的权限。
```

其他：oauth 单点登录

**依赖**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.4.9</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>com.offcn</groupId>
    <artifactId>security-demo</artifactId>
    <version>1.0-SNAPSHOT</version>

    <dependencies>
        <!--web启动器-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <!--security启动器-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-security</artifactId>
        </dependency>
        <!--lombok-->
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
        </dependency>
        <!--开发工具-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-devtools</artifactId>
            <scope>runtime</scope>
            <optional>true</optional>
        </dependency>
        <!--mybatisplus-->
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>mybatis-plus-boot-starter</artifactId>
            <version>3.4.2</version>
        </dependency>
        <!--数据库驱动-->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>5.1.49</version>
        </dependency>
        <!--连接池-->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
            <version>1.1.20</version>
        </dependency>
        <!--json转换-->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>fastjson</artifactId>
            <version>1.2.68</version>
        </dependency>
        <dependency>
            <groupId>org.apache.velocity</groupId>
            <artifactId>velocity-engine-core</artifactId>
            <version>2.0</version>
        </dependency>
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>mybatis-plus-generator</artifactId>
            <version>3.4.1</version>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <!--防止在部署时，映射文件.xml文件不能部署-->
    <build>
        <resources>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.xml</include>
                </includes>
                <filtering>false</filtering>
            </resource>
        </resources>
    </build>
</project>
```

权限设计 五张表 用户、角色、权限、用户角色、角色权限 资源和权限

![image-20210819165818250](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210819165818250.png)

通过 URL 做 数据操作

![image-20210819101616180](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210819101616180.png)

**项目可以分模块 classpath* 读其他模块的配置文件**

mybatis 配置

**逆向生成**

```java
package com.offcn.test;

import com.baomidou.mybatisplus.generator.AutoGenerator;
import com.baomidou.mybatisplus.generator.config.*;
import com.baomidou.mybatisplus.generator.config.rules.NamingStrategy;

public class GeneratorTest {
    public static void main(String[] args) {
        // 代码生成器
        AutoGenerator mpg = new AutoGenerator();
        // 全局配置
        GlobalConfig gc = new GlobalConfig();

        gc.setOutputDir("D:\\bh linfo\\IdeaProjects\\day34\\security-demo\\src\\main\\java");
        gc.setAuthor("zs");
        gc.setOpen(false);
        //实体属性 Swagger2 注解
        //gc.setSwagger2(false);
        mpg.setGlobalConfig(gc);

        // 数据源配置
        DataSourceConfig dsc = new DataSourceConfig();

        dsc.setUrl("jdbc:mysql:///securitydemo?characterEncoding=utf8");
        dsc.setDriverName("com.mysql.jdbc.Driver");
        dsc.setUsername("root");
        dsc.setPassword("admin");
        mpg.setDataSource(dsc);

        // 包配置
        PackageConfig pc = new PackageConfig();
        pc.setParent("com.offcn");
        pc.setEntity("pojo");
        pc.setMapper("dao");
        pc.setController("controller");
        mpg.setPackageInfo(pc);

        // 配置模板
        TemplateConfig templateConfig = new TemplateConfig();
        //默认关闭不需要的生成内容
        templateConfig.setXml(null);
        templateConfig.setService(null);
        templateConfig.setServiceImpl(null);
        mpg.setTemplate(templateConfig);

        // 策略配置
        StrategyConfig strategy = new StrategyConfig();
        strategy.setNaming(NamingStrategy.underline_to_camel);
        strategy.setColumnNaming(NamingStrategy.underline_to_camel);
        strategy.setSuperEntityClass("com.baomidou.mybatisplus.extension.activerecord.Model");
        strategy.setEntityLombokModel(true);
        strategy.setRestControllerStyle(true);

        String  tableNames="sys_role,sys_role_menu,sys_menu,sys_user,sys_user_role";
        strategy.setInclude(tableNames.split(","));
        strategy.setControllerMappingHyphenStyle(true);
        strategy.setTablePrefix("t_");
        mpg.setStrategy(strategy);
        mpg.execute();
    }
}

```

**配置文件**

```yaml
#端口、应用名称
server:
  port: 8003

#数据源
spring:
  application:
    name: security-demo
  datasource:
    driver-class-name: com.mysql.jdbc.Driver
    url: jdbc:mysql:///securitydemo?characterEncoding=utf8
    username: root
    password: admin
  devtools:
    restart:
      enabled: true
      additional-paths: src/main/java
  jackson:
    date-format: yyyy-MM-dd HH:mm:ss
    time-zone: GMT+8

#mybatis-plus
mybatis-plus:
  type-aliases-package: com.offcn.pojo
  mapper-locations: classpath:/mappers/*.xml
  configuration:
    log-impl: org.apache.ibatis.logging.stdout.StdOutImpl  
```

##### login

name=username 名称固定

name=password 名称固定

action=/login 名称固定

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>登录页面</title>
</head>
<body>
<!--action名称固定-->
<form method="post" action="/login">
    <!--name=username名称固定-->
    <p>用户名：<input name="username"></p>
    <!--name=password名称固定-->
    <p>密码：<input type="password" name="password"></p>
    <p><input type="submit" value="提交"></p>
</form>
</body>
</html>
```

##### index

a href

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>首页</title>
</head>
<body>
<a href="user/list">查询</a>
<hr>
<a href="user/add">增加</a>
<hr>
<a href="user/update">修改</a>
<hr>
<a href="user/delete">删除</a>
<hr>
<a href="/logout">退出登录</a>
</body>
</html>
```

Controller

@Secured("ROLE_user")  验证角色

@PreAuthorize("hasAuthority('user:add')") 验证权限

```java
@RestController
@RequestMapping("user")
public class SysUserController {

    //添加角色校验的注解 -- 即当使用者用户在页面中点击对应的连接的时候，验证当前登录用户是否存在指定的角色
    //@Secured("ROLE_user")
    @GetMapping("list")
    public ResultData list(){
        return ResultData.ok();
    }

    //添加权限校验的注解 -- 即当使用者用户在页面中点击对应的连接的时候，验证当前登录用户是否存在指定的权限
    @PreAuthorize("hasAuthority('user:add')")
    @GetMapping("add")
    public ResultData add(){
        return ResultData.ok();
    }

    @GetMapping("update")
    public ResultData update(){
        return ResultData.ok();
    }

    @GetMapping("delete")
    public ResultData delete(){
        return ResultData.ok();
    }
}
```

##### 配置

密文 把原始密码通过加密算法计算得出结果（md5、Password、Bcrypt）

Rounds 增加盐值 破解更麻烦

 一般不可逆（彩虹表暴力破解 穷举）

访问什么资源都需要先登录、验证权限（底层：Session）

本身提供了登录页面

**SecurityConfig**

```java
//允许security读取相关配置
@EnableWebSecurity
//允许在controller层的方法上面添加security框架相关的注解
@EnableGlobalMethodSecurity(prePostEnabled = true, securedEnabled = true)
public class SecurityConfig extends WebSecurityConfigurerAdapter {
    //bean -- spring容器管理的对象
    @Resource
    private CustomUserDetailService userDetailService;
    @Resource
    private AuthenticationFailureHandler authenticationFailureHandler;
    @Resource
    private AuthenticationEntryPoint authenticationEntryPoint;
    @Resource
    private AccessDeniedHandler accessDeniedHandler;
    //加密对象
    @Bean
    public BCryptPasswordEncoder getPasswordEncoder(){
        BCryptPasswordEncoder passwordEncoder = new BCryptPasswordEncoder();
        return passwordEncoder;
    }

    //认证器对象-配置
    @Override
    public void configure(AuthenticationManagerBuilder auth) throws Exception {
        //捆绑两个对象 -- 底层实现返回来的数据库中的密文和前端页面输入的原始密码被加密之后形参的密文，两者对比
        auth.userDetailsService(userDetailService).passwordEncoder(getPasswordEncoder());
    }

    //全局配置
    @Override
    public void configure(HttpSecurity http) throws Exception {
        //跨站请求伪造
        http.csrf().disable()//关闭跨站请求伪造
        //指定登录页面是谁、指定登录成功之后跳转的页面是谁
        .formLogin()//使用表单登录实现认证
        .loginPage("/login.html")//登录页面是哪个
        .loginProcessingUrl("/login")//登录连接是哪个
        .defaultSuccessUrl("/index.html")//登录成功跳转页面
        .permitAll()
        .failureHandler(authenticationFailureHandler)//登录失败如何处理
        .and()//添加其他配置
        .authorizeRequests()//请求需要认证
        //哪些资源不需要登录可以直接访问
        .antMatchers("/login.html","/login").permitAll()//代表哪些页面或者url不需要登录可以直接访问
        .antMatchers("/js/**","/css/**","/img/**","/favicon.ico").permitAll()//代表静态资源不需要登录可以直接访问
        .anyRequest()//代表当前项目任何请求都要到此处
        .authenticated();//代表需要认证

        //发生异常时如何处理
        http.exceptionHandling().authenticationEntryPoint(authenticationEntryPoint).accessDeniedHandler(accessDeniedHandler);

        //登出 -- 退出登录的配置
        http.logout().logoutUrl("/logout").logoutSuccessUrl("/login.html");
    }
}
```

提示用户名或者密码有误 一般提示不会特别明确 防止别有用心的人

CustomUserDetailService 只匹配用户名 密文密码捆绑送回，认证器对象对照密码

**CustomUserDetailService** 

```java
@Component
public class CustomUserDetailService implements UserDetailsService {

    @Autowired
    private SysUserMapper sysUserMapper;
    @Autowired
    private SysRoleMapper sysRoleMapper;
    @Autowired
    private SysMenuMapper sysMenuMapper;

    //认证操作 -- 做登录(验证)和授权
    @Override
    public UserDetails loadUserByUsername(String username) throws UsernameNotFoundException {
        //通过实参获取到了从登录页面送来的用户名
        //到用户表中根据用户名查找用户信息 -- 可能查到、可能没有查到
        QueryWrapper<SysUser>wrapper = new QueryWrapper<>();
        wrapper.eq("user_name",username);
        SysUser sysUser = sysUserMapper.selectOne(wrapper);
        //没有查找认证失败 -- 要么返回到登录页面、要么去到提示页面
        if(sysUser == null){
            System.out.println("************");
            throw new UsernameNotFoundException("用户名或者密码有误");
        }
        //如果查到认证成功
        Integer userId = sysUser.getId();
        //授权 -- 给当前用户绑定角色、绑定权限、绑定资源
        List<GrantedAuthority> list = new ArrayList<>();
        List<SysRole> roleList = sysRoleMapper.selectRoleByUserID(userId);
        for(SysRole sysRole : roleList){
            String roleCode = sysRole.getRoleCode();//admin
            SimpleGrantedAuthority authority = new SimpleGrantedAuthority("ROLE_" + roleCode);
            list.add(authority);
        }
        List<SysMenu> menuList = sysMenuMapper.selectMenuByUserID(userId);
        for(SysMenu sysMenu : menuList){
            String perms = sysMenu.getPerms();
            SimpleGrantedAuthority authority = new SimpleGrantedAuthority(perms);
            list.add(authority);
        }
        //返回登录用户信息 -- 包含用户信息、角色、权限、资源 -- 用户信息也会保存到session
        return new User(username,sysUser.getPassword(),list);
    }
}
```

```java
@Component
public class AccessDeniedHandlerImpl implements AccessDeniedHandler {
    @Override
    public void handle(HttpServletRequest request, HttpServletResponse response, AccessDeniedException e) throws IOException, ServletException {
        response.setContentType("application/json;charset=UTF-8");
        PrintWriter writer = response.getWriter();
        writer.write(JSON.toJSONString(ResultData.error()));
    }
}
///////////////////////
@Component
public class AuthenticationEntryPointImpl implements AuthenticationEntryPoint {
    @Override
    public void commence(HttpServletRequest request, HttpServletResponse response, AuthenticationException e) throws IOException, ServletException {
        response.setContentType("application/json;charset=UTF-8");
        PrintWriter writer = response.getWriter();
        writer.write(JSON.toJSONString(ResultData.error()));
    }
}
///////////////////////
@Component
public class AuthenticationFailureHandlerImpl implements AuthenticationFailureHandler {
    //登录失败如何操作
    @Override
    public void onAuthenticationFailure(HttpServletRequest request, HttpServletResponse response, AuthenticationException e) throws IOException, ServletException {
        response.setContentType("application/json;charset=UTF-8");
        PrintWriter writer = response.getWriter();
        writer.write(JSON.toJSONString(ResultData.error()));
    }
}
```

### Day35

#### Spring Security 

基于 AOP 思想 在执行 Controller 之前切入，查询存入的 list 角色/资源是否有权限

#### 后台系统添加 权限验证

**FrameSet 排版 安全框架默认不支持 设置开关**

`http.csrf().disable().headers().frameOptions().sameOrigin();`

**远程注入有延迟 导致第一次验证不成功**

**Refrence 和 Service 都可以加 timeout 超时时间**

**SecurityConfig**

```java
@EnableWebSecurity
@EnableGlobalMethodSecurity(prePostEnabled = true, securedEnabled = true)
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    @Resource
    private UserDetailsService userDetailsService;
    @Resource
    private AuthenticationFailureHandler authenticationFailureHandler;
    @Resource
    private AuthenticationEntryPoint authenticationEntryPoint;
    @Resource
    private AccessDeniedHandler accessDeniedHandler;

    //加密对象
    @Bean
    public BCryptPasswordEncoder getEncoder(){
        return new BCryptPasswordEncoder();
    }

    //重写的config

    @Override
    protected void configure(AuthenticationManagerBuilder auth) throws Exception {
        auth.userDetailsService(userDetailsService).passwordEncoder(getEncoder());
    }

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http.csrf().disable().headers().frameOptions().sameOrigin();
        //跨站请求伪造
        http.csrf().disable()//关闭跨站请求伪造
                //指定登录页面是谁、指定登录成功之后跳转的页面是谁
                .formLogin()//使用表单登录实现认证
                .loginPage("/index.html")//登录页面是哪个
                .loginProcessingUrl("/login")//登录连接是哪个
                .defaultSuccessUrl("/pages/main.html")//登录成功跳转页面
                .permitAll()
                .failureHandler(authenticationFailureHandler)//登录失败如何处理
                .and()//添加其他配置
                .authorizeRequests()//请求需要认证
                //哪些资源不需要登录可以直接访问
                .antMatchers("/index.html","/login").permitAll()//代表哪些页面或者url不需要登录可以直接访问
                .antMatchers("/js/**","/css/**","/img/**","/plugins/**","/template/**","/loginstyle/**","/zTree_v3-master/**","/favicon.ico").permitAll()//代表静态资源不需要登录可以直接访问
                .anyRequest()//代表当前项目任何请求都要到此处
                .authenticated();//代表需要认证

        //发生异常时如何处理
        http.exceptionHandling().authenticationEntryPoint(authenticationEntryPoint).accessDeniedHandler(accessDeniedHandler);

        //登出 -- 退出登录的配置
        http.logout().logoutUrl("/logout").logoutSuccessUrl("/index.html");
    }
}
```

**UserDetailsServiceImpl**

```java
@Component
public class UserDetailsServiceImpl implements UserDetailsService {

    @Reference(timeout = 30000)
    private TUserService tUserService;
    @Reference(timeout = 30000)
    private TRoleService tRoleService;
    @Reference(timeout = 30000)
    private TPermissionService tPermissionService;

    @Override
    public UserDetails loadUserByUsername(String username) throws UsernameNotFoundException {
        TUser user = tUserService.findUserByUsername(username);
        if(user == null){
            throw new UsernameNotFoundException("用户名或者密码有误");
        }
        List<GrantedAuthority>list = new ArrayList<>();
        Integer userId = user.getId();
        List<TRole> roleList = tRoleService.findRoleByUserID(userId);
        for(TRole tRole : roleList){
            String keyword = tRole.getKeyword();
            list.add(new SimpleGrantedAuthority(keyword));
        }
        List<TPermission>permissionList = tPermissionService.findPermissionByUserID(userId);
        for(TPermission tPermission : permissionList){
            String keyword = tPermission.getKeyword();
            list.add(new SimpleGrantedAuthority(keyword));
        }
        return new User(username,user.getPassword(),list);
    }
}
```

**角色和权限验证**

@Secured({"ROLE_user",......})  验证角色

@PreAuthorize("hasAuthority('权限字符串)") 验证权限

#### 项目中的登出和用户名

**退出**

```html
<a href="/logout">退出</a>
```

通过之前配之类的配置给定 url 即可

```java
//登出 -- 退出登录的配置
        http.logout().logoutUrl("/logout").logoutSuccessUrl("/index.html");
```

**用户名**

页面设置异步函数

```javasc
findUsername(){    
    axios.get('../user/findUsername').then((res) => {
        if(res.data.flag){
            this.username = res.data.obj;
        }
    });
}   
```

Controller

框架保存着用户名 拿出 即可

```java
//获取登录用户名
@GetMapping("findUsername")
public Result findUsername(){
    try{
        String username = SecurityContextHolder.getContext().getAuthentication().getName();
        return new Result(true,"获取用户名成功",username);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,"获取用户名失败",null);
    }
}
```

#### 项目的动态菜单

项目的导航列表

表

![image-20210820230831701](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210820230831701.png)

页面结构 如下 包含 children

```html
menuList:[
    {
        "path": "1",
        "title": "工作列表",
        "icon":"fa-dashboard",
        "children": []
    },
    {
        "path": "2",
        "title": "会员管理",
        "icon":"fa-user-md",
        "children": [
        {
            "path": "/2-1",
            "title": "会员档案管理",
            "linkUrl":"member.html",
            "children":[]
        },
        {
            "path": "/2-2",
            "title": "体检资料上传",
            "children":[]
        },
        {
            "path": "/2-3",
            "title": "会员信息统计",
            "linkUrl":"report_business.html",
            "children":[]
        },
        ]
	}
]
```

pojo

```java
@Data
@EqualsAndHashCode(callSuper = true)
@Accessors(chain = true)
public class TMenu extends Model {

    private static final long serialVersionUID=1L;

    @TableId(value = "id", type = IdType.AUTO)
    private Integer id;

    @TableField("name")
    private String title;

    @TableField("linkUrl")
    private String linkUrl;

    private String path;

    private Integer priority;

    private String icon;

    private String description;

    @TableField("parentMenuId")
    private Integer parentMenuId;

    private Integer level;

    @TableField(exist = false)
    private List<TMenu> children;
}
```

页面设置异步函数

```javascript
findMenu(){
    axios.get('../user/findMenu').then((res) => {
        if(res.data.flag){
            this.menuList = res.data.obj;
            console.log(this.menuList)
        }
    });
}
```

Controller

```java
//获取导航列表
@GetMapping("findMenu")
public Result findMenu(){
    try {
        String name = SecurityContextHolder.getContext().getAuthentication().getName();
        List<TMenu>list = tMenuService.findMenuByUsername(name);
        return new Result(true,"获取菜单成功",list);
    }catch (Exception e){
        e.printStackTrace();
        return new Result(false,"获取菜单失败",null);
    }
}
```

ServiceImpl

```java
public List<TMenu> findMenuByUsername(String name) {
    QueryWrapper<TUser>wrapper = new QueryWrapper<>();
    wrapper.eq("username",name);
    TUser user = tUserMapper.selectOne(wrapper);
    Integer userId = user.getId();
    //一级菜单 -- 暂时没有二级
    List<TMenu> list = tMenuMapper.selectMenuByUserID(userId);

    //实参进去时没有下级，返回时有了下级
    list = change(list);

    return list;
}

private List<TMenu> change(List<TMenu> list) {
    if(list != null && list.size() > 0){
        for(TMenu menu : list){
            Integer menuId = menu.getId();//上级菜单的id
            QueryWrapper<TMenu>wrapper = new QueryWrapper<>();
            wrapper.eq("parentMenuId",menuId);
            //下级菜单集合
            List<TMenu> menuList = tMenuMapper.selectList(wrapper);
            //递归 -- 方法自己调用自己
            //menuList = change(menuList);
            menu.setChildren(menuList);
        }
    }
    return list;
}
```

Mapper

```xml
<!--按照用户id查询菜单-->
<select id="selectMenuByUserID" parameterType="int" resultType="TMenu">
    SELECT id,name title,linkUrl,path,priority,icon,description,parentMenuId,level
    FROM t_menu WHERE id IN(
    SELECT menu_id FROM t_role_menu WHERE role_id IN(
    SELECT role_id FROM t_user_role WHERE user_id = #{value})) AND parentMenuId IS NULL
</select>
```

#### zTree 前端框架

树结构菜单

http://www.treejs.cn/v3/main.php#_zTreeInfo

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>树结构</title>
    <link rel="stylesheet" type="text/css" href="../zTree_v3-master/css/demo.css">
    <link rel="stylesheet" type="text/css" href="../zTree_v3-master/css/zTreeStyle/zTreeStyle.css">
    <script type="text/javascript" src="../zTree_v3-master/js/jquery-1.4.4.min.js"></script>
    <script type="text/javascript" src="../zTree_v3-master/js/jquery.ztree.all.js"></script>
</head>
<body>
<div class="zTreeDemoBackground left">
    <ul id="treeDemo" class="ztree"></ul>
</div>
<script type="text/javascript">
    /*var setting = {	};

    var zNodes =[
        { name:"父节点1 - 展开", open:true,
            children: [
                { name:"父节点11 - 折叠",
                    children: [
                        { name:"叶子节点111"},
                        { name:"叶子节点112"},
                        { name:"叶子节点113"},
                        { name:"叶子节点114"}
                    ]},
                { name:"父节点12 - 折叠",
                    children: [
                        { name:"叶子节点121"},
                        { name:"叶子节点122"},
                        { name:"叶子节点123"},
                        { name:"叶子节点124"}
                    ]},
                { name:"父节点13 - 没有子节点", isParent:true}
            ]},
        { name:"父节点2 - 折叠",
            children: [
                { name:"父节点21 - 展开", open:true,
                    children: [
                        { name:"叶子节点211"},
                        { name:"叶子节点212"},
                        { name:"叶子节点213"},
                        { name:"叶子节点214"}
                    ]},
                { name:"父节点22 - 折叠",
                    children: [
                        { name:"叶子节点221"},
                        { name:"叶子节点222"},
                        { name:"叶子节点223"},
                        { name:"叶子节点224"}
                    ]},
                { name:"父节点23 - 折叠",
                    children: [
                        { name:"叶子节点231"},
                        { name:"叶子节点232"},
                        { name:"叶子节点233"},
                        { name:"叶子节点234"}
                    ]}
            ]},
        { name:"父节点3 - 没有子节点", isParent:true}

    ];

    $(document).ready(function(){
        $.fn.zTree.init($("#treeDemo"), setting, zNodes);
    });*/

    $(function(){
        var setting = {
            async: {
                enable: true,
                url: "../menu/findAll",
                autoParam: ["id", "name"]
            }
        };
        $(document).ready(function(){
            $.fn.zTree.init($("#treeDemo"), setting);
        });
    })
</script>
</body>
</html>
```

pojo

```
package com.offcn.entity;

import lombok.Data;

import java.io.Serializable;
import java.util.List;

@Data
public class Menu implements Serializable {
    private Integer id;
    private String name;
    private String url;
    private Boolean isParent = false;
    private List<Menu> children;
}
```

Controller

```java
@RequestMapping("findAll")
public List<Menu>findAll(){
    return menuService.findAll();
}
```

ServiceImpl

```java
public List<Menu> findAll() {
    List<Menu> menus = menuMapper.selectAll();
    menus = change(menus);
    System.out.println(menus);
    return menus;
}
private List<Menu> change(List<Menu> list) {
    if(list != null && list.size() > 0){
        for(Menu menu : list){
            Integer menuId = menu.getId();//上级菜单的id
            //下级菜单集合
            List<Menu> menuList = menuMapper.selectByParentID(menuId);
            if(menuList != null && menuList.size() > 0) {
                //递归 -- 方法自己调用自己
                menuList = change(menuList);

                menu.setChildren(menuList);
                menu.setIsParent(true);
            }else{
                menu.setChildren(null);
            }
        }
    }
    return list;
}
```

Mapper

```xml
<!--查第一级菜单-->
<select id="selectAll" resultType="com.offcn.entity.Menu">
    SELECT * FROM t_menu WHERE parentMenuId IS NULL
</select>

<!--使用父id查子菜单-->
<select id="selectByParentID" parameterType="int" resultType="com.offcn.entity.Menu">
    SELECT * FROM t_menu WHERE parentMenuId = #{value}
</select>
```



#### 虚拟机静态 IP

```shell
cd /etc/syscongig/network-scripts/
ls
vi ifcfg-ens33
# 设置 ONBOOT为 yes 是动态 ip
ONBOOT=yes
# 静态 ip 修改如下
BOOTPROTO=static
# 追加
IPADDR=192.168.159.21
NETMASK=255.255.255.0
GATEWAY=192.168.159.2
DNS1=8.8.8.8
```

打开 编辑 虚拟网络编辑器

查看 NAT模式 子网地址 为 ip网段 NAT 设置查看网关

![image-20210822233537999](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210822233537999.png)

reboot 重启虚拟机（或者重启网卡systemctl restart network.service）

### Day36

#### 问题

##### Mybatis ResultMap、延迟加载、关联查询 嵌套结果查询、分表查询

映射文件 --- 名称任意（通常和表关联）、保存位置在类路径下（可以在其他任意位置）

resultType 和 resultMap 属性加标签 -- 重点
1）在实现 select 查询时使用 resultType 或者 resultMap
2）区别：
A、resultType 只有属性；resultMap 有属性和标签
B、当实体类属性名和表中字段名称相同时使用resultType；
当实体类属性名和表中字段名称不相同时使用resultMap（使用mysql的字段别名也可以）
C、实现多表关联查询的时候使用resultMap，不能使用resultType。
3）resultType 可以设置的类型有哪些？
A、实体类类型
B、一般类型：Integer、String、Date……
C、Map 类型
4）resultMap （标签）可以设置类型有
A、实体类类型
B、复合实体类类型

resultMap属性和标签 -- 重点
关联查询第一套方案
嵌套结果查询 -- 连接查询

1. 多表关联查询时，resultMap的使用 -- 要把数据映射封装到实体类/复合实体类对象中（否则使用
Map key-value即可）
2. 多表关联查询，结果使用 map 封装，如何处理？
1）查询用户信息，关联详细信息
2）resultType 写map 用List Map 接收 即可
3. 关联查询一对一查询（实体类和复合类封装数据）
1）查询用户信息，关联详细信息
2) resultMap 标签 id result 标签 写 查询表的实体使用 association 标签 中 id、result 标签写连接
的表实体
3）SQL语句是连接查询语句（包括内外连接）
4）查询用户详细信息属于哪个用户
A、实体主方 添加 关联实体
4. 关联查询 实现 一对多关联查询
1）查询用户信息，管理多收件地址
5. 多对多的关联查询
  1）查询用户信息，关联用户购买商品
  2）通过 实体类设计 collection association标签嵌套关系 实现连接查询

关联查询第二套方案

1. 一对一、一对多、多对多关联查询，换一种方式嵌套查询、分表查询方式。
2. 一对一的分表查询实现
1）查询用户信息，关联查询详细信息
2）配置文件变化 语句变化为单表查询
一对一查询嵌套 association 标签中添加 column 属性（本方字段id值）和 select 属性（本方的字
段值送到对方的具体位置，实际上就是对方的某个方法处）相当于左外连接查询
特点：
SQL语句变化连接查询变为单表查询
在 association中没有下级标签 多了两个属性 column 和 select 对方需要配置相应xml内容
3. 一对多实现
1）查询用户信息 以及具备的地址信息
2）association替换为collection javaType替换为ofType即可
4. 多对多实现
1）查询用户 关联购买商品有哪些
延迟加载
1. 介绍
延迟策略、懒加载、延迟查询，是和查询有关。是指在实现查询的时候把查询语句，从框架向数据
库的发送时间延后。在后续程序中如果需要使用相关的数据了，此时才向数据发送SQL查询语句。
2. 在 mybatis 中延延迟策略的实现只有一种情况，关联查询时，查询对方数据可能会被延迟。
3. 在 mybatis 中实现延迟策略时，只有分表方案才能实现延迟。（所以分表方式常用！）
4. 演示
1）局部：使用get展示看效果
一对一、一对多的配置 association、collection 标签中 加入属性 fetchType 值为lazy 不用不发数
据，中间可以隔一段时间，用了才发送。
2）全局：核心配置文件加入全局配置settings标签（properties下typeAliases上）
name为 lazyLoadingEnabled、
aggressiveLazyLoading（极其懒加载）
value为true
3）目的：为了减少向数据库发送 SQL 的次数、从而降低数据库的压力，起到提高整体性能好处

##### SpringAOP 思想实现事务管理

aop 思想实现事务管理-- 重点
1. 什么是事务？
是一个完整的数据库增删改查的执行单元，可能由多条 SQL 语句组成。
2. 事务的特性？
原子性（atomicity）、一致性（consistency）、隔离性（isolation）、持久性（durability） --
ACID
1）原子性：要成功都成功（commit）、要失败都失败（rollback）
2）一致性：事务在执行前后，数据保持不变
3）隔离性：事务和事务之间彼此互不影响
4）持久性：事务在执行前后，对数据的影响是持久的
3. 数据异常
脏读数据、不可重复读数据、幻读数据
1）脏读：读未提交
2）不可重复读：多次读数据不同
3）幻读：插入或者更改造成读取不同
4. 数据异常的处理
事务隔离级别：读未提交、读已提交、可重复读、串行化/序列化
5. 事务的传播性 -- spring实现事务管理时提出的概念
比如：在 service 层的某个方法中存在多个 dao 层方法的调用，service.save()
{dao.insert();dao.select();dao.update()},那么传播性就是事务由第一个 insert 方法传播到第二个
select() 再传播到第三个 update 方法；反过来就是把多个方法纳入一个事务管理单元。
保证同一个连接对象（连接对象绑定到线程中ThreadLocal）
6. spring 中如何实现事务管理？
1）需求：银行中的转账功能的实现
2）实现：
A、创建表、实体类
B、造持久层功能方法
C、造业务层功能
D、相关配置以及事务管理的类
ThreadLocal<> 将连接对象绑定到线程中
queryRunner.query传递链接对象参数，保证事务传播一致性
7. spring 框架中提供的事务管理的方式的实现
1）纯配置
2）配置和注解
@Transactional
3）纯注解
@EnableTransactionManagement
开启事务管理等同于上面标签

##### Spring MVC 执行流程

   ![image-20210715095652702](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210715095652702.png)

1. 用户发送请求至前端控制器 DispatcherServlet
2. DispatcherServlet 收到请求调用 HandlerMapping 处理器映射器
3. 处理器映射器找到具体的处理器（可以根据xml配置、注解进行查找），生成处理器对象及处理器拦截器（如果有则生成）一并返回给 DispatcherServlet
4. DispatcherServlet 调用 HandlerAdapter 处理器适配器
5. HandlerAdapter 经过适配调用具体的处理器（Controller，也叫后端控制器）
6. Controller 执行完成返回 ModelAndView
7. HandlerAdapter 将 Controller 执行结果 ModelAndView 返回给 DispatcherServlet
8. DispatcherServlet 将 ModelAndView 传给 ViewResolver 视图解析器
9. ViewResolver 解析后返回具体 View
10. DispatcherServlet 根据 View 进行渲染视图（即将模型填充至视图中）。DispatcherServlet 响应用户

##### Redis 介绍

Redis 是一个开源（BSD许可）的，内存中的数据结构存储系统，它可以用作数据库、缓存和消息
中间件。

1. 基于内存存储的、以key = value结构存储数据、开源的、可以用于实现数据库、缓存、消息中间件
的系统（从数据库角度，类似mysql，但是没有表结构，是键值对）
2. 数据结构，以哪些结构存储数据？基本结构：字符串结构、列表结构、集合结构、有序集合结构
3. 有事务管理、可以实现数据复制、可以实现数据的持久化、可以实现 LUA 的脚本操作
4. Redis 有高可用、高性能特点：采用集群保证高可用和高性能，在实现集群的时候设置了哨兵的功
能。
Tomcat 的并发（同时访问一条连接） 200条 超过300宕机，需要使用集群。（搭建多个服务器，
每个都相同 用户随机访问）
分布式：不同功能分不同的模块，加上集群，一堆相同的登录、相同的评论等等等。一堆相同的是
一个小集群，小集群与小集群是分布式。
哨兵：用来监测集群的某个服务有没有宕机，是否正常工作，存在主服务。
端口：6379

##### Spring Boot 的 两种配置文件

SpringBoot 配置文件
1. 配置文件作用规范
properties 预定义、自定义的键值对
ymal/yml
2. yml 文件书写格式
key:空格value 如 name: zhangfei
并列关系，左侧对齐
有上下级关系的缩进几个
设置数组属性用 - 、或 []
双引号则 有转义字符的功能
单引号 为字符串拼接

### Day37

回顾

医疗管家 技术的使用 Redis、POI、ECharts、quartz 等技术的使用 能讲解出来。

之后

七天 前端到后台的页面

十四天 第二个项目 纯后台的东西 Postman+Swagger 做测试 暴露 JSON 串 基本增删改查+各种技术+工具类 （加的理由和作用）

模拟面试 一共25天

8月25日-9月30日？

### 注意点

#### 单例模式

懒汉模式

恶汉模式

核心代码

#### mybatis 涉及到的模式

构造者模式

例如SqlSessionFactoryBuilder、XMLConfigBuilder、XMLMapperBuilder、XMLStatementBuilder、CacheBuilder；

工厂模式

例如SqlSessionFactory、ObjectFactory、MapperProxyFactory；

单例模式

例如ErrorContext和LogFactory；

代理模式

Mybatis实现的核心，比如MapperProxy、ConnectionLogger，用的jdk的动态代理；还有executor.loader包使用了cglib或者javassist达到延迟加载的效果；

组合模式

例如SqlNode和各个子类ChooseSqlNode等；

模板方法模式

例如BaseExecutor和SimpleExecutor，还有BaseTypeHandler和所有的子类例如IntegerTypeHandler；

适配器模式

例如Log的Mybatis接口和它对jdbc、log4j等各种日志框架的适配实现；

装饰者模式，例如Cache包中的cache.decorators子包中等各个装饰者的实现；

迭代器模式

例如迭代器模式PropertyTokenizer；

#### Spring 框架涉及到的设计模式

单例模式 scope属性/注解

工厂模式 BeanFactory

代理模式 aop 动态代理

模板模式 jdbcTemplate

springmvc 框架中涉及的模式

适配器模式：接口、抽象类、实现类

ctrl+alt+b：查看接口的实现类；
ctrl+h：查看类或接口的继承关系；

#### jdbcUrl

///代表不写地址和端口，默认也是localhost:3306



#### yum解决方案

在使用yum安装软件包时提示标题所示的错误信息，原因估计是yum查找软件包依赖时使用的是过时的缓存，清空更新之后，再次安装软件，问题消失，

具体指令如下：

```shell
yum clean all
yum update
```

 

#### spring的重点

**事务和AOP**

默认使用jdk动态代理（基于接口）

##### aop典型的应用场景

1. 分页插件采用 aop 思想

   如：mybatis 分页插件 pageHelper（采用 aop 思想）

2. 日志管理采用 aop 思想

   如：log4j 日志打印信息 （aop 前通知的思想）

3. 拦截器采用 aop 思想、实现 

   如：spring-mvc Interceptor

4. 权限验证采用 aop 思想

   如：Spring Security 权限验证框架 用户的操作权限

5. 事务管理采用 aop 思想

#### 从一开始的单页面到分层架构到现在的分布式+微服务

JBLJAVAToWEB Java项目转换web

alt+shift+insert 快速编辑多行

前端页面改的 不用重启 刷新就行

#### SpringMVC 拦截器 涉及 的 问题、坑！

##### 一、拦截器的用法

1. 编写拦截器类 继承HandlerInterceptorAdapter类并重写需要的方法 或实现HandlerInterceptor接口并实现所有方法。

2. 在spring-mvc.xml(也就是springmvc的配置文件)中添加拦截器，代码如下

   ```xml
   <!-- 拦截器 -->
   <mvc:interceptors>   
       <mvc:interceptor>
           <!-- 拦截所有的请求，这个必须写在前面，也就是写在【不拦截】的上面 -->
           <mvc:mapping path="/**"/>
           <!-- 下面是配置不拦截的请求 -->
           <mvc:exclude-mapping path="/login.html" />
           <bean class="com.mm.interceptor.AuthorityInterceptor"/>     
       </mvc:interceptor> 
   </mvc:interceptors>
   ```

   - 需要注意的是，其中bean就是指定前面实现的拦截器类,
   - /**的意思是所有文件夹及里面的子文件夹
   - /*是所有文件夹，不含子文件夹
   - /是web项目的根目录

   除此之外还可以通过DefaultAnnotationHandlerMapping注册自定义拦截器

   ```xml
   <bean class="org.springframework.web.servlet.mvc.annotation.DefaultAnnotationHandlerMapping">
           <property name="interceptors">
               <list>
                   <bean class="com.mm.interceptor.MyInterceptor1"></bean>
                   <bean class="com.mm.interceptor.MyInterceptor2"></bean>
               </list>
              </property>
   </bean>
   ```

   **这种方式注册的时候需要注意，如果配置文件中有<mvc:annotation-driven />那么它默认已经注册了DefaultAnnotationHandlerMapping，AnnotationMethodHandlerAdapter 。我们在配置的这个自定义的就不起作用了，需要把它去掉。所以对待<mvc:annotation-driven />这种简化方法注册的时候，应该是在掌握的足够熟练的前提下使用比较好。**

##### 二、不拦截jsp页面的问题

**拦截器只拦截@Controller注解的类和方法，对于jsp没有拦截(就因为这个耽误了四个小时，一直以为是拦截器配置出错，其实只是访问jsp页面的时候不拦截而已)**

**另外需要注意的是，拦截器是会拦截静态资源的 比如html js css image这类，虽然都是页面 但是html属于静态资源,jsp不属于**

解决方案有两种:

1、将所有的jsp文件放入到WEB-INF文件夹下，这样用户是直接不能访问WEB-INF文件下的jsp文件的。spring mvc的理念也是通过controller里的@RequestMapping来请求相关jsp页面，而非用户直接访问jsp页面。

1. 也就是说，jsp页面的访问需要通过controller来进行一次请求，因为会拦截对controller的请求，所以也就相当于拦截了jsp页面。
2. 如果要做登陆拦截，只需要把登陆页面不拦截，其余页面拦截进行是否登陆的验证即可。

2、还有一种解决方案：jsp如果不放在WEB-INF文件下，spring mvc是无法拦截的，这种情况下需要用最原始的servlet的Filter接口。

**原理：通过Request获取请求的uri进行分析过滤。**

##### 三、防止SpringMVC拦截器拦截js等静态资源文件

SpringMVC提供<mvc:resources>来设置静态资源，但是增加该设置如果采用通配符的方式增加拦截器的话仍然会被拦截器拦截，可采用如下方案进行解决：

**方案一、拦截器中增加针对静态资源不进行过滤(涉及spring-mvc.xml)**

```xml
<mvc:resources location="/" mapping="/**/*.js"/>  
<mvc:resources location="/" mapping="/**/*.css"/>  
<mvc:resources location="/assets/" mapping="/assets/**/*"/>  
<mvc:resources location="/images/" mapping="/images/*" cache-period="360000"/>

<mvc:interceptors>
     <mvc:interceptor>
         <mvc:mapping path="/**/*"/>
         <mvc:exclude-mapping path="/**/fonts/*"/>
         <mvc:exclude-mapping path="/**/*.css"/>
         <mvc:exclude-mapping path="/**/*.js"/>
         <mvc:exclude-mapping path="/**/*.png"/>
         <mvc:exclude-mapping path="/**/*.gif"/>
         <mvc:exclude-mapping path="/**/*.jpg"/>
         <mvc:exclude-mapping path="/**/*.jpeg"/>
         <mvc:exclude-mapping path="/**/*login*"/>
         <mvc:exclude-mapping path="/**/*Login*"/>
         <bean class="com.luwei.console.mg.interceptor.VisitInterceptor"></bean>
     </mvc:interceptor>
</mvc:interceptors>
```

**方案二、使用默认的静态资源处理Servlet处理静态资源(涉及spring-mvc.xml, web.xml)**

在spring-mvc.xml中启用默认Servlet

```xml
<mvc:default-servlet-handler/>
```

在web.xml中增加对静态资源的处理

```xml
<servlet-mapping>    
     <servlet-name>default</servlet-name>    
     <url-pattern>*.js</url-pattern>    
     <url-pattern>*.css</url-pattern>    
     <url-pattern>/assets/*"</url-pattern>    
     <url-pattern>/images/*</url-pattern>    
</servlet-mapping> 
```

**方案三、修改Spring的全局拦截设置为\*.do的拦截（涉及web.xml）**

```xml
<servlet>
     <servlet-name>SpringMVC</servlet-name>
     <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
     <init-param>
         <param-name>contextConfigLocation</param-name>
         <param-value>classpath:spring-mvc.xml</param-value>
     </init-param>
     <load-on-startup>1</load-on-startup>
     <async-supported>true</async-supported>
</servlet>

<servlet-mapping>
     <servlet-name>SpringMVC</servlet-name>
     <url-pattern>*.action</url-pattern>
</servlet-mapping>
```

这样设置，Spring就会只针对以'.do'结尾的请求进行处理，不再维护静态资源

针对这三种方案的优劣分析：

　　第一种方案配置比较臃肿，多个拦截器时增加文件行数，不推荐使用；

　　第二种方案使用默认的Servlet进行资源文件的访问，Spring拦截所有请求，然后再将资源文件交由默认的Sevlet进行处理，性能上少有损耗；

　　第三种方案Spring只是处理以'.action'结尾的访问，性能上更加高效，但是再访问路径上必须都以'.action'结尾，URL不太文雅；

综上所述，推荐使用第二和第三种方案



------



**在SpringMVC3.0之后推荐使用：** 

```xml
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.html"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.ico"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.js"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.css"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.png"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.gif"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.jpg"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.ttf"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.woff"/>
<mvc:resources location="/WEB-INF/html/" mapping="/**/*.woff2"/>
```

 

本文内容参照地方过多，这里不一一列举了。

#### /和/*的区别

**在配置web.xml中SpringMVC拦截器时url-pattern后面配/不能是/***

```xml
其中/和/*的区别：
< url-pattern > / </ url-pattern >   不会匹配到*.jsp，即：*.jsp不会进入spring的 DispatcherServlet类 。
< url-pattern > /* </ url-pattern > 会匹配*.jsp，会出现返回jsp视图时再次进入spring的DispatcherServlet 类，导致找不到对应的controller所以报404错。

总之，关于web.xml的url映射的小知识:
< url-pattern>/</url-pattern>  会匹配到/login这样的路径型url，不会匹配到模式为*.jsp这样的后缀型url
< url-pattern>/*</url-pattern> 会匹配所有url：路径型的和后缀型的url(包括/login,*.jsp,*.js和*.html等)
```

**jsp 的本质是 servlet （编译称为servlet 然后执行），servlet 优先级 默认是最高的（底层实现） 所以 jsp 一般设置为 / 不进行拦截**

#### UUID

Java UUID 统一唯一识别码 的生成 UUID.randomUUID().toString().replaceAll("-", "")

#### 下载文件中文乱码

```java
//下载的时候，响应头即下载文件名可能出现中文乱码
// 处理方式一
byte[] bytes = name.getBytes("UTF-8");
String nName = new String(bytes,"iso8859-1");
// 处理方式二
String nName = URLEncoder.encode(name,"UTF-8");
//实现下载 -- 原生方案：一个头、两个流
//头：响应头
response.setHeader("content-disposition","attachment;filename="+nName);//设置下载时文件名称
                                                                            
String path = "C:\\Users\\Administrator\\Desktop\\upload";                  
File file = new File(path,name);                                            
//流 -- 本地读取流   远程写出流                                                        
InputStream is = new FileInputStream(file);                                 
                                                                            
OutputStream os = response.getOutputStream();                               
                                                                            
//边读边写                                                                      
                                                                            
byte[]bs = new byte[1024];                                                  
int len = -1;                                                               
                                                                            
while((len = is.read(bs)) != -1){                                           
    os.write(bs,0,len);                                                     
}                                                                           
                                                                            
os.close();                                                                 
is.close();                                                                 

```

#### String的endWith判断后缀

```java
// 获取到当前请求url 
String uri = request.getRequestURI();
// 判断是否是addCart 如:xxx/yyy/zzz/addCart
uri.endsWith("addCart");
```

#### Spring 整合 Junit

**在使用 spring-test 的过程中，有两个 runner 可以选择，分别是 SpringRunner 和 SpringJUnit4ClassRunner。**
**如果是在 4.3 之前，只能选择 SpringJUnit4ClassRunner，如果是 4.3 之后，建议选择 SpringRunner。**
**SpringRunner 对 junit 的版本有要求，需要 4.12 及以上。**

#### Spring 和 SpringMVC 分别扫描

Spring 容器和 SpringMVC 容器，父子容器，Spring 是父，SpringMVC 是子；SpringMVC 可以调用父容器对象，反之不可以。

为了安全，进行分别扫描 MVC扫描Controller 不扫描Service，Spring不扫描Controller

![image-20210720105507966](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210720105507966.png)
    
![image-20210720105616712](https://gitee.com/Gitee-CBH/typora-pic/raw/master/img/image-20210720105616712.png)

#### MVC 注解驱动

<mvc:annotation-driven 注解驱动 默认帮你导入三大模块、处理器映射器、处理器适配器、视图解析器，并且帮你使用了jackson 对象 转换 json 格式

#### idea 新项目导入环境

删除.idea、.impl和target文件，这样环境为自己的。

#### 项目的根路径

```jsp
${pageContext.request.contextPath}
```

#### 命令的简称习惯

执行：eXcute，目录：Directory

追问

```html
执行是E开头的啊！
```

追答

```html
英文中excute开头的音（ex...)与X字母的音相近，老外都喜欢这样，类似的圣诞节（Christmas）也曾被简化为Xmas
```

#### JS注意大小引号嵌套的关系

#### 表单的序列化jQuery ajax - serialize() 方法

#### Tomcat启动出错

缓存问题 清除 work目录下 catalina 重启即好

#### Redis启动

先开启服务端 在开启客户端

`./redis-server redis.conf` `./redis-cli`

#### Mysql驱动

高版本需要 com.mysq.cj.jdbc.Driver

#### 释放防火墙

直接关闭防火墙

`systemctl stop firewalld.service`

开启防火墙mysql3306端口的外部访问

```shell
firewall-cmd --zone=public --add-port=3306/tcp --permanent
```

重启防火墙

```shell
 firewall-cmd --reload
```

#### SpringBoot 整合 Dubbo 启动不了服务提供者

dubbo 的 springboot starter 必须卸载 web 依赖 下面 否则 会报错SLF4J 异常



#### getResource().getPath()返回的路径空格变成了 %20

最近我们有一个 web 程序，为了取到配置文件的路径，采用了 this.getClass().getResource(“/”).getPath()
的方法来取得存放 class 的物理路径。本来测试的时候没问题，一发布崩溃掉了。究其原因是发布环境的 Tomcat 的安装目录带有空格，而 getPath 的返回值把空格给转换成了 “%20”。经过一番调查，原来是这是 Java 的一个历史悠久的 bug:

[Bug ID: 4466485 getClass( ).getResource( ).getFile( ) returns file name with %20](http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=4466485)

此 bug 于 2001年6月被提出来，2002年11月最终关闭。没有修复的原因是这样做会导致兼容性问题。官方给出的解决方法是采用URI类再把它解码出来。

方法(1)，使用repaceAll("%20",' ')替换后,只能解决空格问题。但是路径中包含%和中文就不行了。 
方法(2)，使用URLDecoder.decode(str,"UTF-8")解码，但是只能解决一部分，若路径中含有+，也是不能解决的，原因是URL并不是完全用 URLEncoder.encode(str,"UTF-8")编码的,+号被解码后，却变成了空格。
方法(3)，可以解决所有的问题，用TestURL().class.getResource("").toURI().getPath()，但是需要处理URISyntaxException异常，比较麻烦点。

#### XML 写 SQL 解析出错

xml 格式 

第一种方法：
用转义字符把">"和"<"替换掉，就没有问题了。

```
附：XML转义字符

&lt;     	<   	小于号   
&gt;     	>   	大于号   
&amp;     	&   	和   
&apos;     	’   	单引号   
&quot;     	"   	双引号   
```

第二种方法：
因为这个是xml格式的，所以不允许出现类似">"这样的字符

```
<![CDATA[ ]]>符号进行说明，将此类符号不进行解析 

<![CDATA[ 这里写你的sql ]]>  
```

#### Controller 实体类传参接收为 null

实体类起的名字过于简单 第二个为大写字母导致的 因为 RequestBody JSON 解析对象 会去寻找 get方法 但是由于连续的大写字母会导致出错 不遵循驼峰命名规范 和 lombok 有关

@JsonProperty(value = "IdentityCard") （原因： 因为实体类参数和 传入的参数不一致，驼峰命名，具体详细原因不详。增加上这个注解映射后，及可获取实体类中的参数值）

#### JSTL c if 没有 else

使用如下替代

```html
<c:choose>
   <c:when test="">    如果
   </c:when>   
   <c:otherwise>  否则
   </c:otherwise>  
</c:choose>
```

