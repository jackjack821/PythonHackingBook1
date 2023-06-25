# Pytnon黑客编程之极速入门

# 前言

在进行网络安全培训的过程中，很多同学都会问“如何成长为真正的黑客”之类的问题。我都会告诉他们，编程是基础，编程能力决定你理解的是否深入，能走的是否够远。你是想做一个只会用工具的人，还是想做一个能写工具给别人用的黑客？ 当然这是针对初学者的激励，安全工作的方方面面都离不开编程，网络协议分析、数据抓取和解析、逆向工程、自动化扫码、漏洞测试和攻击......哪一样离了编程，都玩不转。但是什么样的编程语言是最合适的呢？

我接触过很多编程语言，c/c++,Java,C#,PHP,Perl,F#,Ruby，JavaScript等等，都是在不同的工作环境或者面对不同的工作任务时候被动接触的，每种语言都有自己的特性和优势，这里我们不去做过多的对比。我最开始从事网络安全相关的工作任务的时候使用的是C 和 C#,使用C#是出于个人喜好，以及在windows上编程的便利性；使用C是为了跨平台和他的底层能力。后来接触了Python，Python在绝大多数场景中直接替代了C和C#。在阅读了很多国外黑客的文章，使用了很多流行的工具之后，我意识到在这个领域里Python具有绝对的霸主地位，尤其是在读了《Gray Hat Python: Python hackers and reverse engineers》一书之后，对Python在底层编程方向上的能力有了新的认识，从此爱上这门语言，一发不可收拾。社区为Python开发了大量的库，我们可以几行代码就实现数据包监听和解析，几十行代码实现Web数据抓取和分析，便利性是其他语言不可比的。同时，黑客们使用Python编写了大量的工具，并且都是开源的，不论是我们参考他们的实现来实现自己的工具还是做上层封装调用各种工具，都极其便利。所以说，黑客编程，Python是最好的选择。

## 为什么要编写这套课程？

“师父领进门，修行在个人”。其实入门是最难的，大量的网络安全爱好者，他们对“黑客”这个词的理解并不准确，一上来把精力放到了各种实战上，甚至花费很多钱购买各种以演示为主的教程上，结果几年过去了，仍然不得其法，一直在门外徘徊。互联网和计算机上看到的一切，都是代码构成的，从理解代码开始，来理解计算机，理解网络，理解程序，理解架构，这才是不二心法。
本着给更多的入门者引路的想法，我着手编写这套教程。

## 本教程的特点

入门要简单，曲线要平滑，是这套课程的设计思路。有的书让人读起来一气呵成，有的书读着读着就放弃了，计算机书籍让人放弃的尤其多，究其原因，在于作者将重点放到了知识本身而不是读者的学习过程。 入门类书籍或者教程需要把重点放在“引导”、“解惑”和“练习”上面。本教程保持了如下特点：

> 1. 快速上手。抛弃过于晦涩的理论讲解，通过实践建立从感性到理性的过渡。
> 2. 曲线平滑。尽可能的照顾最广大的读者，保持各章节内容和知识点上的连贯性。
> 3. 讲练结合。不讲大道理，也不堆代码，保持案例的简洁性和合理性。
> 4. 深广适中。教程会优先注重广度，让读者有全面的认识和感知。深度上适当扩展。
> 5. 提供源码。所有实际案例的源码，都会提供github的链接。

## 内容概览

教程核心内容分为6个大的部分：

### 1. Python编程基础

如果有一定的Python编辑基础的同学来阅读本教程会更容易，为了同时照顾没有接触过Python基础的同学，在教程的第一部分用两章来介绍Python编程基础，以便首次接触Python的同学可以按照教程的内容快速入门，理解书上的例子。

本部分和书上的例子紧密相关，但是不会涵盖Python编程基础的方方面面，真正的理解Python编程，还需要多下功夫看其他的书籍。

### 2. 网络安全

这一部分，集中在网络协议解析，网络层和传输层数据包捕获和注入。网络协议是网络安全的基础，本部分开篇会首先讲解下TCP/IP体系结构的基本概念，在理解协议的基础上理解代码和程序是如何描述网络协议的，如何利用网络协议来达到监听或者数据篡改的目的的。针对以太网和Wifi，都会利用案例来进行讲解。

### 3. Web应用安全

Web应用不论实在桌面端还是移动端，都是我们使用最广泛的应用形式。Web应用从应用编码到容器都存在安全漏洞，有很多经典的漏洞一直存在，比如Sql注入、XSS等。 本部分从Http协议入手，来讲解Web应用的基本原理，在此基础上，讲解经典漏洞的形成原理。了解了漏洞原理，我们就可以通过编程的方式来进行漏洞扫描和自动化攻击了。

### 4. 漏洞利用

这部分集中在针对已经存在的漏洞，如何进行Exploit，编写PoC。信息搜集是渗透测试非常重要的第一步，在信息搜集的基础上需要对目标服务器存在的漏洞进行扫描和探测，探测到已知漏洞，想要突破必须要进行Exploit。在网上我们可以找到大量的使用Python编写的PoC，本部分会相信讲解漏洞利用插件的编写方法和如何进行自动攻击。

### 5. 逆向

逆向的基本功是调试，Pydbg是功能强大的调试工具，本部分会介绍该工具的使用。漏洞利用环节，我们会演示如何通过内存补丁的方式达到破解目的。

### 6. 自动化

程序和手工相比，一个重要的优势就是自动化。通过Python编程，我们可以对多任务进行调度，可以把若干工具整合起来，可以将手工的工作流程整体串联，自动扫描，自动攻击，自动生成报告等等。

## 一点期待

期望通过本教程的学习，各位同学能找到黑客编程的入门之路，能具备编写自己的安全工具的能力，能自己编写代码执行自动化攻击。最最重要的，能从代码的角度，理解你看到的一切。

这个教程的目标是引路，我只有两个实用招式传授给你们：多写代码，多多实践。

##  本书大纲
[课程大纲](大纲.md)
# Python 黑客编程之极速入门

## 第一章: Python 编程基础
•	Python简介和开发环境搭建</br>
•	数值类型</br>
•	字符串、列表、元组、字典和集合</br>
•	流程控制</br>
•	函数</br>
•	模块</br>
•	异常处理</br>
•	面向对象编程</br>
## 第二章: 系统级编程与安全
•	Python编程之禅</br>
•	文件和目录</br>
•	线程</br>
•	进程的创建</br>
•	多进程</br>
•	进程内通信 (IPC)</br>
•	实例讲解</br>
## 第三章: 网络安全编程 – 嗅探和注入
•	原始套接字基础</br>
    套接字编程</br>
•	服务端和客户端编程</br>
•	无线嗅探</br>
•	数据包注入</br>
•	PCAP 分件分析</br>
•	实例讲解</br>
## 第四章: Web 应用安全
•	web服务端和浏览器端</br>
•	Web应用模糊测试</br>
•	HTML 内容自动分析</br>
•	浏览器模拟</br>
•	攻击Web Service</br>
•	代理</br>
•	自动化攻击（SQL注入，XSS等）</br>
•	实例讲解</br>
## 第五章: 漏洞利用
•	Exploit 开发技术</br>
•	免杀</br>
•	使用Python写漏洞利用插件</br>
•	二进制分析</br>
•	自动攻击</br>
•	实例讲解</br>
## 第六章: 恶意软件分析和逆向工程
•	进程调试</br>
•	Pydbg 入门</br>
•	实时应用分析</br>
•	断点调试</br>
•	内存补丁</br>
•	实例讲解</br>
## 第七章: 自动化攻击
•	Python自动化攻击</br>
•	常用类库和应用</br>
•	实例讲解</br>
## 第8章: 课程总结和寄语




 
--  
                      
                        
