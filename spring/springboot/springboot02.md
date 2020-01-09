###链接 https://docs.spring.io/spring-boot/docs/2.2.2.RELEASE/reference/htmlsingle/

2. Getting Started  
If you are getting started with Spring Boot, or “Spring” in general, start by reading this section. It answers the basic “what?”, “how?” and “why?” questions. It includes an introduction to Spring Boot, along with installation instructions. We then walk you through building your first Spring Boot application, discussing some core principles as we go.

### word
1、principle [ˈprɪnsəpl]  
n. 原理，原则；主义，道义；本质，本义；根源，源泉  
例句：We then walk you through building your first Spring Boot application, discussing some core principles as we go.
然后，我们将引导您构建第一个Spring Boot应用程序，并在讨论过程中讨论一些核心原理。

短语
1、sb walk sb through doing sth 某人引导某人做某事 
例句：We then walk you through building your first Spring Boot application
然后，我们将引导您构建第一个Spring Boot应用程序

---------

2.1. Introducing Spring Boot
Spring Boot makes it easy to create stand-alone, production-grade Spring-based Applications that you can run. We take an opinionated view of the Spring platform and third-party libraries, so that you can get started with minimum fuss. Most Spring Boot applications need very little Spring configuration.

You can use Spring Boot to create Java applications that can be started by using java -jar or more traditional war deployments. We also provide a command line tool that runs “spring scripts”.

Our primary goals are:

Provide a radically faster and widely accessible getting-started experience for all Spring development.

Be opinionated out of the box but get out of the way quickly as requirements start to diverge from the defaults.

Provide a range of non-functional features that are common to large classes of projects (such as embedded servers, security, metrics, health checks, and externalized configuration).

Absolutely no code generation and no requirement for XML configuration.

### word
1、stand-alone  [ˈstænd əloʊn]
adj. （计算机）独立运行的；（公司、组织）独立的

2、production-grade 生产级

3、opinionated  [əˈpɪnjəneɪtɪd]
adj. 固执己见的；武断的
例句：We take an opinionated view of the Spring platform and third-party libraries
    我们对Spring平台和第三方库持固执己见的观点
    
4、fuss [fʌs]
n. 大惊小怪；反对，抗议；繁琐的手续；（为小事）大发牢骚
v. 瞎操心；忙乱；打扰；过分关怀；过于讲究细节；吵闹
例句：We take an opinionated view of the Spring platform and third-party libraries, so that you can get started with minimum fuss
我们对Spring平台和第三方库持固执己见的观点，这样您就可以以最小的麻烦入门。

5、radically [ˈrædɪkli]
adv. 根本上；彻底地；以激进的方式
例句:Provide a radically faster and widely accessible getting-started experience for all Spring development.
    为所有Spring开发提供根本上更快且可广泛访问的入门体验

6、accessible [əkˈsesəbl]
adj. 易接近的；可进入的；可理解的
例句：Provide a radically faster and widely accessible getting-started experience for all Spring development.
    为所有Spring开发提供根本上更快且可广泛访问的入门体验
    
7、diverge [daɪˈvɜːrdʒ]
vi. 分歧；偏离；分叉；离题
vt. 使偏离；使分叉
例句：Be opinionated out of the box but get out of the way quickly as requirements start to diverge from the defaults.
开箱即用，但由于需求开始与默认值有所出入，因此很快就会摆脱困境。

短语
get out of the way 让开；避开；解决
例句：Be opinionated out of the box but get out of the way quickly as requirements start to diverge from the defaults.
开箱即用，但由于需求开始与默认值有所出入，因此很快就会摆脱困境。

-------------
2.2. System Requirements
Spring Boot 2.2.2.RELEASE requires Java 8 and is compatible up to Java 13 (included). Spring Framework 5.2.2.RELEASE or above is also required.

Explicit build support is provided for the following build tools:

2.2.1. Servlet Containers
Spring Boot supports the following embedded servlet containers:

2.3. Installing Spring Boot
Spring Boot can be used with “classic” Java development tools or installed as a command line tool. Either way, you need Java SDK v1.8 or higher. Before you begin, you should check your current Java installation by using the following command:

$ java -version
If you are new to Java development or if you want to experiment with Spring Boot, you might want to try the Spring Boot CLI (Command Line Interface) first. Otherwise, read on for “classic” installation instructions.

2.3.1. Installation Instructions for the Java Developer
You can use Spring Boot in the same way as any standard Java library. To do so, include the appropriate spring-boot-*.jar files on your classpath. Spring Boot does not require any special tools integration, so you can use any IDE or text editor. Also, there is nothing special about a Spring Boot application, so you can run and debug a Spring Boot application as you would any other Java program.

Although you could copy Spring Boot jars, we generally recommend that you use a build tool that supports dependency management (such as Maven or Gradle).

Maven Installation
Spring Boot is compatible with Apache Maven 3.3 or above. If you do not already have Maven installed, you can follow the instructions at maven.apache.org.

On many operating systems, Maven can be installed with a package manager. If you use OSX Homebrew, try brew install maven. Ubuntu users can run sudo apt-get install maven. Windows users with Chocolatey can run choco install maven from an elevated (administrator) prompt.
Spring Boot dependencies use the org.springframework.boot groupId. Typically, your Maven POM file inherits from the spring-boot-starter-parent project and declares dependencies to one or more “Starters”. Spring Boot also provides an optional Maven plugin to create executable jars.

###word
1、compatible  [kəmˈpætəbl]
adj. 兼容的；能共处的；可并立的
例句：Spring Boot 2.2.2.RELEASE requires Java 8 and is compatible up to Java 13 (included). 
Spring Boot 2.2.2.RELEASE需要Java 8，并且与Java 13（包括）兼容。

2、explicit  [ɪkˈsplɪsɪt]
adj. 明确的；清楚的；直率的；详述的
例句：Explicit build support is provided for the following build tools:
    为以下构建工具提供了明确的构建支持：

3、instruction [ɪnˈstrʌkʃn]
n. 指令，命令；指示；教导；用法说明
例句：Installation Instructions for the Java Developer
    Java开发人员的安装说明
    
4、appropriate  [əˈproʊpriət]
adj. 适当的；恰当的；合适的
vt. 占用，拨出
例句：To do so, include the appropriate spring-boot-*.jar files on your classpath.
为此，请在类路径中包含相应的spring-boot-*.jar文件。

5、typically [ˈtɪpɪkli]
adv. 代表性地；作为特色地
例句：

6、inherits 继承
例句：Typically, your Maven POM file inherits from the spring-boot-starter-parent project and declares dependencies to one or more “Starters”.
通常，您的Maven POM文件是从spring-boot-starter-parent项目继承的，并声明对一个或多个“ Starters”的依赖关系。


-----------
2.3.2. Installing the Spring Boot CLI
The Spring Boot CLI (Command Line Interface) is a command line tool that you can use to quickly prototype with Spring. It lets you run Groovy scripts, which means that you have a familiar Java-like syntax without so much boilerplate code.

You do not need to use the CLI to work with Spring Boot, but it is definitely the quickest way to get a Spring application off the ground.

Manual Installation
You can download the Spring CLI distribution from the Spring software repository:

spring-boot-cli-2.2.2.RELEASE-bin.zip

spring-boot-cli-2.2.2.RELEASE-bin.tar.gz

Cutting edge snapshot distributions are also available.

Once downloaded, follow the INSTALL.txt instructions from the unpacked archive. In summary, there is a spring script (spring.bat for Windows) in a bin/ directory in the .zip file. Alternatively, you can use java -jar with the .jar file (the script helps you to be sure that the classpath is set correctly).

### word
1、prototype [ˈproʊtətaɪp]
n. 原型；标准，模范
例句：The Spring Boot CLI (Command Line Interface) is a command line tool that you can use to quickly prototype with Spring.

2、boilerplate  [ˈbɔɪlərpleɪt]
n. 样板文件；引用
例句：It lets you run Groovy scripts, which means that you have a familiar Java-like syntax without so much boilerplate code.

3、definitely  [ˈdefɪnətli]
adv. 清楚地，当然；明确地，肯定地
例句：You do not need to use the CLI to work with Spring Boot, but it is definitely the quickest way to get a Spring application off the ground

4、archive [ˈɑːrkaɪv]
n. 档案馆；档案文件
vt. 把…存档
例句：Once downloaded, follow the INSTALL.txt instructions from the unpacked archive.

5、preceding   ['prisidɪŋ]
adj. 在前的；前述的
v. 在...之前（precede的ing形式）
例句：The preceding instructions install a local instance of spring called the dev instance.

-----------

2.3.3. Upgrading from an Earlier Version of Spring Boot
If you are upgrading from the 1.x release of Spring Boot, check the “migration guide” on the project wiki that provides detailed upgrade instructions. Check also the “release notes” for a list of “new and noteworthy” features for each release.

When upgrading to a new feature release, some properties may have been renamed or removed. Spring Boot provides a way to analyze your application’s environment and print diagnostics at startup, but also temporarily migrate properties at runtime for you. To enable that feature, add the following dependency to your project:

###word
1、upgrade [ˈʌpɡreɪd]
v. 使（计算机、软件等）升级；改善（尤指服务）；给（飞机乘客或宾馆客人）升级；给（某人）升职；提高（某事物的）地位
n. 升级；（尤指计算设备的）升级版；向上的斜坡；增加
adj. 往上的
adv. 往上
例句：Upgrading from an Earlier Version of Spring Boot

2、migration [mai'ɡreiʃən]
n. 迁移；移民；移动
例句：If you are upgrading from the 1.x release of Spring Boot, check the “migration guide” on the project wiki that provides detailed upgrade instructions

3、noteworthy  [ˈnoʊtwɜːrði]
adj. 值得注意的；显著的
例句：Check also the “release notes” for a list of “new and noteworthy” features for each release.
还请检查“发行说明”以获取每个发行版的“新功能和值得注意的功能”列表。

---------
2.4. Developing Your First Spring Boot Application
This section describes how to develop a simple “Hello World!” web application that highlights some of Spring Boot’s key features. We use Maven to build this project, since most IDEs support it.

The spring.io web site contains many “Getting Started” guides that use Spring Boot. If you need to solve a specific problem, check there first.

You can shortcut the steps below by going to start.spring.io and choosing the "Web" starter from the dependencies searcher. Doing so generates a new project structure so that you can start coding right away. Check the Spring Initializr documentation for more details.

Before we begin, open a terminal and run the following commands to ensure that you have valid versions of Java and Maven installed:

$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)
$ mvn -v
Apache Maven 3.5.4 (1edded0938998edf8bf061f1ceb3cfdeccf443fe; 2018-06-17T14:33:14-04:00)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation
This sample needs to be created in its own folder. Subsequent instructions assume that you have created a suitable folder and that it is your current directory.

2.4.1. Creating the POM
We need to start by creating a Maven pom.xml file. The pom.xml is the recipe that is used to build your project. Open your favorite text editor and add the following:


### word
1、highlight  [ˈhaɪlaɪt]
v. 突出；强调；使显著；加亮；着亮彩于（头发）
n. 最精彩的部分；最重要的事情；强光部分
例句：This section describes how to develop a simple “Hello World!” web application that highlights some of Spring Boot’s key features. 
本节介绍如何开发一个简单的“ Hello World！” Web应用程序，该应用程序重点介绍Spring Boot的一些关键功能。

2、shortcut [ˈʃɔːrtkʌt]
n. 捷径；被切短的东西
shortcut the steps 简化步骤
例句：You can shortcut the steps below by going to start.spring.io and choosing the "Web" starter from the dependencies searcher. 
通过转到start.spring.io并从依赖项搜索器中选择“ Web”启动器，可以简化以下步骤。

3、subsequent [ˈsʌbsɪkwənt]
adj. 随后的
例句：Subsequent instructions assume that you have created a suitable folder and that it is your current directory.

4、assume [əˈsuːm]
vi. 假定；设想；承担；采取
vt. 僭取；篡夺；夺取；擅用；侵占

5、recipe [ˈresəpi]
n. 食谱；[临床] 处方；秘诀；烹饪法
例句：The pom.xml is the recipe that is used to build your project. 

----------
2.4.2. Adding Classpath Dependencies
Spring Boot provides a number of “Starters” that let you add jars to your classpath. Our applications for smoke tests use the spring-boot-starter-parent in the parent section of the POM. The spring-boot-starter-parent is a special starter that provides useful Maven defaults. It also provides a dependency-management section so that you can omit version tags for “blessed” dependencies.

Other “Starters” provide dependencies that you are likely to need when developing a specific type of application. Since we are developing a web application, we add a spring-boot-starter-web dependency. Before that, we can look at what we currently have by running the following command:

The mvn dependency:tree command prints a tree representation of your project dependencies. You can see that spring-boot-starter-parent provides no dependencies by itself. To add the necessary dependencies, edit your pom.xml and add the spring-boot-starter-web dependency immediately below the parent section:

If you run mvn dependency:tree again, you see that there are now a number of additional dependencies, including the Tomcat web server and Spring Boot itself.

2.4.3. Writing the Code
To finish our application, we need to create a single Java file. By default, Maven compiles sources from src/main/java, so you need to create that folder structure and then add a file named src/main/java/Example.java to contain the following code:

Although there is not much code here, quite a lot is going on. We step through the important parts in the next few sections.

The @RestController and @RequestMapping Annotations
The first annotation on our Example class is @RestController. This is known as a stereotype annotation. It provides hints for people reading the code and for Spring that the class plays a specific role. In this case, our class is a web @Controller, so Spring considers it when handling incoming web requests.

The @RequestMapping annotation provides “routing” information. It tells Spring that any HTTP request with the / path should be mapped to the home method. The @RestController annotation tells Spring to render the resulting string directly back to the caller.

The @RestController and @RequestMapping annotations are Spring MVC annotations (they are not specific to Spring Boot). See the MVC section in the Spring Reference Documentation for more details.
The @EnableAutoConfiguration Annotation
The second class-level annotation is @EnableAutoConfiguration. This annotation tells Spring Boot to “guess” how you want to configure Spring, based on the jar dependencies that you have added. Since spring-boot-starter-web added Tomcat and Spring MVC, the auto-configuration assumes that you are developing a web application and sets up Spring accordingly.

Starters and Auto-configuration
Auto-configuration is designed to work well with “Starters”, but the two concepts are not directly tied. You are free to pick and choose jar dependencies outside of the starters. Spring Boot still does its best to auto-configure your application.

The “main” Method
The final part of our application is the main method. This is just a standard method that follows the Java convention for an application entry point. Our main method delegates to Spring Boot’s SpringApplication class by calling run. SpringApplication bootstraps our application, starting Spring, which, in turn, starts the auto-configured Tomcat web server. We need to pass Example.class as an argument to the run method to tell SpringApplication which is the primary Spring component. The args array is also passed through to expose any command-line arguments.


###word
1、omit  [əˈmɪt]
vt. 省略；遗漏；删除；疏忽
例句：It also provides a dependency-management section so that you can omit version tags for “blessed” dependencies.

2、hint [hɪnt]
n. 暗示，提示（hint的复数形式）
v. 暗示，示意（hint的单三形式）
例句：It provides hints for people reading the code and for Spring that the class plays a specific role.

3、render [ˈrendər]
v. 致使；提供，回报；援助；提交，提出；作出（裁决）；放弃；表达；演奏；翻译；绘制；粉刷；熔化；从（动物身体）提取（蛋白质）；秘密偷渡
n. 底灰，底泥；交纳
例句：The @RestController annotation tells Spring to render the resulting string directly back to the caller.

短语
1、smoke test 【专业术语】冒烟测试 
Our applications for smoke tests use the spring-boot-starter-parent in the parent section of the POM.

