# 5-1. DynamicsCompressor - 动态混音

**[【Demo】](https://benzleung.github.io/web-audio-api-demo/mix.html)**

用于把多个音源实时混音，并防止爆音。

**对象创建方法：**`ctx.createDynamicsCompressor()`

**用法：**直接把多个音源 connect 到这个Node即可。

虽然可以把多个 Node 直接 connect 到 ctx.destination，但是不建议这么做，因为这样可能会出现爆音现象。若有同时播放多个声音的需求（例如一个游戏的各种音效），记得**通过 DynamicsCompressorNode 混合多个声音**。
