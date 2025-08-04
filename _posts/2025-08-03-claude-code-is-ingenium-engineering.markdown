---
layout: post
title: "Claude Code is Engineering rooted in Ingenium"
categories: agent
---

Claude Code火遍Youtube、X、知乎、B站，甚至小红书，哪哪都是她，想不看都不行。于是下载了使用下，居然还不错，Claude家出品必属精品。在不长的使用体验中，有几个不错的体验：
- 可以快速了解CodeBase，如果写新项目，这种CLI的方式确实有点难受，当然CC也有VSCode的插件，不过我还没体验；
- 形成执行计划，如果开了`Bypass Permissions mode` 后，可以一路执行下去；
- 成功率很高，表现在两个方面：
    - 整个流程基本不怎么报错，看来工程做了很多
    - 代码可用性很高，我用的是Claude-code-router[^1]，接入了gpt-4.1、Claude-3.7，模型的能力差距还是挺大的，4.1有时候连python的缩进都是错的。所以，Claude Code的良好变现是建立在优秀模型的基础上的。
- 如果集成到GitHub Actions[^2]中，酷炫又提效

体验了后，又回头去看了眼Claude Code best practices[^3]，发现列出的使用场景也主要在前期项目了解、修复、部署为主，没怎么提到从头build新项目。
<figure>
  <img src="/assets/img/claude_best_practices.png" alt="Claude Code best practices" title="Claude Code best practices">
  <figcaption style="text-align:center;color:#888;">Claude Code best practices</figcaption>
</figure>


出于从小拆解玩具的本能，必须要了解下工作原理，虽然Claude Code本身是闭源的，但是社区已经做了逆向工程[^4]，得以一窥其中的工作原理。

<figure>
  <img src="/assets/img/claude_code_architecture.png" alt="Claude Code architecture" title="Claude Code architecture ">
  <figcaption style="text-align:center;color:#888;">Claude Code architecture （Claude绘制）</figcaption>
</figure>

整体架构相当完整，解决了上下文管理、鉴权、工具选择执行、subagent管理等较难的问题，而且使用起来体验还错，确实对得起Ingenium（engineering的拉丁语词源[^6] [^7]）。具体的模块在逆向工程的文档中有详细的介绍，就不复述其中的细节。

总体看下来，有很多Cline[^5]的影子
- 和Cline很相似的点：
    - 引入了基础的工具，包括文件操作、搜索等，这部分几乎一样，也好理解，写代码的动作无非也就这些，工具的执行方式比较类似；
    - 上下文注入和恢复机制，这部分的相似度也极高，不过Claude Code做得更加细节；
    - 任务规划，相似度也比较高，在这部分上，Coding Agent的实现方式也大差的；
    - 都没有对CodeBase构建索引，而是直接使用文本搜索工具来实现定位，Copilot、Continue、Windsurf等都是对CodeBase构建索引来实现定位的，这样的好处是比较省Token，Cline在文本搜索的基础上做了AST，可以检索到函数签名之类的。Claude Code选择这种方案猜测无非两个原因：
        - 目前的模型能力和上线文都足够强大，文本搜索的结果已经足够好，且不差钱；
        - 构建索引耗时，体验不太好。
- 不同点：
    - 上下文管理是很优秀的，什么时候该压缩，怎么压缩，看起来做得挺好的，这部分需要重点学习下的，所有的Agent中这部分都不能避免。关于内容是用原生的好还是压缩好，其实也没有共识，需要更多的研究；
    - 记忆管理模块做的也很细致，个人理解，Agent中这部分数据其实是结构化的，需要也应该做更加精细的处理，比如只记录状态变更，而不是每次都记录全部内容。

顺便提一句，Claude Code在多Agent的并发做得也没有很好，在[Claude Code best practices](https://www.youtube.com/watch?v=gv0WHhKelSE)演讲的答疑阶段也提到了这点。其难度在于，需要有一个中心化的管理协调模块来实现，这必然涉及到不同任务之间的冲突和撤回等，想象下你和同事的代码冲突就知道了。不过，在实践中可以尝试用[git-worktree](https://git-scm.com/docs/git-worktree)开多个feature分支来实现，没有实践过，但从工作原理上可行。   <span class=emoji>🤞</span>

EOF


---
{: data-content="footnotes"}

[^1]: [Claude-code-router](https://github.com/musistudio/claude-code-router)
[^2]: [Building headless automation with Claude Code](https://www.youtube.com/watch?v=dRsjO-88nBs)
[^3]: [Claude Code best practices](https://www.youtube.com/watch?v=gv0WHhKelSE)
[^4]: [Claude_Code_Agent系统完整技术解析.md](https://github.com/shareAI-lab/analysis_claude_code/blob/main/claude_code_v_1.0.33/stage1_analysis_workspace/Claude_Code_Agent%E7%B3%BB%E7%BB%9F%E5%AE%8C%E6%95%B4%E6%8A%80%E6%9C%AF%E8%A7%A3%E6%9E%90.md)
[^5]: [Github-Cline](https://github.com/cline/cline)
[^6]: 关于为啥中文Blog起了个英文标题  <span class=emoji>😹</span>  
[^7]: [Engineer](https://en.wikipedia.org/wiki/Engineer) 
