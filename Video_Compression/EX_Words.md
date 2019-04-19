# 专有名词补充

> 本章主要介绍一些专业术语，专有名词

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

- x264

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
- `ALAC(Apple Lossless Audio Codec)`是一个由Apple^®^开发的无损压缩数字音频解编码格式，其能将`FLAC` `WAV`等的无压缩格式转换成无损压缩格式。[^alac]
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