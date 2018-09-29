# 5-4. Analyser - 频谱分析器（频谱图、时域图）

**[【Demo 1，频谱图】](https://benzleung.github.io/web-audio-api-demo/analyser.html)**

**[【Demo 2，时域图】](https://benzleung.github.io/web-audio-api-demo/analyser2.html)**

获得音频的频谱数据，可用于绘制频谱图（条状的）和时域图（线状的）。

它不会改变声音波形，只读取波形数据。也就是说，输入和输出的声波是完全一样的，输入什么就输出什么。

**对象创建方法：**`ctx.createAnalyser()`

**常用属性方法：**

- **Analyser.fftSize**
	- 频谱分析下的快速傅里叶变换的大小（难理解？没事，看下一个属性就好），取值范围是 **32-2048 之内 2 的整数次方**，即 32、64、128、256、512、1024、2048。默认值为 2048。
- **Analyser.frequencyBinCount**
	- fftSize 值的一半。这个值代表你要绘制的条形频谱图中有多少条条形。**注意，这是个只读的属性**，要修改这个属性的值请改 fftSize。
- **Analyser.smoothingTimeConstant**
	- 让频谱图的动画带有平滑过渡效果，取值范围 0.0-1.0，0.0 代表不平滑，1.0 代表很平滑。
- **Analyser.getByteFrequencyData(array)**
	- 把当前的即时**频谱图**数据复制到 array 数组里。array 数组须事先创建好，Uint8Array 类型，数组大小为 frequencyBinCount，即应该事先有以下这一代码：
	- `var array = new Uint8Array(analyser.frequencyBinCount);`
- **Analyser.getByteTimeDomainData(array)**
	- 把当前的即时**时域图**数据复制到 array 数组里。array 数组须事先创建好，Uint8Array 类型，数组大小为 frequencyBinCount，即应该事先有以下这一代码：
	- `var array = new Uint8Array(analyser.frequencyBinCount);`
