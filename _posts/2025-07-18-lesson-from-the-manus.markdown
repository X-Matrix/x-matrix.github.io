---
layout: post
title: "从manus的教训中学到的教训"
categories: 随想
---

Manus的Yichao最近发了一篇Blog[Context Engineering for AI Agents: Lessons from Building Manus
](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)，总结了做Manus的过程中的一些教训。从构建Agent来看，这些确实是教训，但其实还是不够苦涩，更苦涩的教训还没有说（或者不好说）。毕竟，当被人问你缺点的时候，你可能会说「我很粗心」，而不会说「我很笨」。

# 教训是什么
文章总结的教训，大致是以下几个方面：
- 使用已有的模型做Context Engineering，而不是从头训练自己的模型；
- 关注KV（Key-Value）Cache，这个关系到钱，从商业角度角度来说这个是一个很大的问题，商业的目的肯定是要赚钱的。为了KV Cache的有效，就需要保持Context的不变，即最好只是追加而不破坏已有的Context，具体设计提到：
    - 不要破坏上文，有变动的信息在下文追加；
    - 在使用的工具的时候，列出工具，在下文使用的时候，只做屏蔽而不是删除工具的列表；
- 上下文压缩的问题，持续的上下文很有可能会超过模型的上下文长度限制，如果压缩上下文又可能会带来信息的丢失（关于上下文的问题，cognition.ai的博客也有讨论[^1]）。采用外挂的系统来解决上下文过长的问题，从而避免把原始的内容直接无脑堆叠在上下文。这段略微语焉不详，个人理解是构建一个外挂的系统要解决：
    - 可以快速准确地检索到信息（高效的Rag系统？）；
    - 对象存储，在上下文中只存储链接，内容本身存储在文件系统中，按需读取；
- 通过背诵来控制注意力： 重要的事情说多遍。其实人类更加能理解，老板交给你的任务，如果不过问说明不重要😊；
- 把错误的信息放在上下文：这个确实很重要，失错的信息本身是一个很重要的信息，比如[Cline](https://cline.bot/) 在设计之初就一直会把错误信息放在上下文中，避免重复尝试相同的错误；
- 减少Few-Shot：过多的Few-Shot会导致模型被带歪，这个在The Bitter Lesson[^2] 中提到过的人类总是试图把现有的经验教给Agent。


# 这些教训本质么
个人觉得不太本质，列了挺多的教训，其实归纳起来更加简单：
- 做Content Engineering，而不是从头训模型；
- 利用工程能力减少上下文的开销，不过重要的信息（比如错误）还是要放入上下文，该省省，该花花；
- 给模型以一定自由，要不然就降级成工作流了。

更简单的教训是：
- 虽然是AI时代，工程能力还是核心，好的模型加上好的工程能力，才能发挥出最大的效能，否则容易停留在DEMO阶段；
- Content Engineering很重要，什么信息何时分发很关键，这个让人想起了一位故友 [微软的Graph](https://learn.microsoft.com/zh-cn/graph/overview)

# 更本质的教训是什么
使用了一些也做了一些Agent类项目，对Yichao在Blog中提到教训深感认同，拍腿说强如Manus也有这么晚这么痛的领悟。不过还要说些构建Agent更苦涩的教训：
- 构建通用的Agent：

作为[有效加速主义支持者](https://zh.wikipedia.org/zh-hans/%E6%9C%89%E6%95%88%E5%8A%A0%E9%80%9F%E4%B8%BB%E7%BE%A9)，我完全相信在有生之年可以见到，但不是现在，理由是我们目前还没能做到完整反馈链路，让Agent真正自助工作。更多的是给出Meta方法，基于此使用模型和工具来完成任务，本质就是一种用自然语言描述的有一些容错弹性的工作流。Meta方法如何产生和迭代需要花大量的时间来解决,是通过上下文给到呢，还是利用RL构建一个内化的模型来实现？ The Bitter Lesson 中的教训是终极的教训，不过我们仍要活在当下，面对现实和客户。

作为一个不构建模型的应用商，需要对领域内的知识有足够了解才能构建出好用的产品。比如，Cursor的好用是对于软件开发流程的理解和对CodeBase的解析，这（目前来说）就不是一个通用方案可以解决。
- 工程的能力：

Agent系统本质还是一个系统，是系统就需要有设计，坏的设计会导致聪明的模型无法施展（社会系统也是如此）。很多工程上习以为常的方案，Agent的创业明星们可能要浪费1个月时间领悟。1个月领悟到了很聪明，但是为什么要浪费这一个月呢，你需要一个懂工程的同事。同时，Agent的构建链路长、环节隐蔽，模型本身容错性也不错，导致中间出了问题不会被轻易发现，这对工程能力的宽度也有更高的要求。


EOF

---
{: data-content="footnotes"}

[^1]: [Don’t Build Multi-Agents](https://cognition.ai/blog/dont-build-multi-agents)
[^2]: [The Bitter Lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)

