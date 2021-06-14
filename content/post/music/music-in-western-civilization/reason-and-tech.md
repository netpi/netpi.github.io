---
title: "〇，读《西方文明中的音乐》的初衷与相关博客影音技术的整理 ｜ 东泽读《西方文明中的音乐》"
date: 2021-04-27T12:57:21+08:00
categories: 
- 西方文明中的音乐
tags:
- 音乐
- blogtech
audio: true
cover_p: https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/2088t.png
---

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/2088t.png)

<!-- Nomos -->

[诺姆（Nomos）]:https://en.wikipedia.org/wiki/Nomos_%28music%29
[酒神赞歌（Dithyramb）]:https://en.wikipedia.org/wiki/Dithyramb





## 阅读《西方文明中的音乐》初衷与初度感受

1. 认知历史可有不同的线索，以王朝更迭的政治为线索；交换媒介的货币为索线；改变生活的科学为线索等等；同样的，文学、绘画、音乐、哲学等等艺术皆可作为认识历史的线索。而音乐，则是我本次认知历史的一条线索。我将在一段段旋律、故事与思考中，拾起一每一块历史图景的碎片。
2. 艺术修养包括了技能水平与艺术知识。本书内容属于后者。
3. 音乐是一门声音的艺术；声音在介质中以波的形式传递，被我们的耳膜接收，将声音信号转化为电信号在神经元的突触间传导，最终使我们的肉身作出行为。这其中涉及物理学、数学、脑科学等等，探索这其中的奥秘，一定很有趣。
4. 一个人的人生选项越多，就越自由。对于耳朵，如果从古至今的音乐类型都成为了它的选项，它就是自由的耳朵。
5. 这本探讨艺术之学术的书，让我感受到了学术之艺术；我喜欢学术，也喜欢艺术。

目前我读完了第一章节《古希腊》，我的感受是「很对胃口」；作者从不同的角度对古希腊音乐进行了非常全面的探讨，包括美学、历史背景、音乐格局的形成、乐器、音乐与社会学、音乐与科学等等。信息密度巨大，20 页的内容我连续阅读了两遍，加之查询资料、消化理解与整理笔记的时间，大概花费了15天（120小时）左右的时间。

## 影音技术接入博客

写博客是我对于知识的最终输出。为了更好的表达，我会在博客中直接插入音乐与视频资料。这个过程并不是很顺利，就古希腊音乐类型
比如[诺姆（Nomos）]、[酒神赞歌（Dithyramb）]在国内的音乐平台上资料极少。国外的 Spotify 和 Youtube 上倒是有一些。

因此为了让墙内的朋友可以在阅读时直接感受影音，我利用一些开源技术将影音资料整理到博客中。

**音频资料的整理：** 
1. [spotDL/spotify-downloader](https://github.com/spotDL/spotify-downloader) 将 Spotify 音频同步到本地
2. [DIYgod/APlayer](https://github.com/DIYgod/APlayer) 作为音频播放器，接入到博客中。

效果：
{{% audio artist="Petros Tabouris Ensemble" name="诺姆 - Nomos in Dorios Harmonia [kithara]" url="/audios/2.mp3" mini="false" cover="https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/y2jww.png" %}} 

或者

{{% audio artist="Petros Tabouris Ensemble" name="Nomos in Dorios Harmonia [kithara]" url="/audios/2.mp3" mini="true" cover="https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/y2jww.png" %}} 

<br>

**视频资料的整理：** 
 1. 使用 [Softorino YouTube Converter 2](https://softorino.com/youtube-converter/) 将 YouTube 视频同步到本地
 2. 上传至哔哩哔哩，我创建了一个频道： [「方文明中的音乐」](https://space.bilibili.com/89673392/channel/detail?cid=183523) 

效果：

{{< bilibili BV1Pf4y1p73k >}}

以上效果 UI 相对简陋，但是功能还是全面的，目前满足博客中的影音要求够用。后面有空考虑更新至首图 UI。

具体技术的接入方法，我后面有时间在来补上。

我暂时先将[「博客代码」](https://github.com/netpi/netpi.github.io) 以及 [「博客主题代码（包含接入方式）」](https://github.com/netpi/hugo-theme-ice)开源；

**衷心的感谢这些优秀项目的开发者们。**

也欢迎留言。