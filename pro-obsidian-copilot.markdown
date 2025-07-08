---
layout: page
title: "obsidian-copilot"
---


[该项目](https://github.com/X-Matrix/obsidian-copilot)基于[logancyang/obsidian-copilot](https://github.com/logancyang/obsidian-copilot) 迭代 感谢原作者的贡献💙


基于自己的需求做了定制，主要包括几个方面：
- [x] i18n：对配置进行了国际化处理，方便配置
- [x] 本地化：对会员功能做了部分本地化处理，方便接入本地模型和私有模型进行使用
    - [x] 意图识别的本地化
    - [ ] 搜索的本地化，使用`playwright`实现，直接使用本地浏览器进行搜索，总体功能实现，易用性需要进一步提升，需要优化更加简单化的配置
    - [x] 网页内容的本地化，使用`playwright`实现，直接使用本地浏览器进行网页内容的获取，并且做了readability处理，方便阅读和LLMs使用
- [ ] query改写
- [ ] 文本向量化的优化
    - [ ]  本地化多模态索引
    - [ ]  优化索引构建，主要的方向graphrag
- [ ] 更多远程tools的接入
    - [ ] wikipedia的搜索和内容获取
    - [ ] arxiv的搜索和内容获取
    - [ ] 其他
- [ ] 知识库的服务化，个人知识库转成服务化的形式，方便LLMs和其他用户使用