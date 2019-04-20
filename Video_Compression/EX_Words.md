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
  | libpostproc[^libpostproc]                        | 用于老的h263视频后处理                                       |
  | libswscale[^libswscale]                          | 用于视频以及图像缩放，像素长宽比的调整                       |
  | libavfilter[^libavfilter]                        | 用于加载音视频滤镜                                           |

  以及以下这些命令行工具，他们的用法会在进阶中讲到

  | 工具名            | 用途                                                         |
  | ----------------- | ------------------------------------------------------------ |
  | ffmpeg[^ffmpeg2]  | 用于转换音视频的格式，同时能够从视频采集设备采集视频并实时编码 |
  | ffplay[^ffplay]   | 一个简单的多媒体播放器，以及ffmpeg的函数库                   |
  | ffprobe[^ffprobe] | 用于分析多媒体信息                                           |

- `x264`

---

### 音频编解码器

> 音频编解码器是指能编码或解码音频数字数据信息流的设备或计算机程序

- `NeroAAC(Nero AAC Codec)`是一个用于解编码AAC格式(Advance Audio Coding)的免费工具集 [^neroaac]
- `QAAC(Quicktime AAC/ALAC Codec)`是一个基于Apple编码格式的命令行工具[^qaac]，需要iTunes或者QuickTime的支持。

---

## 编码格式

**编码格式≠视频格式**

**编码格式≠容器格式**

编码格式是指一个

### 视频编码格式

### 音频编码格式

- `WAV(Waveform Audio File Format)`是一个由微软及IBM开发的无压缩数字音频编码格式。[^wav]注意，**无压缩≠无损**。就像你把棉被塞到仓库里面，如果棉被本来就是坏的那拿出来还是坏的。
- `ALAC(Apple Lossless Audio Codec)`是一个由苹果公司开发的无损压缩数字音频解编码格式，其能将`FLAC` `WAV`等的无压缩格式转换成无损压缩格式。[^alac]
- `FLAC(Free Lossless Audio Codec)`是一个免费开源的无损压缩数字音频编码格式。[^flac]
- `FDKAAC(Fraunhofer FDK AAC Codec Library for Android)`是一个在安卓上的免费开源AAC解编码工具库。[^fdkaac]
- `AC3(Audio Codec 3,Advanced Codec 3,Acoustic Coder 3[这里区分一下， Adaptive Transform Acoustic Coding 3 是一种由索尼开发的格式])`是指杜比数字编码(Dolby Digital 或称AC-3)[^ac3]。
- `MP3(formally MPEG-1 Audio Layer III, MPEG-2 Audio Layer III)`是一种有损压缩数字音频编码格式。

---

## 封装容器

### 视频封装容器

- `MP4`

### 音频封装容器



---

## 视频名词

## 音频名词





---

##脚注

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



[^encoder]: [Wiki-Encoder](https://www.wikiwand.com/en/Encoder): An **encoder** is a device, circuit, transducer, software program, algorithm or person that [converts](https://www.wikiwand.com/en/Encoding) information from one format or [code](https://www.wikiwand.com/en/Code) to another, for the purpose of standardization, speed or compression.
[^decoder]: [Wiki-Decoder](https://www.wikiwand.com/en/Video_decoder): A **video decoder** is an [electronic circuit](https://www.wikiwand.com/en/Electronic_circuit), often contained within a single [integrated circuit](https://www.wikiwand.com/en/Integrated_circuit) chip, that converts base-band [analog video](https://www.wikiwand.com/en/Analog_video) signals to digital components video.
[^neroaac]: [Wiki-NeroAAC](https://www.wikiwand.com/en/Nero_AAC_Codec): **Nero AAC Codec** is a set of software tools for [encoding and decoding](https://www.wikiwand.com/en/Codec)[Advanced Audio Coding](https://www.wikiwand.com/en/Advanced_Audio_Coding) (AAC) format audio, and editing [MPEG-4](https://www.wikiwand.com/en/MPEG-4) metadata.
[^qaac]: [Google-QAAC](https://sites.google.com/site/qaacpage/): qaac is a command line AAC/ALAC encoder frontend based on Apple encoder
[^wav]: [Wiki-WAV](https://www.wikiwand.com/zh/WAV): **Waveform Audio File Format** (**WAVE**, or more commonly known as **WAV** due to its [filename extension](https://www.wikiwand.com/en/Filename_extension); pronounced "wave" or [/ˈwæv/](https://www.wikiwand.com/en/Help:IPA/English)[*WAV*](https://www.wikiwand.com/en/Help:Pronunciation_respelling_key)(rarely, **Audio for Windows**) is a [Microsoft](https://www.wikiwand.com/en/Microsoft) and [IBM](https://www.wikiwand.com/en/International_Business_Machines)[audio file format](https://www.wikiwand.com/en/Audio_file_format) standard for storing an audio bitstream on [PCs](https://www.wikiwand.com/en/Personal_computer).
[^alac]: [Wiki-ALAC](https://www.wikiwand.com/en/Apple_Lossless): **Apple Lossless**, also known as **Apple Lossless Audio Codec** (**ALAC**), or **Apple Lossless Encoder** (**ALE**), is an [audio coding format](https://www.wikiwand.com/en/Audio_coding_format), and its reference [audio codec](https://www.wikiwand.com/en/Audio_codec) implementation, developed by [Apple Inc.](https://www.wikiwand.com/en/Apple_Inc.) for [lossless data compression](https://www.wikiwand.com/en/Lossless_data_compression) of digital [music](https://www.wikiwand.com/en/Music)
[^flac]: [Wiki-FLAC](https://www.wikiwand.com/en/FLAC): **FLAC** ([/flæk/](https://www.wikiwand.com/en/Help:IPA/English); **Free Lossless Audio Codec**) is an [audio coding format](https://www.wikiwand.com/en/Audio_coding_format) for [lossless compression](https://www.wikiwand.com/en/Lossless_compression) of [digital audio](https://www.wikiwand.com/en/Digital_audio), and is also the name of the free software project producing the FLAC tools,
[^fdkaac]: [Wiki-FDKAAC](https://www.wikiwand.com/en/Fraunhofer_FDK_AAC): **Fraunhofer FDK AAC** (Full title **Fraunhofer FDK AAC Codec Library for Android**) is an [open-source](https://www.wikiwand.com/en/Open-source_software) software library for [encoding and decoding](https://www.wikiwand.com/en/Codec)[Advanced Audio Coding](https://www.wikiwand.com/en/Advanced_Audio_Coding) (AAC) format audio
[^ac3]: [Wiki-AC3](https://www.wikiwand.com/en/Dolby_Digital#/Dolby_Digital): AC-3 (Audio Codec 3, Advanced Codec 3, Acoustic Coder 3. [These are [backronyms](https://www.wikiwand.com/en/Backronym). [Adaptive Transform Acoustic Coding 3](https://www.wikiwand.com/en/ATRAC3) is a separate format developed by [Sony](https://www.wikiwand.com/en/Sony).])
[^mp3]: [Wiki-MP3](https://www.wikiwand.com/en/MP3): **MP3** (formally **MPEG-1 Audio Layer III** or **MPEG-2 Audio Layer III**)[[4\]](https://www.wikiwand.com/en/MP3#citenoterfc52194) is a [coding format](https://www.wikiwand.com/en/Audio_coding_format) for [digital audio](https://www.wikiwand.com/en/Digital_audio). 

---

最后修改

Gerardyang

20190420

本文无法遵守996Linces

<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a>

本作品采用[知识共享署名-相同方式共享 3.0 未本地化版本许可协议](http://creativecommons.org/licenses/by-sa/3.0/)进行许可。