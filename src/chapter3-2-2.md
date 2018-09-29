# 3-2-2. GainNode 音量调节器

- 用于调节音量
- 创建方法： `ctx.createGain()`
- 调音量： `gainNode.gain.value = 0.5`（取值范围 0.0-1.0）

例：（把上文以及上一节的 playBuffer() 加上音量功能）

```javascript
function playBuffer(buffer, volume) {
  var sourceNode = ctx.createBufferSource();
  sourceNode.buffer = buffer;
  var gainNode = ctx.createGain();
  gainNode.gain.value = volume;
  sourceNode.connect(gainNode);
  gainNode.connect(ctx.destination);
  sourceNode.start(0);
}
```

上述代码，Node 连接成 `sourceNode` -> `gainNode` -> `destination`。然后，可以随时通过修改 `gainNode.gain.value` 的值，来调节音量。

## GainNode.gain

```
gain = [AudioParam]
```

- 使用 `gainNode.gain.value` 调音量。
- `gain` 是一个 `AudioParam` 对象，`gain.value` 才是音量的具体值（0.0-1.0）。
- **AudioParam** 是个 Audio API 特有的对象（下文分解↓↓）
