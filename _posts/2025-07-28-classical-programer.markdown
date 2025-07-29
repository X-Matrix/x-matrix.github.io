---
layout: post
title: "古典程序员"
categories: 随想
---

最近看了 David Heinemeier Hansson (DHH) 关于 Vibe Coding 的访谈[^1][^2]，颇有感触。DHH 是 Ruby on Rails 的创造者，也是 [37signals](https://37signals.com/) 的联合创始人（顺带一提，37signals 正是那家以《[重来](https://book.douban.com/subject/30184215/)》一书闻名的公司）。

从访谈中可以清晰地看到，DHH 绝非抗拒 AI 编程的老古董。他本人也在使用 AI 工具辅助编程。他提出的某些观点深得我心，我愿称他为“古典程序员”——其理念中蕴含着一种古典而厚重的美感。以下是几个引起我强烈共鸣的点：

# 编程的乐趣
编程是一种能以极低试错成本亲手构建世界的行为。通过代码，你能创造一个符合自己心意的世界，且（通常）不会对物理世界或他人造成伤害。编程确实能带来极大乐趣：你既可以是这个世界的暴君、仁君，也可以是无赖，并能获得近乎即时的反馈。DHH 提到，他选择编程而非项目管理，正是因为“写 Ruby 真的让人开心”。作为程序员，我理解 DHH 的快乐；作为人，我也理解 Vibe Coding 的诱惑。但想象一下：长期依赖 AI 输出代码，自己不再动手编写，这像不像你在脉脉上吐槽的那些只会动嘴的老板？<span class=emoji>😂</span>

# 如何学习
DHH 提出的另一个关键点是：如果你总是在按 `Tab` 键（接受 AI 建议），如何学到新东西？学不到又如何修正错误？“编辑和修正代码的能力，建立在是否具备创作能力之上。就像编辑一本书的人，通常也要具备写作能力。”

我曾计划每年学习一门新语言，方法是照着手册敲示例代码，以此理解语言特性和用法。但这个计划在 2024 年暂停了——随着 Copilot、Cursor 等 AI 工具的兴起，阅读手册的效率显得太低。现在，我更倾向于做一个小项目，借助 Copilot 辅助。例如，直接问“如何用 TypeScript 实现类似 Python 的协程？”，得到答案后手动输入、调试，以此理解相关知识。因此，我非常赞同 DHH：你可以不写代码，但你必须**能**写代码。如今，24 小时联网、本地部署模型已成常态，但总有例外：万一无法使用 AI 怎么办？遭遇《[全频段阻塞干扰](https://book.douban.com/subject/3571732/)》式的极端情况怎么办？一个切身体会是：日常依赖 AI 翻译没觉得不便，但在需要即时交流的会议中遇到外语，瞬间就懵了。

# 古典还是流行？
如同音乐领域，结构严谨的古典乐与旋律简单的流行乐各有其美，并非非此即彼。代码本身是对物理世界的简化描述，大部分场景下无需复杂结构或极度严密的逻辑——能在约束条件下完成任务即可。然而，构建代码世界的基石（例如 [ffmpeg](https://ffmpeg.org/)）仍需用“古典”的方式精心打造。
![ffmpeg](/assets/img/ffmpeg.jpg "ffmpeg")


# 对 Vibe Coding 的态度
1.  **无条件拥抱并使用**  
2.  **采纳能理解的 AI 生成代码：** 对于看得懂、信得过的部分，直接采纳；
3.  **调试并追问不理解的代码：** 遇到无法理解的生成代码，调试和追问，填补知识盲区。

---
{: data-content="footnotes"}
[^1]: [DHH on AI, Vibe Coding and the Future of Programming](https://thenewstack.io/dhh-on-ai-vibe-coding-and-the-future-of-programming/)
[^2]: [DHH: Future of Programming, AI, Ruby on Rails, Productivity & Parenting \\| Lex Fridman Podcast #474](https://www.youtube.com/watch?v=6b1a3d9c7f4)