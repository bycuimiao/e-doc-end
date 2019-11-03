### section 15
Reactive Programming in Java  
Java is not a "reactive language" in the sense that it doesn’t support coroutines natively. There are other languages on the JVM (Scala and Clojure) that support reactive models more natively, but Java itself does not until version 9. Java, however, is a powerhouse of enterprise development, and there has been a lot of activity recently in providing Reactive layers on top of the JDK. We only take a very brief look at a few of them here.
### word 15
powerhouse n. 精力充沛的人，身强力壮的人；强大的集团（或组织）；强国；权势集团；权威人士；动力源  

### section 16
Reactive Streams is a very low level contract, expressed as a handful of Java interfaces (plus a TCK), but also applicable to other languages. The interfaces express the basic building blocks of Publisher and Subscriber with explicit back pressure, forming a common language for interoperable libraries. Reactive Streams have been incorporated into the JDK as java.util.concurrent.Flow in version 9. The project is a collaboration between engineers from Kaazing, Netflix, Pivotal, Red Hat, Twitter, Typesafe and many others.
### word 16
contract n. 合同，契约；婚约  
explicit adj. 明确的；清楚的；直率的；详述的  
back pressure [机] 背压；[力] 回压；  
interoperable adj. （计算机系统或软件、不同机器）可共同操作的，可互换利用信息的，可配合动作的  
collaboration n. 合作；勾结；通敌  

### section 17
RxJava: Netflix were using reactive patterns internally for some time and then they released the tools they were using under an open source license as Netflix/RxJava (subsequently re-branded as "ReactiveX/RxJava"). Netflix does a lot of programming in Groovy on top of RxJava, but it is open to Java usage and quite well suited to Java 8 through the use of Lambdas. There is a bridge to Reactive Streams. RxJava is a "2nd Generation" library according to David Karnok’s Generations of Reactive classification.  
Reactor is a Java framework from the Pivotal open source team (the one that created Spring). It builds directly on Reactive Streams, so there is no need for a bridge. The Reactor IO project provides wrappers around low-level network runtimes like Netty and Aeron. Reactor is a "4th Generation" library according to David Karnok’s Generations of Reactive classification.
### word 17
pivotal adj. 关键的；中枢的；枢轴的 n. 关键事物；中心事物  
classification n. 分类；类别，等级  

### section 18
Spring Framework 5.0 (first milestone June 2016) has reactive features built into it, including tools for building HTTP servers and clients. Existing users of Spring in the web tier will find a very familiar programming model using annotations to decorate controller methods to handle HTTP requests, for the most part handing off the dispatching of reactive requests and back pressure concerns to the framework. Spring builds on Reactor, but also exposes APIs that allow its features to be expressed using a choice of libraries (e.g. Reactor or RxJava). Users can choose from Tomcat, Jetty, Netty (via Reactor IO) and Undertow for the server side network stack.
### word 18
milestone n. 里程碑，划时代的事件  
tier n. 层，排；行，列；等级  
handing off 交接  
expose vt. 揭露，揭发；使曝光；显示  

### section 19
Ratpack is a set of libraries for building high performance services over HTTP. It builds on Netty and implements Reactive Streams for interoperability (so you can use other Reactive Streams implementations higher up the stack, for instance). Spring is supported as a native component, and can be used to provide dependency injection using some simple utility classes. There is also some autoconfiguration so that Spring Boot users can embed Ratpack inside a Spring application, bringing up an HTTP endpoint and listening there instead of using one of the embedded servers supplied directly by Spring Boot.
### word 19
utility adj. 实用的；通用的；有多种用途的 n. 实用；效用；公共设施；功用  

### section 20
Akka is a toolkit for building applications using the Actor pattern in Scala or Java, with interprocess communication using Akka Streams, and Reactive Streams contracts are built in. Akka is a "3rd Generation" library according to David Karnok’s Generations of Reactive classification.
### word 20
toolkit n. 工具包，工具箱  


### section 21
Why Now?  
What is driving the rise of Reactive in Enterprise Java? Well, it’s not (all) just a technology fad — people jumping on the bandwagon with the shiny new toys. The driver is efficient resource utilization, or in other words, spending less money on servers and data centres. The promise of Reactive is that you can do more with less, specifically you can process higher loads with fewer threads. This is where the intersection of Reactive and non-blocking, asynchronous I/O comes to the foreground. For the right problem, the effects are dramatic. For the wrong problem, the effects might go into reverse (you actually make things worse). Also remember, even if you pick the right problem, there is no such thing as a free lunch, and Reactive doesn’t solve the problems for you, it just gives you a toolbox that you can use to implement solutions.
### word 21
fad n. 时尚；一时的爱好；一时流行的狂热  
bandwagon n. 流行，时尚，潮流；乐队花车；（尤指政客追赶的）浪头  
utilization n. 利用，使用 ps:utility adj. 实用的；通用的；  
intersection n. 交叉；十字路口；交集；交叉点  
foreground n. 前景；最显著的位置  
dramatic adj. 戏剧的；急剧的；引人注目的；激动人心的  
reverse v. 颠倒；撤销；反转； n. 逆向；相反；背面； adj. 相反的；背面的

### section 22
Conclusion  
In this article we have taken a very broad and high level look at the Reactive movement, setting it in context in the modern enterprise. There are a number of Reactive libraries or frameworks for the JVM, all under active development. To a large extent they provide similar features, but increasingly, thanks to Reactive Streams, they are interoperable. In the next article in the series we will get down to brass tacks and have a look at some actual code samples, to get a better picture of the specifics of what it means to be Reactive and why it matters. We will also devote some time to understanding why the "F" in FRP is important, and how the concepts of back pressure and non-blocking code have a profound impact on programming style. And most importantly, we will help you to make the important decision about when and how to go Reactive, and when to stay put on the older styles and stacks.
### word 22
brass tacks 基本事实；事实真相；黄铜平头钉   
brass n. 黄铜；黄铜制品；铜管乐器  
tack n. 大头钉  
devote v. 致力于，奉献于  
