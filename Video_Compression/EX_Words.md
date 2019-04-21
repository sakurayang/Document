# 专有名词补充

> 本章主要介绍一些专业术语，专有名词
>
> 请用ctrl+f搜索关键词

---

## 解编码器

从广义上来说，编码是信息从一种形式或格式**转换为**另一种形式或格式的过程。解码，是编码的逆向。*加密也算是一种编码。*

**在这里我们主要解释数字音视频方面的解编码。**

`编码器(Encoder)`是一个电子元件、芯片、传感器、软件、算法或是将信息从一种格式或代码转换成另一种格式或代码的人。其主要目的是为了标准化、速度、压缩或加密。[^encoder]

`解码器(Decoder)`是一个电子元件，经常被用在单片机里面。用于将模拟信号视频转换成数字信号视频，其通常允许对视频特性的可编程控控制，如色温 锐度 亮度等。[^decoder]**解码器是编码器的反函数。**

*最常见的一个例子就是声卡与显卡*

**在这里提及的所有解编码器都是软件解编码器。**

[这里](https://www.wikiwand.com/en/List_of_codecs)有一份解编码器列表

### 视频解编码器

> 视频解编码器是指能编码或解码视频数字数据信息流的设备或计算机程序

- `FFmpeg`是一个免费开源的软件集，可以进行音频及视频的录制，转码，串流(直播)的功能。[^ffmpeg]其包含以下这些主要的函数库。


  | 函数库名称 | 用途|
  | :--------- | :------------------------- |
  | libswresample[^libswresample]| 音频重采样|
  | libavresample[^libavresample]                    | 音频重采样，来自libav分支，和上一个类似                      |
  | libavcodec[^libavcodec]                          | 用于音视频解编码，所有的编码器从头构建，以确保最高效率       |
  | libavformat*(Lavf)*[^libavformat][^libavformat2] | 用于音视频封装以及解封装                                     |
  | libavutil[^libavutil]                            | 这是一个通用的辅助函数库，用于封装各部分都需要用到的函数，其包含了各种加解密算法以及压缩与解压缩算法 |
  | libpostproc[^libpostproc]                        | 用于老的h.263视频后处理                                      |
  | libswscale[^libswscale]                          | 用于视频以及图像缩放，像素长宽比的调整                       |
  | libavfilter[^libavfilter]                        | 用于加载音视频滤镜                                           |

  以及以下这些命令行工具，他们的用法会在进阶中讲到

  | 工具名            | 用途                                                         |
  | ----------------- | ------------------------------------------------------------ |
  | ffmpeg[^ffmpeg2]  | 用于转换音视频的格式，同时能够从视频采集设备采集视频并实时编码 |
  | ffplay[^ffplay]   | 一个简单的多媒体播放器，以及ffmpeg的函数库                   |
  | ffprobe[^ffprobe] | 用于分析多媒体信息                                           |

- `x264`是一个由VideoLAN开发的用于将视频流编码为`H.264/MPEG-4 AVC`格式的免费开源的软件函数库以及命令行工具[^x264]。*ffmpeg使用x264来解码H.264编码格式的多媒体流*。

- `x265`是一个由MulticoreWare开发的用于将视频流编码为`H.265/HEVC`格式的基于`x264`修改的免费开源的软件函数库以及命令行工具[^x265]。*ffmpeg以及[UHDcode](https://www.wikiwand.com/en/MulticoreWare)使用x265来解码H.265编码格式的多媒体流*。

- `QuickTime`是一种由苹果公司开发的可拓展的多媒体框架，能够处理各种格式的数字音视频，图像，全景图像以及交互式媒体。[^QT]

- `libaom`由Alliance for Open Media开发并用于解编码AV1编码格式[^codec]。

- `libvpx`由Google开发并用于解编码VP9编码格式[^codec]

- `EVE for VP9`由twoorioles开发并用于解编码VP9编码格式[^evevp9]

- `DivX`是一个用于解编码`H.264/MPEG-4 AVC`的商业软件[^divx]

- `Xvid`同上，是一个开源软件[^xvid]

---

### 音频编解码器

> 音频编解码器是指能编码或解码音频数字数据信息流的设备或计算机程序

- `ffmpeg`[^ffmpeg]

- `NeroAAC(Nero AAC Codec)`是一个用于解编码AAC格式(Advance Audio Coding)的免费工具集 [^neroaac]
- `QAAC(Quicktime AAC/ALAC Codec)`是一个基于Apple编码方式用于编码AAC以及ALAC的命令行工具[^qaac]，需要iTunes或者QuickTime的支持。
- `Fraunhofer FDK AAC(Fraunhofer FDK AAC Codec Library for Android)`是一个基于安卓系统开源并用于在安卓系统上解编码AAC编码格式音频的函数库。[^fdkaacenc]
- `faac（Freeware Advanced Audio Coder）`是一个包含了用于编码AAC的FAAC以及用于解码的FAAD2的软件[^faac]
- `iTunes`是一个由苹果公司开发的多媒体播放器，多媒体库，网络，以及手机管理的软件。能够支持多种常见编码格式的播放。[^itunes]
- `Lame(LAME Ain't an MP3 Encoder)`是一个用于将音频转换为MP3编码格式的开源免费软件[^lame]
- `L3enc(raunhofer l3enc)`是第一个能将PCM(.wav)编码格式转换为MP3的软件，早期的安卓系统曾采用[^l3enc]
- `libopus`用于解编码Opus编码格式的音频[^codec]
- `libvobis`用于解编码viobs(.ogg)格式[^libvorbis]
- `WME(Windows Media Encoder)`不解释（

---

## 编码格式

**编码格式≠视频格式**

**编码格式≠容器格式**

编码格式是指一个多媒体流文件的编码方式，根据其编码的算法不同，其性能以及使用场景也不同。

### 视频编码格式

- `H.264/AVC`通常以`.264`为后缀名
- `H.265/HEVC`通常以`.265`为后缀名
- `RealMedia`
- `vp8/vp9`通常被封装于`webm`容器中
- `av1`通常被封装于`webm`容器中
- `quicktime`通常以`.mov` `.qt`为后缀名
- `MPEG-TS`通常以`.mts` `.m2ts`为后缀名

### 音频编码格式

- `WAV(Waveform Audio File Format)`是一个由微软及IBM开发的无压缩数字音频编码格式。注意，**无压缩≠无损**。就像你把棉被塞到仓库里面，如果棉被本来就是坏的那拿出来还是坏的。通常以`.wav`为后缀名
- `ALAC(Apple Lossless Audio Codec)`是一个由苹果公司开发的无损压缩数字音频解编码格式，其能将`FLAC` `WAV`等的无压缩格式转换成无损压缩格式。[^alac]通常以`.alac`为后缀名
- `Monkey's Audio(APE)`通常以`.ape`为后缀名
- `AAC(Advance Audio Codec)`通常以`.aac`为后缀名
  - `AAC(MPEG-2 Part 7)`
  - `AAC(MPEG-4 Part3 shubpart4)`
    - `HE-AAC`
    - `AAC-LD(AAC-Low Delay)`
- `Opus`通常以`.opus`为后缀名，通常被封装在`webm`容器中
- `Vorbis(ogg)`通常以`.ogg`为后缀名
- `WMA(Windows Media Audio)`通常以`.wma`为后缀名
- `PCM(Pulse-code modulation)`即脉冲编码调变。以数字信息记录模拟信号，这样的到的音频信号会清楚且能用于分时多工系统(如现代的公共电话)，但是体积较大。通常以`.pcm`为后缀名
- `FLAC(Free Lossless Audio Codec)`是一个免费开源的无损压缩数字音频编码格式。通常以`.flac`为后缀名
- `AC3(Audio Codec 3,Advanced Codec 3,Acoustic Coder 3[这里区分一下， Adaptive Transform Acoustic Coding 3 是一种由索尼开发的格式])`是指杜比数字编码(Dolby Digital 或称AC-3)。通常被封装在`VOB`或`MPEG-TS`容器中
- `MP3(formally MPEG-1 Audio Layer III, MPEG-2 Audio Layer III)`是一种有损压缩数字音频编码格式。通常以`.mp3`为后缀名

---

## 封装格式

[这里](https://www.wikiwand.com/en/Comparison_of_video_container_formats)有一份视频容器表

封装格式，你可以理解为文件后缀名，就是那些`.mp4` `.avi`的东西

形象点就是不同的行李箱能装的东西不同以及装东西的方式不同

| 容器      | 后缀      | 描述                                                         |
| --------- | --------- | ------------------------------------------------------------ |
| MPEG-4    | .mp4      |                                                              |
| flv       | .flv/.f4v |                                                              |
| avi       | .avi      |                                                              |
|           | .mkv      |                                                              |
|           | .webm     |                                                              |
| RealMedia | .rm/.rmvb | rm被用于早期的网络传输，后来推出了支持可变码率的rmvb再后来由于技术落后被淘汰 |
|           | .cue      |                                                              |
|           | .vob      |                                                              |





---

## 视频名词

> 理解难度从上往下递增

- `profile`即配置文件，其针对不同的应用程序定义了不同的配置，这些被声明为配置文件代码(`profile_idc`)和在编码器种应用的一系列约束。这允许解码器识别解码该特定流的要求。一般来说有以下这些[^profile]

  > constraint 约束
  >
  > Progressive 渐进
  >
  > Predictive 前向预测性

  ​	*对非可适性视频编码而言有以下这些标准*

  - Constrained Baseline Profile (CBP, 66 with constraint set 1)

    ​	主要被用于低开销的应用场景，这种等级的profile通常被用于视频会议以及一些手机应用。他是BP MP HP之间的共有特征子集

  - Baseline Profile (BP, 66, 基线)

    ​	主要被用于需要额外数据以保持数据传输鲁棒性[^鲁棒性]的低开销应用场景，有时候在一些视频会议和手机应用中使用。该等级的配置在CBP的基础上增加了三个功能以保证传输稳定(或是用于其他目的例如低延迟多点的视频流合成)。自从2009年CBP被定义以来，该配置文件的重要性逐渐消失，所有CBP流也被视为BP流，所以共享相同的标识码(66)

  - Extended Profile (XP, 88, 额外)

    ​	被用于视频流文件，这个配置文件有相对较高的压缩能力以及一些额外的功能来确保对数据丢失和服务器媒体流切换的鲁棒性

  - Main Profile (MP, 77, 主要)

    ​	被用于使用DVB标准中定义的MPEG-4格式的标清数字电视广播。然而它并不用于高清电视广播，因为在2004年针对高清电视广播开发HiP之后，该配置文件的重要性已经消失。

  - High Profile (HiP, 100, 高)

  - Progressive High Profile (PHiP, 100 with constraint set 4)

  - Constrained High Profile (100 with constraint set 4 and 5)

  - High 10 Profile (Hi10P, 110)

  - High 4:2:2 Profile (Hi422P, 122)

  - High 4:4:4 Predictive Profile (Hi444PP, 244)

  - High 10 Intra Profile (110 with constraint set 3)

  - High 4:2:2 Intra Profile (122 with constraint set 3)

  - High 4:4:4 Intra Profile (244 with constraint set 3)

  - CAVLC 4:4:4 Intra Profile (44)

- `level`

- `NTSC`

- `PAL`

- `逐行扫描`

- `隔行扫描`

- `四比三下位变换`

- `DVR`

- `CBR`

- `VBR`

- `ABR`

- `2pass`

- `前向预测(Context-based)`

- `B帧 I帧 P帧`

- `运动补偿`

- `宏块`

- `熵编码(entropy encoding)`在信息学上来说是一种不依赖媒介具体特征的接近无损的数据压缩方式，熵编码通常与其他编码方式结合使用。[^entropyEnc]一种主要类型的熵编码方式是在输入的时候创建并分配一个唯一的无首位代码(prefix-free code)

- `前缀码(Prefix code)`是一种编码系统，通常为长度可变的，在其中的每一个前缀码都具备前置性质(prefix property)。也就是说，该编码是独立唯一且不能被其他编码所作为前置部分的，举个例子，编码集合`{1,32,75}`具备前置性质，但`{1,3,7,32,75}`不具备，因为`3`和`7`可以分别作为`32`与`75`的前置编码。这种被叫做无首位编码(PFC, prefix-free codes)。

  每一个前置码都是解码结果唯一的：给定完整准确的序列，接收方可以识别每个单词而不需要编码与单词之间做特殊标记。但是有解码结果唯一的代码不是前缀码; 例如，将前缀码进行逆转操作`(45->54)`仍然是解码结果唯一的（它是后缀代码），但它不一定是前缀代码。

  霍夫曼编码是该编码系统中的一种算法。[^prefixcode]

- `算术编码(Arithmetic Coding)`是一种无损数据压缩方式，同时也是一种熵编码的算法。[^算术编码]这个是一个完整的算法，可以单独开一章，这里就简单的说一下。算术编码是不同于其他熵编码的编码算法，其他的熵编码方法通常是把输入的消息分割为符号，然后对每个符号进行编码，而算术编码是直接把整个输入的消息编码为一个数，一个满足（0.0 ≤ *n* < 1.0）的小数n。举个简单的例子

  以`wiki`这一个字符串为例，一共有四个字符，使用二进制区间表示(00,01,10,11)

  - w: 25% [0,0.25) ==>[0.00,0.01)
  - i: 50% [0.25,0.75) ==>[0.01,0.11)
  - k: 25% [0.75,1) ==>[0.11,1.00)

  那么序列`ww`出现的区间是`[0,0.01*0.01)`，`wi`出现的区间是`[0.0001,0.01*0.11+0.0001)`，`wk`出现的区间是`[0.0011,0.01)`。依此类推，可以算出，`wik`出现的区间是`[0.00101，0.0011)`，`wiki`出现的区间是`[0.001011,0.0010101)`，我们使用`0.001011`作为其编码，可以轻易地逆向。

  下图采用自[维基百科](https://www.wikiwand.com/en/Arithmetic_coding)

  ![img](images/640px-Arithmetic_coding_visualisation_circle.svg.png)

- `CABAC(Context-based Adaptive Binary Arithmetic Coding)`[^cabbc]，即前文参考性自适应二元算术编码，是一种基于算术编码的在HEVC以及AVC编码中使用的熵编码方式。其分为三部分`Binarizer(二值化算法)` `Context Modeler(上下文模型)` `Arithmetic Coding Engine(算术编码引擎)` 。他首先将所有非二进制符号转换为二进制，编码器遍历每个比特来选择使用哪个概率模型，然后根据上下文信息来优化概率估计。最后用算术编码来压缩数据。[^cabbc]通常比CAVLC性能更佳。但不支持Baseline以及Extended profiles。

- `CAVLC(Context-based Adaptive Variable-Length code)`，适应性可变长度编码法，又被称为`UVLC`。是h.264的演算法机制，其对传统的霍夫曼编码进行了改进，因此在压缩效率上取得了相当大的进步。其支持所有的H.264 peofile。过程解释有点复杂（[^cavlc]

- `可视性视频编码(Scalable Video Coding, SVC)`是传统H.264编码的延伸，是H.264视频压缩标准附录G的名称，可以提升更大的编码弹性，并且有时间(帧速率)可适性(Temporal Scalability),空间(图片大小)可适性（Spatial Scalability）及信噪比/质量/品质可适性（SNR Scalability）[^ensvc][^cnsvc]三大特性，使得视频传输能在不同的网络带宽中使用。

## 音频名词



## 其他名词

- `ISO(International Organization for Standardization)`即国际化标准组织。其制定了一系列标准，包括但不限于电影播放，视频播放，文字，食品。

  ![1555759999551](images/1555759999551.png)

  这里的ISO表示的是遵循着`ISO/IEC 14496`标准

- `IEC(International Electrotechnical Commission)`国际电工协会，主要负责电气工程以及电子工程的国际标准制定

- `ITU-T(ITU Telecommunication Standardization Sector)`即国际电信联盟电信标准化部门。其制定了一系列用于远程通讯传输的多媒体标准，其中包括`ITU-T H.264`等

- `ITU-R(ITU Radiocommunication Sector)`国际电信联盟无线电通信部门

- [^鲁棒性]:`鲁棒性(robustness)`，是指控制系统在一定(结构，大小)的**参数扰动下**，仍能够维持其他某些性能的特性，也就是系统的健壮性。鲁棒控制方法适用于稳定性和可靠性作为首要目标的应用，同时过程的动态特征已知，且不确定因素的变化范围可以预估。**鲁棒性不同于稳定性**，稳定性是指控制系统在使它偏离平衡状态的**扰动消失之后** ，返回原来平衡状态的能力。举个例子，鲁棒性就像你种菜(物理)的时候，不会因为某一天浇水多了抑或少了，某一天出太阳了或下雨了而长不出来。稳定性就你给弹簧一个压力，你放手之后弹簧能回到原来的状态

- 

---

##脚注

[^codec]: [Wiki-Codec](https://www.wikiwand.com/en/List_of_codecs)
[^ffmpeg]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): **FFmpeg** is a [free software](https://www.wikiwand.com/en/Free_software) project consisting of a vast software suite of [libraries](https://www.wikiwand.com/en/Library_(computing)) and [programs](https://www.wikiwand.com/en/Computer_program) for handling video, audio, and other [multimedia](https://www.wikiwand.com/en/Multimedia) files and streams.
[^ffmpeg2]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *ffmpeg* is a command-line tool that converts audio or video  formats. It can also capture and encode in real-time from various  hardware and software sources such as a TV capture card.
[^ffplay]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *ffplay* is a simple media player utilizing [SDL](https://www.wikiwand.com/en/Simple_DirectMedia_Layer) and the FFmpeg libraries.
[^ffprobe]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *ffprobe* is a command-line tool to display media information (text, [CSV](https://www.wikiwand.com/en/Comma-separated_values), [XML](https://www.wikiwand.com/en/XML), [JSON](https://www.wikiwand.com/en/JSON)), see also [Mediainfo](https://www.wikiwand.com/en/Mediainfo).
[^libswresample]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *ibswresample* is a library containing audio [resampling](https://www.wikiwand.com/en/Resampling_(audio)) routines.
[^libavresample]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libavresample* is a library containing audio resampling routines from the [Libav](https://www.wikiwand.com/en/Libav) project, similar to *libswresample* from *ffmpeg*.
[^libavcodec]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libavcodec*is a library containing all of the native FFmpeg audio/video encoders and decoders. Most codecs were developed from scratch to ensure best performance and high code reusability.
[^libavformat]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libavformat* (Lavf)is a library containing demuxers and muxers for audio/video container formats.
[^libavformat2]: ["FFmpeg: Lavf: I/O and Muxing/Demuxing Library"](https://www.ffmpeg.org/doxygen/2.2/group__libavf.html). *ffmpeg.org*. Retrieved 21 October 2016.
[^libavutil]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libavutil* is a helper library containing routines common to different parts of FFmpeg. This library includes hash functions ([Adler-32](https://www.wikiwand.com/en/Adler-32), [CRC](https://www.wikiwand.com/en/Cyclic_redundancy_check), [MD5](https://www.wikiwand.com/en/MD5), [RIPEMD](https://www.wikiwand.com/en/RIPEMD), [SHA-1](https://www.wikiwand.com/en/SHA-1). [SHA-2](https://www.wikiwand.com/en/SHA-2), [MurmurHash](https://www.wikiwand.com/en/MurmurHash)3, [HMAC](https://www.wikiwand.com/en/Hash-based_message_authentication_code) MD-5, HMAC SHA-1 and HMAC SHA-2), ciphers ([DES](https://www.wikiwand.com/en/Data_Encryption_Standard), [RC4](https://www.wikiwand.com/en/RC4), [AES](https://www.wikiwand.com/en/Advanced_Encryption_Standard), AES-CTR, [TEA](https://www.wikiwand.com/en/Tiny_Encryption_Algorithm), [XTEA](https://www.wikiwand.com/en/XTEA), [Blowfish](https://www.wikiwand.com/en/Blowfish_(cipher)), [CAST-128](https://www.wikiwand.com/en/CAST-128), [Twofish](https://www.wikiwand.com/en/Twofish) and [Camellia](https://www.wikiwand.com/en/Camellia_(cipher))), [LZO](https://www.wikiwand.com/en/Lempel–Ziv–Oberhumer) decompressor  and [Base64](https://www.wikiwand.com/en/Base64) encoder/decoder.
[^libpostproc]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libpostproc* is a library containing older h263 based [video postprocessing](https://www.wikiwand.com/en/Video_postprocessing) routines.
[^libswscale]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libswscale* is a library containing video [image scaling](https://www.wikiwand.com/en/Image_scaling) and [colorspace](https://www.wikiwand.com/en/Color_space)/pixelformat conversion routines.
[^libavfilter]: [Wiki-FFmpeg](https://www.wikiwand.com/en/FFmpeg): *libavfilter* is the  substitute for vhook which allows the video/audio to be modified or  examined between the decoder and the encoder. Filters have been ported  from many projects including [MPlayer](https://www.wikiwand.com/en/MPlayer) and [avisynth](https://www.wikiwand.com/en/Avisynth)
[^x264]: [Wiki-X264](https://www.wikiwand.com/en/X264): **x264** is a [free and open-source](https://www.wikiwand.com/en/Free_and_open-source_software)[software library](https://www.wikiwand.com/en/Library_(computing)) and a [command-line](https://www.wikiwand.com/en/Command-line_interface) utility developed by [VideoLAN](https://www.wikiwand.com/en/VideoLAN) for encoding video streams into the [H.264/MPEG-4 AVC](https://www.wikiwand.com/en/H.264/MPEG-4_AVC) format.
[^x265]: [Wiki-X265](https://www.wikiwand.com/en/X265): **x265** is a [library](https://www.wikiwand.com/en/Library_(computing)) for encoding video into the [High Efficiency Video Coding](https://www.wikiwand.com/en/High_Efficiency_Video_Coding) (HEVC/H.265) [video compression](https://www.wikiwand.com/en/Video_compression) format
[^QT]: [Wiki-QuickTime]:(https://www.wikiwand.com/en/QuickTime): **QuickTime** is an extensible [multimedia framework](https://www.wikiwand.com/en/Multimedia_framework) developed by [Apple Inc.](https://www.wikiwand.com/en/Apple_Inc.), capable of handling various formats of [digital video](https://www.wikiwand.com/en/Digital_video), picture, sound, [panoramic images](https://www.wikiwand.com/en/QuickTime_VR), and [interactivity](https://www.wikiwand.com/en/Interactivity). 
[^evevp9]: [twoorioles](https://www.twoorioles.com/eve-for-vp9)
[^dvix]: [Wiki-DivX](https://www.wikiwand.com/en/DivX): **DivX** is a brand of [video codec](https://www.wikiwand.com/en/Video_codec) products developed by DivX, LLC. The DivX codec gained fame for its ability to [compress](https://www.wikiwand.com/en/Video_compression) lengthy video segments into small sizes while maintaining relatively high visual quality. There are three DivX [codecs](https://www.wikiwand.com/en/Codec); the original [MPEG-4 Part 2](https://www.wikiwand.com/en/MPEG-4_Part_2) DivX codec, the [H.264/MPEG-4 AVC](https://www.wikiwand.com/en/H.264/MPEG-4_AVC) DivX Plus HD codec and the [High Efficiency Video Coding](https://www.wikiwand.com/en/High_Efficiency_Video_Coding) DivX HEVC Ultra HD codec. 

[^xvid]: [Wiki-Xvid](https://www.wikiwand.com/en/Xvid): **Xvid** (formerly "**XviD**") is a [video codec](https://www.wikiwand.com/en/Video_codec)[library](https://www.wikiwand.com/en/Library_(computing)) following the [MPEG-4](https://www.wikiwand.com/en/MPEG-4)[video coding standard](https://www.wikiwand.com/en/Video_coding_standard), specifically [MPEG-4 Part 2 Advanced Simple Profile](https://www.wikiwand.com/en/MPEG-4_Part_2) (ASP). It uses ASP features such as [b-frames](https://www.wikiwand.com/en/B-frame), global and quarter pixel [motion compensation](https://www.wikiwand.com/en/Motion_compensation), [lumi masking](https://www.wikiwand.com/en/Lumi_masking), [trellis quantization](https://www.wikiwand.com/en/Trellis_quantization), and [H.263](https://www.wikiwand.com/en/H.263), MPEG and custom [quantization matrices](https://www.wikiwand.com/en/Quantization_(image_processing)). 

[^lame]: [Wiki-Lame](https://www.wikiwand.com/en/LAME): **LAME** is a software [encoder](https://www.wikiwand.com/en/Encoder) that converts audio to the [MP3](https://www.wikiwand.com/en/MP3) file format.
[^l3enc]: [Wiki-L3enc](https://www.wikiwand.com/en/L3enc): **Fraunhofer l3enc** was the first public software able to encode [PCM](https://www.wikiwand.com/en/Pulse-code_modulation) ([.wav](https://www.wikiwand.com/en/WAV)) files to the [MP3](https://www.wikiwand.com/en/MP3) format. 
[^fdkaacenc]: [Wiki-FDKAACenc](https://www.wikiwand.com/en/Fraunhofer_FDK_AAC): **Fraunhofer FDK AAC** (Full title **Fraunhofer FDK AAC Codec Library for Android**) is an [open-source](https://www.wikiwand.com/en/Open-source_software)software library for [encoding and decoding](https://www.wikiwand.com/en/Codec)[Advanced Audio Coding](https://www.wikiwand.com/en/Advanced_Audio_Coding) (AAC) format audio
[^faac]:[Wiki-FAAC](https://www.wikiwand.com/en/FAAC): **FAAC** or **Freeware Advanced Audio Coder** is a software project which includes the [AAC](https://www.wikiwand.com/en/Advanced_Audio_Coding)[encoder](https://www.wikiwand.com/en/Encoder)**FAAC** and [decoder](https://www.wikiwand.com/en/Audio_decoder)**FAAD2**. 
[^itunes]:[Wiki-iTunes](https://www.wikiwand.com/en/ITunes): **iTunes** ([/ˈaɪtjuːnz/](https://www.wikiwand.com/en/Help:IPA/English))is a [media player](https://www.wikiwand.com/en/Media_player_(software)), media library, [Internet radio](https://www.wikiwand.com/en/Internet_radio) broadcaster, and [mobile device](https://www.wikiwand.com/en/Mobile_device) management application developed by [Apple Inc.](https://www.wikiwand.com/en/Apple_Inc.)  iTunes supports [WAV](https://www.wikiwand.com/en/WAV), [AIFF](https://www.wikiwand.com/en/AIFF), [Apple Lossless](https://www.wikiwand.com/en/Apple_Lossless), [AAC](https://www.wikiwand.com/en/Advanced_Audio_Coding), and [MP3](https://www.wikiwand.com/en/MP3) audio formats.
[^libvorbis]: [Wiki-Vorbis](https://www.wikiwand.com/en/Vorbis): **Vorbis** is a [free and open-source software](https://www.wikiwand.com/en/Free_and_open-source_software) project headed by the [Xiph.Org Foundation](https://www.wikiwand.com/en/Xiph.Org_Foundation). The project produces an [audio coding format](https://www.wikiwand.com/en/Audio_coding_format) and software reference encoder/decoder ([codec](https://www.wikiwand.com/en/Codec)) for [lossy](https://www.wikiwand.com/en/Lossy_compression)[audio compression](https://www.wikiwand.com/en/Audio_compression_(data)). Vorbis is most commonly used in conjunction with the [Ogg](https://www.wikiwand.com/en/Ogg)[container format](https://www.wikiwand.com/en/Digital_container_format)and it is therefore often referred to as **Ogg Vorbis**. 

[^pcm]: [Wiki-PCM](https://www.wikiwand.com/en/Pulse-code_modulation): **Pulse-code modulation** (**PCM**) is a method used to [digitally](https://www.wikiwand.com/en/Digital_signal_(signal_processing)) represent sampled [analog signals](https://www.wikiwand.com/en/Analog_signal).
[^rm]: [Wiki-RealMedia](https://www.wikiwand.com/en/RealMedia): **RealMedia** is a proprietary [multimedia](https://www.wikiwand.com/en/Multimedia)[container format](https://www.wikiwand.com/en/Container_format_(digital)) created by [RealNetworks](https://www.wikiwand.com/en/RealNetworks).
[^iec]: [Wiki-IEC](https://www.wikiwand.com/en/International_Electrotechnical_Commission): The **International Electrotechnical Commission[3]** (**IEC**; in [French](https://www.wikiwand.com/en/French_language): *Commission électrotechnique internationale*) is an international [standards organization](https://www.wikiwand.com/en/Standards_organization)[[4\]](https://www.wikiwand.com/en/International_Electrotechnical_Commission#citenote4)[[5\]](https://www.wikiwand.com/en/International_Electrotechnical_Commission#citenote5) that prepares and publishes International Standards for all [electrical](https://www.wikiwand.com/en/Electrical), [electronic](https://www.wikiwand.com/en/Electronics) and related technologies – collectively known as "[electrotechnology](https://www.wikiwand.com/en/Electrotechnics)". 
[^cabbc]: [Wiki-CABBC](https://www.wikiwand.com/en/Context-adaptive_binary_arithmetic_coding)
[^entropyEnc]: [Wiki-EntropyEncoding](https://www.wikiwand.com/en/Entropy_encoding): In [information theory](https://www.wikiwand.com/en/Information_theory) an  **entropy encoding** is a [lossless data compression](https://www.wikiwand.com/en/Lossless_compression) scheme that is independent of the specific characteristics of the medium. 
[^prefixcode]:[Wiki-prefixcode](https://www.wikiwand.com/en/Prefix_code): A **prefix code** is a type of [code](https://www.wikiwand.com/en/Code) system (typically a [variable-length code](https://www.wikiwand.com/en/Variable-length_code)) distinguished by its possession of the "prefix property", which requires that there is no whole [code word](https://www.wikiwand.com/en/Code_word) in the system that is a [prefix](https://www.wikiwand.com/en/Prefix_(computer_science)) (initial segment) of any other code word in the system.A prefix code is a [uniquely decodable code](https://www.wikiwand.com/en/Uniquely_decodable_code)
[^算术编码]: [Wiki-ArithmeticCoding](https://www.wikiwand.com/en/Arithmetic_coding)
[^cavlc]: [Wiki-CAVLC](https://www.wikiwand.com/en/Context-adaptive_variable-length_coding)
[^profile]: [Wiki-H.264-Profile](https://www.wikiwand.com/en/H.264/MPEG-4_AVC#Profiles)
[^ensvc]: [Wiki-ensvc](https://www.wikiwand.com/en/Scalable_Video_Coding): **Scalable Video Coding:** (**SVC**) is the name for the Annex G extension of the [H.264/MPEG-4 AVC](https://www.wikiwand.com/en/H.264/MPEG-4_AVC) video compression standard.  
[^cnsvc]: [Wiki-cnsvc](https://www.wikiwand.com/zh-hans/%E5%8F%AF%E9%81%A9%E6%80%A7%E8%A6%96%E8%A8%8A%E7%B7%A8%E7%A2%BC): **可适性视讯编码（Scalable Video Coding, SVC）**是传统[H.264/MPEG-4 AVC](https://www.wikiwand.com/zh-hans/H.264/MPEG-4_AVC)编码的延伸，可提升更大的编码弹性，并具有**时间可适性**（Temporal Scalability）、**空间可适性**（Spatial Scalability）及**讯杂比可适性**（SNR Scalability）三大特性，使视讯传输更能适应在异质的网路频宽