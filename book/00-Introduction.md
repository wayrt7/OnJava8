
# 简介

> “我的语言极限，即是我的世界的极限。” ——路德维希·维特根斯坦（*Wittgenstein*）

这句话对于编程语言来说也一样。你所使用的编程语言会将你的思维模式固化并逐渐远离其他语言。Java 作为一门傲娇的派生语言尤其如此。最早的语言设计者为了不想在项目中使用 C ++，而创造了这种看起来很像 C ++,却比 C ++有了改进的新语言（他们的原始项目从未实现过）。虚拟机和垃圾回收机制是其最核心的变化，这两个概念本书后面的章节都会有详细描述。 不仅如此，Java 还在其他方面推动行业了发展。例如，现在绝大多数编程语言都包含文档注释语法和 HTML 文档生成的工具。Java 最主要的概念之一“对象”来自SmallTalk语言。Java 定义了“对象”（在下一章中描述）为编程的基本单元。于是万物皆对象。

时间已经检验了这种信念，并发现它太过狂热。有些人甚至认为“对象”是完全错误的概念，应该被丢弃。就我个人而言，把一切都当成一个对象不仅是一个不必要的负担，而且还会招致许多设计朝着不好的方向发展。尽管如此，“对象”的概念依然有其闪光点。固执地要求所有东西都是一个对象（特别是一直到最底层级别）是一个设计错误。相反，完全逃避“对象”的概念似乎同样太过苛刻。

其他 Java 语言决策并没有像承诺的那样完成。在本书中，我会尝试解释这些。你不仅了解这些功能，还要了解为什么他们可能对你不太适用。这无关 Java 是一种好语言或者坏语言。一旦你了解了该语言的缺陷和局限性，你就能够：

1. 遇到“已停用”的功能特性时不会疑惑。

2. 了解 Java 语言界限，更好地设计和编码。

编程有关管理复杂性；问题的复杂性依赖于机器的复杂性。由于这种复杂性，我们的大多数编程项目都失败了。许多语言设计决策时都考虑到了复杂性，但在某些时候，其他问题也势必不会少的，程序员不可避免地“碰壁”。例如，C ++必须向后兼容C（允许C程序员轻松迁移），并且效率很高。这些目标诚然很好，并且也解释了为什么C ++在编程界取得了成功。为了保证兼容性的代价会造成语言额外的复杂性。当然，你可以责怪程序员和管理人员，但如果一种语言可以通过捕捉异常来提供有用的信息，为什么不呢？

虽然Visual BASIC（VB）绑定在BASIC上，但BASIC实际上并不是一种可扩展的语言。在VB上堆积的所有扩展造成大量无法维护的语法。Perl 向后兼容 awk，sed，grep 以及其它要替换的 Unix 工具，因此它经常被指责生成“只写代码”（也就是说，你看不懂自己的代码）。另一方面，C ++，VB，Perl 和其他语言（如 SmallTalk）的一些设计工作集中在复杂性问题上，因此在解决某些类型的问题方面非常成功。通信革命使我们所有人更容易地相互沟通：一对一，团体和行星。据说下一次革命会形成一种新全球性的思想，这种思想源于足量的人之间的相互联系。Java 可能会也可能不会成为这场革命的工具之一，但至少这种可能性让我觉得我现在正在做的传道授业是一件有意义的事情。




## 前提条件

阅读本书需要读者对编程有基本的了解:

程序是由一系列代码块，子句或函数组成的控制语句的集合。比如 “if”，“while”判断语句等等。

你可能已经在学校、网络或其他书本上了熟悉了这样。只要你对自己的编程基础有自信，你就可以完成本书的学习。

你可以通过在 On Java 8的网站上免费下载 Think in C 来补充学习 Java 所需要的前置知识。 本书介绍了 Java 语言的基本控制机制以及面对对象编程的概念。在本书中我引述了一些C/C ++ 语言中的一些特性来帮助读者更好的理解 Java。 毕竟 Java 是在它们的基础之上发明的。理解他们之间的区别，有助于读者更好的学习Java。 


## JDK文档

甲骨文公司已经提供了标准免费的JDK文档。除非必要，否则在本书中将不再赘述有关API使用的细节。使用浏览器来即时搜索最新最全的JDK文档要好过翻阅本书来查找。只有在需要补充特定的示例时，我才会提供有关的额外描述。


## C编程思想

《Think in C 》已经可以在www.OnJava8.com免费下载。Java的基础语法是基于C语言的。《Think in C 》中有更适合初学者的编程基础介绍。 我已经委托 Chuck Allison 将这本C基础的书籍作为独立产品附赠于本书的 CD 中。希望大家在阅读本书时，都已具备了学习 JAVA 的良好基础。


## 源码下载

本书中所有源代码的示例都在版权保护的前提下通过GITHUB免费提供。您可以将这些代码用于教育。任何人不得在未经正确引用代码来源的情况下随意重新发布此代码示例。在每个代码文件中，您都可以找到以下版权声明文件作为参考：

**Copyright.txt**

©2017 MindView LLC。版权所有。如果上述版权声明，本段和以下内容，特此授予免费使用，复制，修改和分发此计算机源代码（源代码）及其文档的许可，且无需出于下述目的的书面协议所有副本中都有五个编号的段落。

1. 允许编译源代码并将编译代码仅以可执行格式包含在个人和商业软件程序中。

2. 允许在课堂情况下使用源代码而不修改源代码，包括在演示材料中，前提是“On Java 8”一书被引用为原点。

3. 可以通过以下方式获得将源代码合并到印刷媒体中的许可：MindView LLC，PO Box 969，Crested Butte，CO 81224 MindViewInc@gmail.com 

4. 源代码和文档的版权归MindView LLC所有。提供的源代码没有任何明示或暗示的担保，包括任何适销性，适用于特定用途或不侵权的默示担保。MindView LLC不保证任何包含源代码的程序的运行不会中断或没有错误。MindView LLC不对任何目的的源代码或包含源代码的任何软件的适用性做出任何陈述。包含源代码的任何程序的质量和性能的全部风险来自源代码的用户。用户理解源代码是为研究和教学目的而开发的，建议不要仅仅因任何原因依赖源代码或任何包含源代码的程序。如果源代码或任何产生的软件证明有缺陷，则用户承担所有必要的维修，修理或更正的费用。

5. 在任何情况下，MINDVIEW LLC或其出版商均不对任何一方根据任何法律理论对直接，间接，特殊，偶发或后果性损害承担任何责任，包括利润损失，业务中断，商业信息丢失或任何其他保险公司。由于MINDVIEW LLC或其出版商已被告知此类损害的可能性，因此使用本源代码及其文档或因无法使用任何结果程序而导致的个人受伤或者个人受伤。MINDVIEW LLC特别声明不提供任何担保，包括但不限于对适销性和特定用途适用性的暗示担保。此处提供的源代码和文档基于“原样”基础，没有MINDVIEW LLC的任何随附服务，MINDVIEW LLC没有义务提供维护，支持，更新，增强或修改。


**请注意**，MindView LLC 仅提供以下唯一网址发布更新书中的代码示例，https://github.com/BruceEckel/OnJava8-examples 。您可在上述条款范围内将示例免费使用于项目和课堂中。

如果您在源代码中发现错误，请在下面的网址提交更正：https://github.com/BruceEckel/OnJava8-examples/issues 


## 编码样式

本书中代码标识符（关键字，方法，变量和类名）以粗体，固定宽度代码字体显示。像“**class**”这种在代码中高频率出现的关键字可能让你觉得粗体有点乏味。其他显示为正常字体。本书文本格式尽可能遵循 Oracle 常见样式，并保证在大多数 Java 开发环境中被支持。书中我使用了自己喜欢的字体风格。Java 是一种自由的编程语言，你也可以使用 IDE（集成开发环境）工具（如 IntelliJ IDEA，Eclipse或NetBeans）将格式更改为适合你的格式。

本书代码文件使用自动化工具进行测试，并在最新版本的 Java 编译通过（除了那些特别标记的错误之外）。本书重点介绍并使用 Java 8进行测试。如果您必须了解更早的语言版本，可以在[www.OnJava8.com](http://www.OnJava8.com)免费下载 *Thinking in Java*。


## BUG提交

本书经过多重校订，但还是难免有所遗漏被新读者发现。如果您在正文或示例中发现任何错误的内容，请在[此处](https://github.com/BruceEckel/OnJava8-examples/issues)提交错误以及建议更正，作者感激不尽。


## 邮箱订阅

您可以在[www.OnJava8.com上](http://www.OnJava8.com)订阅邮件。邮件不含广告并尽量提供干货。


## Java图形界面

Java 在图形用户界面和桌面程序方面的发展可以说是一段悲伤的历史。Java 1.0中图形用户界面（GUI）库的原始设计目标是让用户能在所有平台提供一个漂亮的界面。但遗憾的是这个理想没有实现。相反，Java 1.0抽象窗口工具包（AWT）在所有平台都表现平平，并且有诸多限制;您只能使用四种字体。另外， Java 1.0 AWT 编程模型也很笨拙且不面向对象。我的一个曾在 Java 设计期间工作过的学生道出了缘由：早期的 AWT 设计是在仅仅在一个月内构思，设计和实施的。不得不说这是一个“奇迹”，但同时更是“设计失败”的绝佳教材。

在 Java 1.1 版本的AWT中 情况有所改善，事件模型采用了更加清晰的面向对象方法，并添加了JavaBeans，致力于面向易于创建可视化编程环境的组件编程模型（已废弃）。

Java 2（Java 1.2）通过基本上用 Java基类（JFC）替换所有内容来完成从旧Java 1.0 AWT的转换，其中GUI部分称为“Swing”。这是一组丰富的JavaBeans，它们创建了一个合理的GUI。修订版3（3之前都不好）比以往更适用于开发图形界面程序。

Sun 在图形界面的最后一次尝试，称为 JavaFX。当 Oracle 收购 Sun 时，他们将原来雄心勃勃的项目（包括脚本语言）改为库，现在它似乎是Java官方唯一还在开发中的UI工具包（参见维基百科关于JavaFX的文章） - 但即使如此。JavaFX 似乎最终后也失败了。

现今 Swing 依然是 Java 发行版的一部分（只接受维护，不再有新功能开发），而Java现在是一个开源项目，它应该始终可用。此外，Swing 和 JavaFX 有一些有限的交互性。这些可能是为了帮助开发者过渡到 JavaFX。

桌面程序领域似乎从没勾起 Java设计师的野心。最终，Java 没有在图形界面取得该有的一席之地。另外，曾被大肆吹嘘的 JavaBeans 也没有获得任何影响力。（许多不幸的作者花了很多精力在Swing上编写书籍，甚至只用JavaBeans编写书籍）。Java图形界面程序大多数情况下仅用于 集成开发环境（IDE）和一些企业内部应用程序。您是可以使用 Java 开发图形界面，但这不是 Java 最擅长的领域。如果你必须学习 Swing，它可以在 *Thinking in Java*，第4版（可从www.OnJava8.com获得）和其他专门的书籍中学习。。


<!-- 分页 -->
<div style="page-break-after: always;"></div>