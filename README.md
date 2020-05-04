# 本项目可作为互联网公司培训JAVA新手的工具，或JAVA初级进阶JAVA高级的必备指南
# 项目目录
1.初级JAVA程序员应该掌握的Maven知识

2.待更新

# 1.初级JAVA程序员应该掌握的Maven知识
## 引子
俗话说我们不能重复造轮子，那我们该如何用别人的代码呢？
我能想到的有这样几种方式，
1.拷贝别人的代码到项目里

2.使用jar包引入

3.使用构建工具maven，gradle等

第一种方法定制性好，你觉得别人写的代码不好了就直接改掉，缺点是你未必能改好
第二种方法就是jar包引入了
那什么是jar包呢，我们可以通俗的理解成：是含有很多别人写的Java类的压缩包
（我们可以通过Intellij Idea的功能生成和引入jar包，具体自行搜索）
第三种方法就是今天的MAVEN方式

## MAVEN
目前Java后端开发都是以SpringBoot为主进行开发的
通常都是Maven项目，使用MAVEN可以帮助我们很方便构建和管理我们的Java项目
除了方便，使用MAVEN还有哪些好处呢？

1.能让项目对象模型最大程度跟实际代码相独立（解耦）

2.便于项目管理，你想想，MAVEN使用简单的版本号之类的描述信息来管理项目，

跟使用复杂的注释或者文件夹命名或者可能手误的文档相比，哪个更好呢
通常我们会在公司的项目里看到pom.xml文件，而pom.xml是Maven的核心

## POM
pom定义了项目的基本信息，用于描述项目如何构建，声明项目依赖
pom.xml文件里最重要的三行是grouId，artifactId，version，它们定义了项目的基本坐标
其中grouId指项目的组，artifactId定义了项目的组，version定义了项目的当前版本
这三个有什么用呢，它可以帮助我们在下文提到的仓库里找到别人写的代码

< groupId >com.springboot</ groupId >

< artifactId >exersize</ artifactId >

< version >1.0.0</ version >

## 代码是怎么被MAVEN引入的
首先，肯定要有一个存放别人代码的地方对不对？
U盘也行，网站也行（例如github），总之我们心中要有一个代码仓库的概念
实际上，maven获取代码的过程就跟你手动从github下载代码一样
我们只需要使用上文提到的grouId，artifactId，version就能找到我们要用的项目的代码

事实上，MAVEN有本地仓库和远程仓库（私服和中央仓库）的概念，
本地仓库就是你电脑上的一个目录，私服就类似你私有的github，中央仓库就类似于公开的github
MAVEN寻找代码的过程如下：

1.MAVEN会首先从本地仓库寻找代码，如果有，美滋滋，结束，否则，进入下一步

2.MAVEN会继续从远程仓库寻找代码，如果有，美滋滋，结束，否则，报错

## 拓展
可以多学习了解下maven的命令，例如mvn clean install，mvn clean package等等

参考书推荐《MAVEN实战》
