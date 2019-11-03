### https://spring.io/blog/2016/06/07/notes-on-reactive-programming-part-i-the-reactive-landscape#reactive-use-cases
Notes on Reactive Programming Part I: The Reactive Landscape
### section 1
Reactive Programming is interesting (again) and there is a lot of noise about it at the moment, not all of which is very easy to understand for an outsider and simple enterprise Java developer, such as the author. This article (the first in a series) might help to clarify your understanding of what the fuss is about. The approach is as concrete as possible, and there is no mention of "denotational semantics". If you are looking for a more academic approach and loads of code samples in Haskell, the internet is full of them, but you probably don’t want to be here.

### word 1
landscape n. 风景，景色；山水画  
clarify vt. 澄清；阐明  
fuss n. 大惊小怪；反对，抗议；繁琐的手续；（为小事）大发牢骚  
approach n. 方法，方式；接近；接洽；（某事的）临近；路径；进场（着陆）；相似的事物  
concrete adj. 混凝土的；实在的，具体的；有形的
mention n. 提及，说起  
denotational semantics [计] 指称语义  
academic adj. 学术的；理论的；学院的  

### section 2
Reactive Programming is often conflated with concurrent programming and high performance to such an extent that it’s hard to separate those concepts, when actually they are in principle completely different. This inevitably leads to confusion. Reactive Programming is also often referred to as or conflated with Functional Reactive Programming, or FRP (and we use the two interchangeably here). Some people think Reactive is nothing new, and it’s what they do all day anyway (mostly they use JavaScript). Others seem to think that it’s a gift from Microsoft (who made a big splash about it when they released some C# extensions a while ago). In the Enterprise Java space there has been something of a buzz recently (e.g. see the Reactive Streams initiative), and as with anything shiny and new, there are a lot of easy mistakes to make out there, about when and where it can and should be used.

### word 2
conflate vt. 合并；异文合并; 这里译为 混为一谈  
concurrent programming [计] 并发程序设计  
high performance [计]高性能  
extent n. 程度；范围；长度  
such an extent 如此程度；这里译为 以至于  
separate adj. 分开的；单独的；不同的；各自的；不受影响的 v. （使）分离，分开；隔开；分手；（使）分居；（使）区别（于）
principle n. 原理，原则；  
inevitably adv. 不可避免地；必然地  
confusion n. 混淆，混乱；困惑  
interchangeably adv. [数] 可交换地  
extensions n. 扩展，扩张；延长（extension的复数）   
buzz n. 嗡嗡声；唧唧喳喳的谈话声；  
shiny adj. 光滑的，有光泽的，闪亮的  
mistakes n. 错误（mistake的复数形式）

### section 3
What Is It?  
Reactive Programming is a style of micro-architecture involving intelligent routing and consumption of events, all combining to change behaviour. That’s a bit abstract, and so are many of the other definitions you will come across online. We attempt build up some more concrete notions of what it means to be reactive, or why it might be important in what follows.  
### word 3
involving v. 涉及；包括；使陷于（involve的ing形式）  
intelligent adj. 智能的；聪明的；理解力强的  

### section 4
The origins of Reactive Programming can probably be traced to the 1970s or even earlier, so there’s nothing new about the idea, but they are really resonating with something in the modern enterprise. This resonance has arrived (not accidentally) at the same time as the rise of microservices, and the ubiquity of multi-core processors. Some of the reasons for that will hopefully become clear.
### word 4
resonating v. 产生共鸣；回响；使产生联想；产生（电或机械）共振；（对某人）有重要性（resonate 的现在分词）  
ubiquity n. 普遍存在；到处存在

### section 5
Here are some useful potted definitions from other sources:  
The basic idea behind reactive programming is that there are certain
datatypes that represent a value "over time". Computations that
involve these changing-over-time values will themselves have values
that change over time.  
An easy way of reaching a first intuition about what it's like is to
imagine your program is a spreadsheet and all of your variables are
cells. If any of the cells in a spreadsheet change, any cells that
refer to that cell change as well. It's just the same with FRP. Now
imagine that some of the cells change on their own (or rather, are
taken from the outside world): in a GUI situation, the position of
the mouse would be a good example.  
FRP has a strong affinity with high-performance, concurrency, asynchronous operations and non-blocking IO. However, it might be helpful to start with a suspicion that FRP has nothing to do with any of them. It is certainly the case that such concerns can be naturally handled, often transparently to the caller, when using a Reactive model. But the actual benefit, in terms of handling those concerns effectively or efficiently is entirely up to the implementation in question (and therefore should be subject to a high degree of scrutiny). It is also possible to implement a perfectly sane and useful FRP framework in a synchronous, single-threaded way, but that isn’t really likely to be helpful in trying to use any of the new tools and libraries.
### word 5
pot vt. 把…装罐；射击；节略 n. 壶；盆；罐  
potted adj. 盆栽的；罐装的；密封的；喝醉的  
intuition n. 直觉；直觉力；直觉的知识  
spreadsheet n. 电子制表软件；电子数据表；试算表  
affinity n. 密切关系；吸引力；姻亲关系；类同  
suspicion n. 怀疑；嫌疑；疑心；一点儿  
transparently adv. 显然地，易觉察地；明亮地  
transparently to the caller 对调用者透明  
entirely adv. 完全地，彻底地  
degree n. 程度，等级；度；学位；阶层  
in terms of 就...而言 在…方面  
sane adj. 健全的；理智的；