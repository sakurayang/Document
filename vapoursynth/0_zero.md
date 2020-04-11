# 第零章 零之入门

<!-- toc -->

## 0.1 介绍

关于Vapoursynth是什么这里就不多说了，主要还是讲一下安装与使用方法

### 0.1.1 注意事项

 - 对Python的一些名词及语法有粗浅的了解，包括但不限于 变量、函数调用、命名空间、模块引用
 - 一丢丢的命令行使用基础
 - 本文只是简单地介绍，并不会多作深入
 - 建议将常用脚本存为模板文件
 - 本文中的`必填项/必填参数`以 **粗体** 表示，`非必填项/选填参数`以 *斜体* 表示
 - Vspoursynth的文档十分少，也不太完备，遇到问题大胆猜想，小心验证，注意控制变量
 - 人外有人天外有天，本文不是最好的。

### 0.1.2 准备物品
 - [ ] 你的脑子
 - [ ] 一台可以用来编辑代码并压制视频的设备
 - [ ] 文本编辑器，如 [Notepad++](https://notepad-plus-plus.org/) / [Notepad3](https://www.rizonesoft.com/downloads/notepad3/) ，==不要用Windows自带的记事本==
 - [ ] 搜索引擎
 - [ ] Python 3.8 +
 - [ ] VpaourSynth r49 +
 - [ ] x264或ffmpeg
 - [ ] *可选* Vpaoursynth Editor (自行百度)

由于安装Python与VapourSynth的步骤比较繁琐且容易出错，我魔改了个懒人包

下载：
 - [Google Drive](https://drive.google.com/open?id=1sLTF5cjP5PTsligmYVWnKJqSjxXQzxls)
 - [微云](https://share.weiyun.com/5PyzHDP)
 - [百度](https://pan.baidu.com/s/1XgKSOo-gfmDCkr_s0J9A2w) k62u

## 0.2 安装

当你下载好上面的懒人包解压后你会看到如下的目录结构
```text
.
├── scripts                          | 一些脚本
├── settings                         | 设置文件，请不要动这个文件夹内的东西
├── python-3.8.2.amd64               | Python与Vapoursynth核心文件夹
├── license.txt                      | 授权文件，请务必保留
├── WinPython Command Prompt.exe     | cmd命令行环境
├── WinPython Interpreter.exe        | 命令交互式调试
└── WinPython Powershell Prompt.exe  | powershell命令行环境
```

安装完了

## 0.3 使用

### 0.3.1 使用前的介绍

打开`python-3.8.2.amd64`文件夹，你会看到如下的文件（无关文件已省略）

```text
python-3.8.2.amd64/
├── vapoursynth64/      | 滤镜、插件文件夹
│   ├── coreplugins/    | 自动加载的滤镜与插件
│   ├── plugins/        | 需要手动加载的滤镜与插件
│   └── unuse/          | 滤镜与插件库
└── VSPipe.exe          | 将vpy转换成视频的东西
```

我已经把一些对字幕组来说常用的插件放到自动加载的文件夹里面了，一些不常用的放在滤镜库里面，避免混乱。

```text
vapoursynth64/  
├── avcodec-57.dll      | avcodec插件
├── avformat-57.dll     | avformat插件
├── avisource.dll       | AviSource滤镜，用于加载源文件
├── AvsCompat.dll       | AvsCompat滤镜，用于加载Avs脚本与滤镜
├── avutil-55.dll       | Avutil滤镜，用于视频的基本处理
├── ffms2.dll           | FFMS2滤镜，用于加载源文件
├── ffms2.lib           | 同上
├── ffmsindex.exe       | 同上，用于索引
├── libgcc_s_seh-1.dll  | 插件
├── libHalf.dll         | 插件
├── VSFilter.dll        | VSFilter (64 bit)
├── VSFilterMod.dll     | VSFilterMod (64 bit)
├── vslsmashsource.dll  | L-SMASH滤镜，用于加载源文件
└── Yadifmod.dll        | 滤镜，用于反交错
```

unuse里面的一些滤镜例如waifu2x等可能有人会用到，嘛……Do It Yourself

### 0.3.2 开始使用

随便拿一个视频和与之配套的字幕

在开始处理之前，你需要确认以下几点：
 - [ ] 你的字幕是`UTF-8 With BOM`或者`带签名的UTF-8`，当有`UTF-8 Without BOM`的时候，选择`UTF-8`，总之要带BOM。
 - [ ] 你的视频与字幕文件的完整路径，如`D:\xxx\yyy\zzz.mp4`中，==不得出现非英文字符，不得出现空格==。(即使你的vpy文件改了编码也不行，这可能是个Bug)。

然后新建一个py文件，假设文件名是`test.py`，在其中写下


```python
# -*- coding:utf8 -*-
# ↑上面这一行必须写，而且必须写在开头，其他注释不用
import vapoursynth as vs
# 初始化
core = vs.get_core()
# 设定缓存为 1G
core.max_cache_size = 1000

# 将这里改成你视频和字幕文件的完整路径，下同
source = r"D:\e\f.mp4"
sub_file = r"D:\e\f.ass"

# 加载视频文件
src = core.lsmas.LWLibavSource(source, threads=0)
# 将字幕放到视频中
sub = core.vsfm.TextSubMod(clip=src, file=sub_file)
# 将视频变成YUV420 8bit bt.709 (B站投稿标准) 以免某些奇怪的颜色出现
video = core.resize.Bicubic(source, format=vs.YUV420P8, matrix_s="709")

#输出视频
video.set_output()
```

然后打开一个命令行窗口(Win + R 输入cmd后回车)

然后将`VSpipe.exe`拖进去，按一下空格，然后将你刚才写好的py文件也拖进去，然后在输入一些东西，完成品如下

```cmd
# 使用ffmpeg
D:\xxx\yyy\VSpipe.exe D:\a\b\test.py -p -y - | ffmpeg -i - D:\a\b\out.mp4

# 使用x264
D:\xxx\yyy\VSpipe.exe D:\a\b\test.py -p -y - | x264 --demuxer y4m -o D:\a\b\out.mp4 -
```

啥？你说你没有x264？打开你小丸工具箱的安装目录，`D:\xxx\yyy\小丸工具箱rev194\tools\`，有一个tools目录，打开它，翻到最下面，把`x264_64-8bit.exe`像刚刚一样拖进去

然后在你电脑风扇的一阵狂转后，完成了。要注意的是，视频没有声音，请自行使用小丸之类的工具把声音压进去


---
最后修改

Gerardyang

20200411

本文无法遵守996 License

<a rel="license" href="https://creativecommons.org/licenses/by-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">知识共享署名-相同方式共享 4.0 国际许可协议</a>进行许可。