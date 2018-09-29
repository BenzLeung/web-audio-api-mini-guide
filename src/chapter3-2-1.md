# 3-2-1. SourceNode

这是最常用的 Node ，用于存储波形数据。

创建方法：

```javascript
var sourceNode = ctx.createBufferSource();
```

提供数据：

```javascript
sourceNode.buffer = buffer;
```

例：

```javascript
function playBuffer(buffer) {
  var sourceNode = ctx.createBufferSource();
  sourceNode.buffer = buffer;
  sourceNode.connect(ctx.destination);
  sourceNode.start(0);
}
```

## SourceNode.start() 开始播放

```javascript
start(when, offset, duration)
```

- `when`: 何时开始播放（秒）（参数可省掉）
- `offset`: 音频的何处开始播放（秒）（参数可省掉）
- `duration`: 播放多长时间（参数可省掉）
- 返回值：无

例：

```javascript
sourceNode.start(ctx.currentTime + 5, 1.5, 3.0);
```

上述语句表示：5秒后开始播放（当前时间+5），从音频1.5秒开始，播放到4.5秒处停止（持续3.0秒）。

若 `when` 参数的值小于等于 `ctx.currentTime` ，则默认立即开始播放。下面 `stop()` 也一样。


## SourceNode.stop() 结束

	stop(when)

- `when`: 何时结束（秒）（参数可省掉）
- 返回值：无

例：

```javascript
sourceNode.stop(ctx.currentTime + 5);
```

上述语句表示：5秒后结束（当前时间+5），然后**整个 SourceNode 就作废了**（上一节讲过），要播放就需要重新创建对象。

## SourceNode.loop / loopStart / loopEnd 循环播放设定

```
loop = [boolean]
loopStart = [number]
loopEnd = [number]
```

- `loop`: 是否循环播放
- `loopStart`: 循环开始点
- `loopEnd`: 循环结束点

例：

```javascript
sourceNode.loop = true;
sourceNode.loopStart = 2.2;
sourceNode.loopEnd = 6.0;
```

上述语句表示：2.2秒-6.0秒是循环节，播放到6.0秒处立即返回2.2秒继续播放。

可以指定循环节位置，是 SourceNode 比 HTML-5 的 `<audio>` 更强大的地方之一。所以，在游戏开发中，即使背景音乐也应该用 Web Audio API 而不用 `<audio>`。

## SourceNode.onended 播放完毕事件

```
onended = [function]
```

- `onended`: 播放完毕后触发的事件

例：

```javascript
sourceNode.onended = function () {
  alert('播放完毕！');
};
```
