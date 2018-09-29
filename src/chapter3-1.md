# 3-1. AudioNode 回顾

## 概念

- `AudioNode` 是一种用于生成或处理音频数据的类。
- `AudioNode` 是一个基础类，它有很多子类。
- 它的子类们，分别有不同的处理音频的功能
	- 例如均衡器、音量增益、滤波器……

## 种类

作为【声音源头】的 AudioNode。

- 用于存储波形数据，或者凭空生成波形数据。
- 音源没有输入，只有输出。
- 例： `SourceNode` ，用于存储波形数据并直接原样输出。

作为【过滤器】的 AudioNode。

- 用于过滤所输入的波形，并输出过滤后的结果。
- 过滤器至少接受1个输入，有1个输出。
- 有些过滤器可接受多个输入。
- 例：`GainNode`，用于调整音量。

作为【终点】的 `destination`。

- 这是Node的终点。
- 可接受多个输入（但不建议），无须输出。
- 输入到这里的声音将被用户听到。

## 代码

使用 `.connect` 方法把各种Node连接起来，起点是 `SourceNode`，终点是 `destination`：

```javascript
sourceNode.connect(node1);
node1.connect(node2);
node2.connect(node3);
// ......
nodeN.connect(ctx.destination);
```

使用 context 创建 AudioNode 对象，而不是 new 一个。

例如使用 `context.createBufferSource();` 而不是 new SourceNode();

```javascript
var sourceNode = ctx.createBufferSource();
```
----------
