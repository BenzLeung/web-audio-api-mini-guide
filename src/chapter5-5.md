# 5-5. Convolver - 卷积运算处理（环境混响音效）

**[【Demo】](https://benzleung.github.io/web-audio-api-demo/convolution.html)**

对音频进行卷积运算，用于添加环境音效，例如房间、音乐厅、剧院、电话等等。

在声学中，**回声**可以表示为声波与“特定波形”的**卷积**。

这些“特定波形”可以反映房间回声、教堂回声、电话声等等，并且可以用WAV格式存储。

参考：[维基百科：卷积](https://zh.wikipedia.org/wiki/%E5%8D%B7%E7%A7%AF)

（其实卷积到底是什么鬼，我也不太明白，维基百科的解释我看得似懂非懂、不明觉厉。）

（总之不管卷积了，能实现环境混响音效就好 ^_^）

**对象创建方法：**`ctx.createConvolver()`

**常用属性方法：**

- **ConvolverNode.buffer**
	- 把需要做卷积运算的波形数据扔进这个属性，就像 SourceNode.buffer 一样个扔法。然后输入的声波将会与这个 buffer 数据进行卷积运算后输出。

**注1：** 用于卷积运算的特定波形必须使用**无损**格式存储。也就是说可以是WAV格式的，但不能是MP3、AAC等有损压缩格式。

**注2：** 可以在这儿找到想要的卷积波形WAV文件——

- [包括大量卷积文件的 Github](https://github.com/GoogleChrome/web-audio-samples/tree/gh-pages/samples/audio/impulse-responses)
- [这大量卷积文件的 Demo](https://googlechrome.github.io/web-audio-samples/samples/audio/convolution-effects.html)
