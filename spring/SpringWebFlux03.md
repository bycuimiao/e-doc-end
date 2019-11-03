### section 6
Reactive Use Cases  
The hardest question to get an answer to as a newbie seems to be "what is it good for?" Here are some examples from an enterprise setting that illustrate general patterns of use:
### word 6
illustrate vt. 阐明，举例说明；图解

### section 7
External Service Calls Many backend services these days are REST-ful (i.e. they operate over HTTP) so the underlying protocol is fundamentally blocking and synchronous. Not obvious territory for FRP maybe, but actually it’s quite fertile ground because the implementation of such services often involves calling other services, and then yet more services depending on the results from the first calls. With so much IO going on if you were to wait for one call to complete before sending the next request, your poor client would give up in frustration before you managed to assemble a reply. So external service calls, especially complex orchestrations of dependencies between calls, are a good thing to optimize. FRP offers the promise of "composability" of the logic driving those operations, so that it is easier to write for the developer of the calling service.
### word 7
underlying adj. 潜在的；根本的；  
fertile adj. 富饶的，肥沃的；能生育的  
territory n. 领土，领域；范围；地域；版图  
frustration n. 挫折
optimize vt. 使最优化，使完善 vi. 优化；持乐观态度
composability 可组合性

### section 8Deferred results (Futures) Java 1.5 introduced a rich new set of libraries including Doug Lea’s "java.util.concurrent", and part of that is the concept of a deferred result, encapsulated in a Future. It’s a good example of a simple abstraction over an asynchronous pattern, without forcing the implementation to be asynchronous, or use any particular model of asynchronous processing. As the Netflix Tech Blog: Functional Reactive in the Netflix API with RxJava shows nicely, Futures are great when all you need is concurrent processing of a set of similar tasks, but as soon as any of them want to depend on each other or execute conditionally you get into a form of "nested callback hell". Reactive Programming provides an antidote to that.
Highly Concurrent Message Consumers Message processing, in particular when it is highly concurrent, is a common enterprise use case. Reactive frameworks like to measure micro benchmarks, and brag about how many messages per second you can process in the JVM. The results are truly staggering (tens of millions of messages per second are easy to achieve), but possibly somewhat artificial - you wouldn’t be so impressed if they said they were benchmarking a simple "for" loop. However, we should not be too quick to write off such work, and it’s easy to see that when performance matters, all contributions should be gratefully accepted. Reactive patterns fit naturally with message processing (since an event translates nicely into a message), so if there is a way to process more messages faster we should pay attention.
### word 8
measure n. 测量；措施；程度；尺寸 vt. 测量；估量；权衡  
benchmarks n. [计] 基准；标竿；水准点；基准测试程序数值（benchmark的复数形式）  
brag v. 吹牛，吹嘘；夸耀  
staggering adj. 惊人的，令人震惊的

### section 9
Spreadsheets Perhaps not really an enterprise use case, but one that everyone in the enterprise can easily relate to, and it nicely captures the philosophy of, and difficulty of implementing FRP. If cell B depends on cell A, and cell C depends on both cells A and B, then how do you propagate changes in A, ensuring that C is updated before any change events are sent to B? If you have a truly reactive framework to build on, then the answer is "you don’t care, you just declare the dependencies," and that is really the power of a spreadsheet in a nutshell. It also highlights the difference between FRP and simple event-driven programming — it puts the "intelligent" in "intelligent routing".
### word 9
relate to 涉及，有关   
capture vt. 俘获；夺得；捕捉，拍摄，录制;这里可译为 体现  
philosophy n. 哲学；哲理；人生观

### section 10
Abstraction Over (A)synchronous Processing This is more of an abstract use case, so straying into the territory we should perhaps be avoiding. There is also some (a lot) of overlap between this and the more concrete use cases already mentioned, but hopefully it is still worth some discussion. The basic claim is a familiar (and justifiable) one, that as long as developers are willing to accept an extra layer of abstraction, they can forget about whether the code they are calling is synchronous or asynchronous. Since it costs precious brain cells to deal with asynchronous programming, there could be some useful ideas there. Reactive Programming is not the only approach to this issue, but some of the implementaters of FRP have thought hard enough about this problem that their tools are useful.
### word 10
stray v. 迷路，走失，偏离；  
perhaps adv. 或许；（表示不确定）也许；  
overlap v. 与……重叠，与……互搭  
precious adj. 宝贵的；珍贵的；矫揉造作的    
costs precious brain cells to deal with ... 花费宝贵的脑细胞处理...  

### section 11
Comparisons  
If you haven’t been living in a cave since 1970 you will have come across some other concepts that are relevant to Reactive Programming and the kinds of problems people try and solve with it. Here are a few of them with my personal take on their relevance:
### word 11 
relevant adj. 相关的；切题的  
cave n. 山洞，洞穴；窑洞

### section 12
Ruby Event-Machine The Event Machine is an abstraction over concurrent programming (usually involving non-blocking IO). Rubyists struggled for a long time to turn a language that was designed for single-threaded scripting into something that you could use to write a server application that a) worked, b) performed well, and c) stayed alive under load. Ruby has had threads for quite some time, but they aren’t used much and have a bad reputation because they don’t always perform very well. The alternative, which is ubiquitous now that it has been promoted (in Ruby 1.9) to the core of the language, is Fibers(sic). The Fiber programming model is sort of a flavour of coroutines (see below), where a single native thread is used to process large numbers of concurrent requests (usually involving IO). The programming model itself is a bit abstract and hard to reason about, so most people use a wrapper, and the Event Machine is the most common. Event Machine doesn’t necessarily use Fibers (it abstracts those concerns), but it is easy to find examples of code using Event Machine with Fibers in Ruby web apps (e.g. see this article by Ilya Grigorik, or the fibered example from em-http-request). People do this a lot to get the benefit of scalability that comes from using Event Machine in an I/O intensive application, without the ugly programming model that you get with lots of nested callbacks.
### word 12
struggled v. 奋斗；努力  
reputation n. 名声，名誉；声望  
ubiquitous adj. 普遍存在的；无所不在的  
promote vt. 促进；提升；推销；发扬  
flavour n. 香味；滋味  
coroutine n. 协同程序  
scalability n. 可扩展性；可伸缩性；可量测性  
intensive adj. 加强的；集中的  

### section 13
Actor Model Similar to Object Oriented Programming, the Actor Model is a deep thread of Computer Science going back to the 1970s. Actors provide an abstraction over computation (as opposed to data and behaviour) that allows for concurrency as a natural consequence, so in practical terms they can form the basis of a concurrent system. Actors send each other messages, so they are reactive in some sense, and there is a lot of overlap between systems that style themselves as Actors or Reactive. Often the distinction is at the level of their implementation (e.g. Actors in Akka can be distributed across processes, and that is a distinguishing feature of that framework).
### word 13
opposed adj. 相反的；敌对的  
consequence n. 结果；重要性；推论

### section 14
Deferred results (Futures) Java 1.5 introduced a rich new set of libraries including Doug Lea’s "java.util.concurrent", and part of that is the concept of a deferred result, encapsulated in a Future. It’s a good example of a simple abstraction over an asynchronous pattern, without forcing the implementation to be asynchronous, or use any particular model of asynchronous processing. As the Netflix Tech Blog: Functional Reactive in the Netflix API with RxJava shows nicely, Futures are great when all you need is concurrent processing of a set of similar tasks, but as soon as any of them want to depend on each other or execute conditionally you get into a form of "nested callback hell". Reactive Programming provides an antidote to that.
### word 14