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

  | 函数库名称                                       | 用途                                                         |
  | :----------------------------------------------- | :----------------------------------------------------------- |
  | libswresample[^libswresample]                    | 音频重采样                                                   |
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

- `x264`是一个由VideoLAN开发的用于将视频流编码为`H.264/MPEG-4 AVC`格式的免费开源的软件函数库以及命令行工具[^x264]。*ffmpeg使用x264来解码H.264编码格式的多媒体流*

- `x265`是一个由MulticoreWare开发的用于将视频流编码为`H.265/HEVC`格式的基于`x264`修改的免费开源的软件函数库以及命令行工具[^x265]。*ffmpeg以及[UHDcode](https://www.wikiwand.com/en/MulticoreWare)使用x265来解码H.265编码格式的多媒体流*

- `libopenjpeg`用于解编码[Motion JPEG 2000](https://www.wikiwand.com/en/Motion_JPEG_2000) 编码格式的视频。[^codec]

- `QuickTime`是一种由苹果公司开发的可拓展的多媒体框架，能够处理各种格式的数字音视频，图像，全景图像以及交互式媒体。[^QT]

- `libaom`由Alliance for Open Media开发并用于解编码AV1编码格式[^codec]

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

- `H.264/AVC`
- `H.265/HEVC`
- 

### 音频编码格式

- `WAV(Waveform Audio File Format)`是一个由微软及IBM开发的无压缩数字音频编码格式。[^wav]注意，**无压缩≠无损**。就像你把棉被塞到仓库里面，如果棉被本来就是坏的那拿出来还是坏的。
- `AAC(Advance Audio Codec)`被分为很多种分支
  - `ALAC(Apple Lossless Audio Codec)`是一个由苹果公司开发的无损压缩数字音频解编码格式，其能将`FLAC` `WAV`等的无压缩格式转换成无损压缩格式。[^alac]
  - 
- `FLAC(Free Lossless Audio Codec)`是一个免费开源的无损压缩数字音频编码格式。[^flac]
- `AC3(Audio Codec 3,Advanced Codec 3,Acoustic Coder 3[这里区分一下， Adaptive Transform Acoustic Coding 3 是一种由索尼开发的格式])`是指杜比数字编码(Dolby Digital 或称AC-3)[^ac3]。
- `MP3(formally MPEG-1 Audio Layer III, MPEG-2 Audio Layer III)`是一种有损压缩数字音频编码格式。[^mp3]

---

## 封装格式

封装格式，你可以理解为文件后缀名，就是那些`.mp4` `.avi`的东西

形象点就是不同的行李箱装不同的东西以及装东西的方式不同

### 视频封装格式

- `MP4`
- `Motion JPEG 2000`是一种封装了JPEG 2000图像的序列以及音频的封装格式，其基于MP4/QuickTime封装格式[^MJ2]

### 音频封装容器



---

## 视频名词

## 音频名词





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



