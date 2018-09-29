# 3-2-4. DynamicsCompressorNode 动态压缩器

这是一个动态混音器，用于把多个音源实时混音，并防止爆音。

**创建方法：**`ctx.createDynamicsCompressor()`

**用法：**直接把多个音源 connect 到这个Node即可。

例：

```javascript
var compressorNode = ctx.createDynamicsCompressor();
sourceNode1.connect(compressorNode);
sourceNode2.connect(compressorNode);
sourceNode3.connect(compressorNode);
compressorNode.connect(ctx.destination);
```

虽然可以把多个 Node 直接 connect 到 ctx.destination，但是不建议这么做，因为这样可能会出现爆音现象。若有同时播放多个声音的需求（例如一个游戏的各种音效），记得**通过 DynamicsCompressorNode 混合多个声音**。
