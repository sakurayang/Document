# Avisynth滤镜列表

## 内置滤镜

### 源文件加载

> 这些滤镜可以读取媒体文件并返回AviSynth Clip

| 名称                                            | 作用                                                         | 备注 |
| ----------------------------------------------- | ------------------------------------------------------------ | ---- |
| AviSource<br>AviFileSource<br>OpenDMLSource     | 打开AVI文件                                                  | 无   |
| DirectShowSource                                | 以DirectShow(Microsoft™的一种加载多媒体的方式)的方式打开文件 | 无   |
| ImageReader<br>ImageSource<br>ImageSourceAnim   | 读取一张静止或者动态的图片                                   | 无   |
| Import                                          | 将AviSynth脚本导入另一个脚本                                 | 无   |
| SegmentedAuiSource<br>SegmentedDirectShowSource | 可一次性加载最多1000个Avi文件                                | 无   |
| WavSource                                       | 加载Wav文件或AVI音频文件                                     | 无   |

### 色彩空间转换

> 这些滤镜可用于更改颜色格式或调整Clip的颜色

| 名称                                                         | 作用                                                         | 支持的源色彩空间   |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------ |
| ColorYUV                                                     | 独立调整颜色与亮度                                           | YUV[8-16bit]       |
| ConvertBackToYUY2                                            | 将RGB转换回YUY2                                              | RGB                |
| ConvertToRGB                                                 | 除非Clip是RGB24，否则将源文件转换为RGB32                     | All[8bit]          |
| ConvertToRGB24<br>ConvertToRGB32                             | 将Clip转换成8 bit色彩深度，RGB24/RGB32色彩空间的交错格式     | All[8bit]          |
| ConvertToRGB48<br>ConvertToRGB64                             | 将Clip转换成16 bit色彩深度，RGB48/RGB64色彩空间的交错格式==仅AVS+== | All[16bit]         |
| ConvertToPlanarRGB<br>ConvertToPlanarRGBA                    | 转换到平面RGB(A)色彩空间记录方式==仅AVS+==                   | All                |
| ConvertToYUY2                                                | 转换到8 bit色彩深度，YUY2色彩空间的的交错格式                | RGB24/32,YUV[8bit] |
| ConvertToYV24<br>ConvertToYV16<br>ConvertToYV12<br>ConvertToY8 | 转换到8bit的平面YV24/YV26/YV12/Y-only的色彩空间记录方式      | All                |
| ConvertToYUV444<br>ConvertToYUUV422<br>ConvertToYUV420<br><hr>ConvertToYUVA444<br>ConvertToYUVA422<br>ConvertToYUVA420 | 转换到平面YUV(A)色彩空间记录方式==仅AVS+==                   | All                |
| ConvertToYUV411                                              | 转换到8bit的平面YV411记录方式==仅AVS+==                      | All                |
| FixLuminance                                                 | 更正垂直亮度偏移                                             | YUY2               |
| Greyscale<br>Grayscale                                       | 转换到黑白                                                   | All                |
| Invert                                                       | 将指定的色彩通道反色                                         | All                |
| Levels                                                       | Scales and clamps the black and white levels(看不懂)，以及调整伽马值 | All[8-16bit]       |
| Limiter                                                      | 将色彩级别限制在CCIR-601范围内，并可选择突出显示该范围之外的像素 | YUV[8-16bit]       |
| MergeRGB<br>MergeARGB                                        | 选择并合并每一个输入的色彩通道                               | All                |
| MergeLuma<br>MergeChroma                                     | 将一个Clip的色度或者亮度合并（混合）到另一个Clip。可以选择两个Clip之间的权重 | YUV                |
| RGBAdjust                                                    | 将不同的色彩通道分开来调整                                   | RGB[8-16bit]       |
| ShowRed<br>ShowGreen<br>ShowBlue<br>ShowAlpha                | 展示所选的RGB(A)分片                                         | RGB                |
| SwapUV                                                       | 交换色度通道                                                 | YUV                |
| Tweak                                                        | 调整色调，饱和度，亮度和对比度                               | YUV                |
| UToY<br>UToY8<br>VToY<br>VToY8                               | 将U或V色度平面复制到Y亮度平面                                | YUV, 除了Y8        |
| YToUV                                                        | 将两个Clip的亮度通道分别作为U和V通道。 亮度通道是50％的灰色。 | YUV                |

### 遮罩以及图层

> 这些滤镜能用来通过或不通过蒙版在Clip上叠加图层，或者创建蒙版

| 名称         | 作用                                                         | 支持的源色彩空间                        |
| ------------ | ------------------------------------------------------------ | --------------------------------------- |
| ColorKeyMask | 按照颜色来抠图，生成一个alpha通道                            | RGB32/*RGB64*/*所有以平面方式记录的RGB* |
| Layer        | 将一个Clip放在另一个的上面，可以更改透明度                   | YUY2/RGB32/*RGB64*                      |
| Mask         | 将alpha蒙版应用于Clip                                        | RGB32/*RGB64*/*所有以平面方式记录的RGB* |
| MaskHS       | 使用给定的色调和饱和度范围返回Clip的蒙版（如Y8）             | YUV                                     |
| Merge        | 将一个Clip合并（混合）到另一个Clip。可以选择两个Clip之间的权重 | All                                     |
| Overlay      | 使用不同的叠加（混合）模式和可变不透明度，将一个Clip放在另一个上面，并使用可选的XY位移叠加图像。使用单独的Clip蒙版获取透明度信息 | 除了YV411都支持                         |
| ResetMask    | 对Clip应用全不透明的透明蒙板$$_{蛤？}$$<br><small>*原文：Applies an "all-opaque" alpha-mask to clip.*</small> | RGB32/*RGB64*/*所有以平面方式记录的RGB* |
| Subtract     | 显示两个Clip之间的对应像素的差异。                           | All                                     |

*斜体为仅在AviSynth+中支持*

### 几何变换

> 这些滤镜可以用来改变图片大小，处理边界，或变换形状

| 名称                                                         | 作用                                                | 支持的源色彩空间             |
| ------------------------------------------------------------ | --------------------------------------------------- | ---------------------------- |
| AddBorders                                                   | 给图片加上黑色边框                                  | All                          |
| Crop                                                         | 裁剪                                                | All                          |
| CropBottom                                                   | 裁剪底部像素                                        | All                          |
| FlipHorizontal<br>FlipVertical                               | 水平翻转<br>垂直翻转                                | All                          |
| Letterbox                                                    | 在顶部和底部或者左边和右边(或者四周)加上黑边        | All                          |
| HorizontalReducerBy2<br>VerticalReduceBy2<br>ReduceBy2       | 向水平，垂直或向两个方向缩小一半                    | All                          |
| BicubicResize<br>BilinearResize<br>BlackmanResize<br>GaussResize<br>LanczosResize<br>Lanczos4Resize<br>PointResize<br>SincResize<br>Spline16Resize<br>Spline36Resize<br/>Spline64Resize | 使用不同的采样算法将输入重新调整为任意分辨率        | All                          |
| SkewRows                                                     | 倾斜（或矫正）Clip的行                              | RGB24<br>RGB24<br>YUY2<br>Y8 |
| TurnLeft<br>TurnRight<br>Turn180                             | 将CLip逆时针旋转90度<br>顺时针旋转90度<br>旋转180度 | All                          |

### 图像修复

> 可用于图像修复，如去噪，模糊，锐化等

| 名称                      | 作用                                             | 支持的源色彩空间     |
| :------------------------ | ------------------------------------------------ | -------------------- |
| Blur<br>Sharpen           | 简单的3x3模糊 / 锐化处理                         | All                  |
| GeneralConvolution        | 生成3x3 或 5x5的卷积矩阵                         | RGB32                |
| SpatialSoften             | 以在空间上混合像素的方式来去噪                   | YUY2                 |
| TemporalSoften            | 以在时间上混合像素的方式来去噪                   | 除了RGB48和RGB24之外 |
| FixBrokenChromaUpsampling | 用于修复色度通道（虽然有更新的版本但不是免费的） | YUY2                 |

### 时间线编辑

> 用于剪辑或其它操作

| 名称                                                         | 作用                                 | 支持的源色彩空间 |
| ------------------------------------------------------------ | ------------------------------------ | ---------------- |
| AlignedSplice<br>UnalignedSplice                             | 连接两个Clip                         | All              |
| AssumeFPS<br>AssumeScaledFPS<br>ChangeFPS<br>ConvertFPS      | 以不同的方式改变帧率或者速度         | All              |
| DeleteFrame                                                  | 单独删除一个帧                       | All              |
| Dissolve                                                     | 连接两个Clip，同时重叠某些重复的部分 | All              |
| DuplicateFrame                                               | 重复某个帧                           | All              |
| FadeIn0 / FadeIn / FadeIn2<br>FadeOut0 / FadeOut / FadeOut2<br>FadeIO0 / FadeIO / FadeIO2 | 线性淡入/淡出                        | All              |
| FreezeFrame                                                  | 将Clip的所有帧替换为同一选定的帧     | All              |
| Interleave                                                   | 交错转场                             | All              |
| Loop                                                         | 将某一指定部分在选定时间内重复       | All              |
| Reverse                                                      | 倒放                                 | All              |
| SelectEven<br>SelectOdd                                      | 选择只输出奇数帧或偶数帧             | All              |
| SelectEvery                                                  | 输出一个固定周期的内所有帧           | All              |
| SelectRangeEvery                                             | 输出一个范围周期内的所有帧           | All              |
| Trim                                                         | 剪辑                                 | All              |

### 交错(Interlace)处理

> 用于创建以及处理以场为基础（隔行扫描）或者以帧为基础（逐行扫描）

| 名称                                 | 作用                                                         | 转换方向 | 支持的源色彩空间 |
| ------------------------------------ | ------------------------------------------------------------ | -------- | ---------------- |
| AssumeFrameBased<br>AssumeFieldBased | 强制素材以帧为基础或以场为基础                               | P<->I    | All              |
| AssumeBFF<br>AssumeTFF               | 强制以场为基础                                               | P->I     | All              |
| Bob                                  | 采用放大的方式来去交错。[Wiki](http://en.wikipedia.org/wiki/Deinterlacing#Field_extension_deinterlacing) | I->P     | All              |
| ComplemrntParity                     | 将上场优先转换为下场优先，反之亦然                           | I->I     | All              |
| DoubleWeave                          | 像Weave一样，以及可以将帧率翻倍(看不懂)<br>Operates like Weave, except that it produces double the number of frames by combining both the odd and even pairs of fields. | I->I     | YUY2             |
| PeculiarBlend                        | 以一种奇特的方式将每两帧混合起来                             | I->P     | All              |
| Pulldown                             | 选择源视频的每五帧中的两帧(用于2:3下位变换)                  | I->I     | All              |
| SeparateColumns<br>SparateFields     | 将每个帧的列或行分割开为新帧                                 | P->I     | All              |
| SeparateFilelds                      | 将每个帧拆分为上场和下场                                     | P->I     | All              |
| SwapFields                           | 交换两个场的顺序                                             | I->I     | All              |
| Weave                                | 生成隔行扫描的素材                                           | P->I     | All              |
| WeaveColumns<br>WeaveRows            | 将Clip以及Weave组中的列或行拼合在一起以生成复合帧            | ?        | All              |

### 音频处理

> 用于音频处理，当滤镜不支持输入的采样类型的时候，他会强制转换
>
> ==在AVS+中不会执行自动转换，你需要使用ConvertAudio来转换==
>
> 除非OPT_AllowFloatAudio设置为true，否则在处理ACM时，浮点音频信息将转换为16位。在这种情况下，音频保持原样。当直接访问AviSynth时（例如MeGUI，BeHappy或ffmpeg），不会自动转换。
>
> 自动转换是为无法处理浮点音频信息的用户所写的（过去大部分都无法处理）。注意，==转换在脚本处理完成后进行==。脚本中始终允许使用浮点音频信息。

| 名称                                                         | 用途                                                         | 支持的采样格式 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | -------------- |
| Amplify<br>AmplifydB                                         | 按倍数放大音量                                               | 16 bit, Float  |
| AssumeSampleRate                                             | 调整应聘的播放速度                                           | All            |
| AudioDub<br>AudioDubEx                                       | **AudioDub**将第一个参数中的Clip中的视频流与第二个参数中的Clip中的音频流合并。**AudioDubEx**一样，只不过当两个都没有音频流或者视频流的时候会抛出一个错误 | All            |
| AudioTrim                                                    | 剪辑                                                         | All            |
| ConvertAudioTo8bit<br>ConvertAudioTo16bit<br>ConvertAudioTo24bit<br>ConvertAudioTo32bit<br>ConvertAudioToFloat | 转换音频采样精度                                             | All            |
| ConvertToMono                                                | 转换到单声道                                                 | 16 bit, Float  |
| DelayAudio                                                   | 延迟音频播放时间                                             | All            |
| EnsureVBRMP3Sync                                             | 修正MP3与AVI的音画不同步问题                                 | All            |
| GetChannel<br>GetLeftChannel<br>GetRightChannel              | 从Clip获取一个音频轨道                                       | All            |
| KillAudio<br>KillVideo                                       | 从Clip中完全移除音频或视频                                   | All            |
| MergeChannels                                                | 合并两个Clip的音频轨道                                       | All            |
| MixAudio                                                     | 混合两个Clip的音频轨道                                       | 16 bit, Float  |
| MonoToStereo                                                 | 将两个单独的音轨转换为双声道                                 | 16 bit, Float  |
| Normalize                                                    | 在不削波的情况下尽可能放大整个波形                           | 16 bit, Float  |
| ResampleAudio                                                | 高质量音频重采样                                             | 16 bit, Float  |
| SuperEQ                                                      | 高质量18轨道均衡器                                           | Float          |
| SSRC                                                         | 非常高质量的音频重采样                                       | Float          |
| TimeStretch                                                  | 改变音频播放速率而不改变音色，或者改变音色不改变音频时间长度 | Float          |

### 条件以及元(meta)控制

> 元控制允许你控制其他滤镜的执行。条件控制将会在每一帧被执行并进行检查，而不是在最后。

| 名称                                                         | 作用                                                         | 支持的源色彩空间 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| CondictionalFilter<br>FrameEvaluate<br>ScriptClip<br>CondictionalSelect | 如果符合设定的条件，**CondictionalFilter**将返回第一个源，否则将返回第二个源。<br>**ScriptClip/FrameEvaluate**返回一个每帧都经过审查的Clip。<br>**CondicitionalSelect**将通过整数型评价从一堆源中返回一帧 | All              |
| ConditionalReader                                            | 从文本文件中读取用于比对的信息                               | All              |
| WriteFile<br>WriteFileIf<br>WriteFileStart<br>WriteFileEnd   | 计算条件表达式，然后输出到文本文件中                         | All              |
| Animate<br>ApplyRange                                        | **Animate**是一个用连续变化的参数来控制其他滤镜的元控制器<br>**ApplyRange**是一个**Animate**的开头的参数和结尾的参数一样的特殊情况。 | All              |
| TCPServer<br>TCPSource                                       | 通过网络发送Clip                                             | All              |

### 导出

> 用于直接导出多媒体

| 名称        | 作用     | 支持的源色彩空间 |
| ----------- | -------- | ---------------- |
| ImageWriter | 逐帧导出 | All              |

### 调试

| 名称                                     | 作用                                                         | 支持的源色彩空间        |
| ---------------------------------------- | ------------------------------------------------------------ | ----------------------- |
| BankClip<br>Blackness                    | 生成指定长度的纯色静音视频Clip（以帧为单位）                 | All                     |
| ColorBars<br>ColorBarsHD                 | 生成包含SMPTE彩条的Clip(就是信号中断那种)                    | RGB32, YUY2, YV12, YV24 |
| Compare                                  | 比较两个Clip并输出有差别的地方                               | All                     |
| Echo                                     | 强制对所有输入的Clip进行GetFrame调用。仅返回第一个结果       | All                     |
| Histogram                                | 多功能音频/视频分析工具                                      | All                     |
| Info                                     | 输出图像和声音信息                                           | All                     |
| MessageClip                              | 生成包含文本消息的Clip                                       | RGB32                   |
| Preroll                                  | 在非线性编辑上前进音频或视频                                 | All                     |
| ShowFiveVersions                         | 将五个视频Clip，并将它们从左到右排列                         | All                     |
| ShowFrameNumber<br>ShowSMPTE<br>ShowTime | 在每个帧上绘制AviSynth认为的数字<br><small>*原文:Draws text on every frame indicating what number AviSynth thinks it is.*</small> | All                     |
| StackHorizontal<br>StackVertical         | 将两个Clip上下或左右排列                                     | All                     |
| Subtitle                                 | 字幕                                                         | All                     |
| Tone                                     | 生成声音                                                     | Float*这里指采样进度*   |
| Version                                  | 使用简短的AviSynth版本和版权声明生成视频剪辑                 | RGB32                   |

### 脚注

> 上面的表格中使用以下命名颜色格式

| 名称                                                         | 色彩格式                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| All                                                          | RGB, YUV (detailed below)                                    |
| [RGB](http://avisynth.nl/index.php/RGB) [Interleaved](http://avisynth.nl/index.php/Interleaved) | [RGB24](http://avisynth.nl/index.php/RGB24), [RGB32](http://avisynth.nl/index.php/RGB32) [*8bit*] [RGB48, RGB64](http://avisynth.nl/index.php/Avisynthplus_color_formats) [*16bit*] **$$^{[+]}$$** |
| [RGB](http://avisynth.nl/index.php/RGB) [Planar](http://avisynth.nl/index.php/Planar) | [RGBP8, RGB**A**P8, RGBP**10**, RGB**A**P10 etc](http://avisynth.nl/index.php/Avisynthplus_color_formats) **$$^{[+]}$$** |
| [YUV](http://avisynth.nl/index.php/YUV)                      | [YUY2](http://avisynth.nl/index.php/YUY2) [Interleaved](http://avisynth.nl/index.php/Interleaved), YUV [Planar](http://avisynth.nl/index.php/Planar), [YUVA Planar](http://avisynth.nl/index.php/Avisynthplus_color_formats) **$$^{[+]}$$** |
| YUV [Planar](http://avisynth.nl/index.php/Planar)            | [YV12](http://avisynth.nl/index.php/YV12), [YV24](http://avisynth.nl/index.php/YV24)‡, [YV16](http://avisynth.nl/index.php/YV16)‡, [YV411](http://avisynth.nl/index.php/YV411)‡, [Y8](http://avisynth.nl/index.php/Y8)‡  [YUV444P8, YUV444P**10**, YUV444P**12** etc](http://avisynth.nl/index.php/Avisynthplus_color_formats) **$$^{[+]}$$** |
| YUVA [Planar](http://avisynth.nl/index.php/Planar)           | [YUV**A**444P8, YUV**A**444P**10**, YUV**A**444P12 etc](http://avisynth.nl/index.php/Avisynthplus_color_formats) **$$^{[+]}$$** |

符号说明

‡ : 	        不支持版本低于2.58的AviSynth

**$$^{[+]}$$** :   仅在AviSynth+中的色彩格式(Deep Color, Planar RGB, YUVA).

[8bit] :	   只有8-bit **$$^{[+]}$$**

[16bit] :	  只有16-bit **$$^{[+]}$$**

[8-16bit] :	8, 10, 12, 14, 16 bit (除了 32-bit浮点) **$$^{[+]}$$**

==AVS+== :	 AviSynth+的滤镜. 

---

最后修改

Gerardyang

20190428

本文无法遵守996 License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">知识共享署名-相同方式共享 4.0 国际许可协议</a>进行许可。