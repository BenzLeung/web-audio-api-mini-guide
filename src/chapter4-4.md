# 4-4. 常见的音频格式

## MP3

一种很常见的声音文件格式，比特率范围是 30 - 320 Kbps。

网上最流行 128 Kbps。

现在 MP3 已经被所有浏览器所支持了。（[Can I Use: MP3](http://caniuse.com/#feat=mp3)）

## WAV

另一种很常见的声音文件格式，音频数据不经过任何处理和压缩，一个一个字节地忠实地记录每一个采样数据，因此文件体积比较大，不便于网络传播。

但是在 Web Audio API 中，有个 AudioNode 称为 Convolver （后文会介绍）的，必须用到一些特殊的 WAV 格式音频。

## WMA

在2000年-2010年之间还蛮常见的一种声音格式，由微软公司发明。

当时被很多 MP3 随身听支持，压缩率比 MP3 高。即 WMA 的 64 Kbps 的音质大概相当于 MP3 128 Kbps（[维基百科：WMA](https://zh.wikipedia.org/wiki/Windows_Media_Audio)）。

但是可能由于微软开出版权费过高（我猜的），所以现在的浏览器全都不支持了。

## AAC

一种网上不太常见但是兼容性最接近 MP3 的声音文件格式。常见扩展名有 `.aac` `.mp4` `.m4a` `.3gp`。

这是 MP3 的继承者，都是 MPEG 系列的标准，因此一般来说只要支持 MP3 的浏览器都能支持 AAC。

AAC 的压缩率几乎肯定比 MP3 高，但是能高多少取决于压缩软件是否给力，因为根据[维基百科](https://zh.wikipedia.org/wiki/%E9%80%B2%E9%9A%8E%E9%9F%B3%E8%A8%8A%E7%B7%A8%E7%A2%BC)的描述，AAC是个庞大家族，有很多种AAC，压缩率参差不齐。

不过无论如何，在Web端，AAC 确实是一种比 MP3 更省网络流量的选择。

现在 AAC 也已经被所有浏览器所支持了（[Can I Use: AAC](http://caniuse.com/#feat=aac)），所以以后都不需要用 MP3 了，放心地用 AAC 吧。
