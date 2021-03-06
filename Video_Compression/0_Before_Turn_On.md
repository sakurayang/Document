# 第零章 在打开之前

> 本章主要介绍一下压制所需要的东西
>
> 共942字
>
> 预计阅读时间 <3 min

---

<!-- toc -->

## 0.1 什么是压制

`压制(Compression)`指将一个多媒体文件(Media)通过压缩算法使其体积变小

其分为`音频压制` `视频压制` `图像压制`，对应三种不同的压缩算法种类，其编码器和编码原理也**完全不同**，即使视频是由一系列的图像组合而成，但是其算法也和图像压缩有着根本性的不同。我们需要了解的是前两个，`音频压制`与`视频压制`。

---

## 0.2 为什么要研究压制

在解释这个问题之前先来了解一下一些概念

`无损压制(Lossless Compression)` 从英文意思可以看出来，无损并不是真的无损，只是看上去和听上去无损而已，举个例子：

原片：AAAAAAAAAABBCCDDDEEFG

假设每一个字母是一帧，你可以看到，上面的A持续了10帧，那么就有10张包含着A的图像放在这个视频里面，那么这就浪费了

压制后：A---------ABBCCD-DEEFG

那么我可以把中间那些全丢掉，留下首尾两帧，这就节省了很大空间了

当然，这只是一个通俗点的比喻，实际上的编码过程比这个复杂很多，在这里就不说了

回到问题上来，这当然只是其中一个原因

然后我们来说一下另一个原因

在以前互联网还没有现在这样的高速互联网的时候，传输带宽是有限的，于是就需要尽量降低视频体积，而又保证质量，这就是最主要的一个原因了。而研究压制主要是研究两个方面

- 如何在保证质量没有太大损失的同时将体积尽量减小

- 如何在有限时间和有限资源的情况下来进行压制

  > 有限时间指的是在肉眼看不出差别的情况下，使用何种方式能够让压制时间最短
  >
  > 有限资源指的是在有限的内存，CPU性能之内，使用何种方式能使压制质量高而压制时间短

并不是说电脑不好就不能压制，你拿一台I3 2U 512M的机子过来一样能压制

然后回到现在，的确互联网放开了，但是你上传一个三分钟10G的视频，肯定会被二压的，所以本教程研究的是**如何压制才能投稿到b站后不被二压。**

---

## 0.3 怎么压制

压制一般分为以下这几个步骤

```Text
       拆分              分析              检查
原片----------->视频-------------->压制-------------->成片
```

拿到原片之后，先对视频和音频进行拆分，这样方便压制，也方便整合

然后对视频进行分析，主要会有以下几种情况

- 静态画面居多 如杂谈，歌回一类的

- 动静参半 如普通的日常视频，老爱那种

- 动态画面较多 如歌曲MV 游戏实况一类的

这几类后面的章节会分开来讲的

关于软件的调用流程，在后面的章节也会详细的讲到

---

## 0.4 要准备什么

- [ ] [小丸工具箱](https://maruko.appinn.me/index.html)
- [ ] [32位的MEGUI](https://sourceforge.net/projects/megui/files/megui-stable/2896/MeGUI-2896-32.zip/download)
- [ ] *可选* [64位的MEGUI](http://gerardyang.hk.ufileos.com/megui.tar.xz)
- [ ] *可选* [64位的AviSynth滤镜](http://gerardyang.hk.ufileos.com/64%E4%BD%8D%E6%BB%A4%E9%95%9C.tar.xz)

---

最后修改

Gerardyang

2019.4.23

本文无法遵守996 License

修改历史：

190423 升级CC-BY-SA协议

190418 开始动笔

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">知识共享署名-相同方式共享 4.0 国际许可协议</a>进行许可。