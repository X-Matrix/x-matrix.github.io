---
layout: post
title: "古典程序员"
categories: 随想
---
最近看了David Heinemeier Hansson (DHH)关于对Vibe Coding的看法[^1] [^2]，有一些感触。DHH是Ruby on Rails的作者，[37signals](https://37signals.com/)的创始人。插一句，37signals就是那个著名的写了《[重来](https://book.douban.com/subject/30184215/)》 的公司。



从访谈也可以看出，DHH并不是拒绝AI编程的老古董，他也在用AI Coding工具在辅助编程，他提到的一些观点深有同感，我愿称DHH为古典程序员，有一种古典的厚重的美感。说几个深有同感的观点

# 编程的乐趣
编程是一种能以极低的试错成本亲手来构建世界的行为。通过编写代码，可以创造出符合自己想法的世界，并且（基本）不会对物理世界和人造成伤害。编程确实是一种可以带来极大乐趣的行为，你可以是这个世界的暴君、仁君、无赖，并且可以几乎实时的反馈。DHH也提到，他之所以选择编程而不是成为一名项目经理，是因为写Ruby真的让人开心。作为程序员能够理解DHH编程的快乐，作为人，也可以理解Vibe Coding的快乐。想象一下，你在指挥AI编程，时间久了不再会写代码，是不是有点像你在脉脉上吐槽的你的老板？<span class=emoji>😂</span>


# 如何学习
DHH提到另外一个点是如果你一直在Tab，如何学到新东西，学不到的话如何修改，「编辑和修正代码的能力建立在是否具备创作能力之上，就像编辑一本书的人通常也要具备写作能力」。

之前有一年学习一门编程语言的计划，学习的方法是对着手册敲入示例代码，在这个过程中了解语言的特性和用法。但是这个计划在2024年停止了，因为随着Copilot、Cursor等AI编程工具的出现，看手册的效率太低了,我会选择做一个简单的项目，用Copilot辅助，问「实现类似Python中的协程用TypeScript如何实现」，获取答案后手动敲入代码调试来理解这部分知识。所以，我非常赞同DHH的观点，你可以不写代码，但是你要能写代码。虽然现在24h联网、本地模型部署都逐渐常态化，但是总有特殊情况，在无法使用AI怎么办，如果遇到[全频段阻塞干扰](https://book.douban.com/subject/3571732/) 那种极端情况怎么办？最近遇到一个例子就是平时做AI做翻译，觉得也没啥不方便，但是在会议场景下遇到外语就很懵。

# 古典还是流行
和音乐一样，结构严谨的古典乐和旋律简单的流行乐各有其美，并不是非此即彼。代码本身是对物理世界的简单描述，大部分时候并不需要复杂的结构和十分严谨的逻辑，可以在大量的限制下完成任务就可以了。但是，构建代码世界的基座，比如[ffmpeg](https://ffmpeg.org/)  ，需要用古典的方式来构建。
![ffmpeg](/assets/img/ffmpeg.jpg "ffmpeg")

最近看到一个让人难绷的笑话，真·一代人有一代人信仰 <span class=emoji>😊</span> 但是，古典程序员手写的代码还真比AI优秀。
![vibe coding joke](/assets/img/vibe_coding_joke.png "vibe coding joke")

# 对Vibe Coding的态度
无条件拥抱并且使用

无条件采纳能够理解的代码

调试和追问无法理解的代码，在过程中补充盲区。



---
{: data-content="footnotes"}
[^1]: [DHH on AI, Vibe Coding and the Future of Programming](https://thenewstack.io/dhh-on-ai-vibe-coding-and-the-future-of-programming/)

[^2]: [DHH: Future of Programming, AI, Ruby on Rails, Productivity & Parenting \\| Lex Fridman Podcast #474](https://www.youtube.com/watch?v=6b1a3d9c7f4)