# 5-7. 总结

* DynamicsCompressor - 动态混音
* Panner - 3D立体环绕音效
* BiquadFilter - 滤波器、均衡器
* Analyser - 频谱分析器（频谱图、时域图）
* Convolver - 卷积运算处理（环境混响音效）
* Oscillator - 振荡器（声波生成器）
* 以上所有 Node 都有自制的 [Demo](https://benzleung.github.io/web-audio-api-demo/)

## 本节的内容都用不着？

那么可以考虑使用我已经封装好的 Javascript 库 —— **Benz Audio Engine**。

项目 Github：[https://github.com/BenzLeung/benz-audio-engine](https://github.com/BenzLeung/benz-audio-engine)

这个库仅仅用到了本节所提到的第一个 API —— DynamicsCompressor，以及 SourceNode 和 GainNode（可能后续会考虑加入 Panner）。简单、干净，没有多余的功能。
