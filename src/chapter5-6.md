# 5-6. Oscillator - 振荡器（声波生成器）

**[【Demo 1，简易电子琴】](https://benzleung.github.io/web-audio-api-demo/oscillator.html)**

**[【Demo 2，铃儿响叮当】](https://benzleung.github.io/web-audio-api-demo/jinglebell.html)**

**[【Demo 3，各种波形对比】](https://benzleung.github.io/web-audio-api-demo/oscillator2.html)**

发出指定频率和指定形状的声波。

这是一种作为音源的 Node，没有输入（即其他Node不能connect它）。

**对象创建方法：**`ctx.createOscillator()`

**常用属性方法：**

- **OscillatorNode.type**
	- 指定声波类型，有五种值：方形波`square`、三角波`triangle`、正弦波`sine`、锯齿波`sawtooth`、自定义`custom`。
- **OscillatorNode.frequency**
	- 指定一个频率

**注1：** 使用振荡器可以实现**零流量**演奏音乐，但是需要一定的乐理知识。

**注2：** 一般来说，方形波和锯齿波用于演奏高音和中音，三角波和正弦波用于演奏低音。

**注3：** 可以在维基百科找到音高和频率的对照表，把每个音符所对应的频率赋值给 `OscillatorNode.frequency` 即可演奏音乐——

- [维基百科：音高频率表](http://zh.wikipedia.org/wiki/%E9%9F%B3%E9%AB%98#.E9.9F.B3.E9.AB.98.E9.A0.BB.E7.8E.87.E8.A1.A8)
