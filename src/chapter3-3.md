# 3-3. 总结

* SourceNode 不仅可以播放一段音频，而且可以设置循环节，并且播放完毕后会触发 `onended` 事件。
* GainNode 用来调节音量。
* AudioParam 不是 AudioNode，它是一个非常有用的类，可以对音量或者其他数值类参数设置关键帧，产生**渐变**效果。
* 若有多个音频同时播放，它们都应该连接到 DynamicsCompressorNode 动态压缩器来处理混音，这样可以防止爆音。

## 接下来

下一节《一些声音常识》，在继续介绍 Web Audio API 的高级玩法之前，我觉得有必要先普及一些声音常识。因为有些高级玩法要求一些乐理知识。

所以，下一节没有代码。

## 一个更好的选择

如果觉得 Web Audio API 写起来代码量太大，那么可以考虑使用我已经封装好的 Javascript 库 —— **Benz Audio Engine**。

项目 Github：[https://github.com/BenzLeung/benz-audio-engine](https://github.com/BenzLeung/benz-audio-engine)

这个库**仅仅**使用了本节所提到的3个 Node 。简单、干净，没有多余的功能。

## 参考文献

- [Web Audio API W3C Working Draft](http://webaudio.github.io/web-audio-api/)
