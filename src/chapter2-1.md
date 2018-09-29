# 2-1. 播放声音的基本步骤

## 概念：AudioContext

AudioContext 是一个管理、播放声音的对象，大概跟 Canvas 的 context 差不多。

我们可以在 AudioContext 里“画”出各种声音。

## 初始化 AudioContext

```javascript
var AudioContext = window.AudioContext || window.webkitAudioContext;
var ctx = new AudioContext();
```

## 加载、解码mp3文件

```javascript
// 创建一个XMLHttpRequest请求对象
var request = new XMLHttpRequest();
// 请求一个MP3文件
request.open('GET', 'http://path/to/audio.mp3', true);
// Web Audio API 固定为 "arraybuffer"
request.responseType = 'arraybuffer';
// 加载完成后解码
request.onload = function() { 
    ctx.decodeAudioData(request.response, function(buffer) { 
        // 获得解码后的数据：buffer 
        // 这里可以立即播放解码后的 buffer，也可以把 buffer 值先存起来
        // 这个 playBuffer() 将在下文讲解如此实现
        playBuffer(buffer);
    }, function (){ 
        // 这里写解码出错的处理（例如文件损坏、格式不对等） 
    }); 
};
// 发送这个XMLHttpRequest请求
request.send();
```

1. 使用 `XMLHTTPRequest` 对象加载mp3资源数据
2. 加载完成后，mp3数据将被存储到 request.response 里
3. 使用 `ctx.decodeAudioData` 把mp3解码成wav格式的 `buffer`（异步）

## 播放声音

```javascript
function playBuffer(buffer) { 
  var sourceNode = ctx.createBufferSource(); 
  sourceNode.buffer = buffer; 
  sourceNode.connect(ctx.destination); 
  sourceNode.start(0); 
}
```

1. 加载mp3并解码得到 `buffer` 之后…
2. 创建 `sourceNode` 对象（下文将详解这个对象）；
3. 把 `buffer` 传入 `sourceNode.buffer` 属性；
4. 把 `sourceNode` 连接到 `AudioContext` 的音频输出口“`.destination`”；
5. 对 `sourceNode` 执行 `.start(0)`，声音就出来了。

![sourceNode 处理 buffer，然后传输到 destination](/assets/chapter2/3.png "sourceNode 处理 buffer，然后传输到 destination")

## 小结：播放声音的基本步骤

1. 初始化 `AudioContext` 对象
1. 使用 `XMLHTTPRequest` 对象从服务器获取mp3
1. 把mp3数据用 `ctx.decodeAudioData` 转换成wav格式的 `buffer`
1. 使用 `SourceNode` 对象（下文将详解这个对象）把 `buffer` 装起来
1. 让 `SourceNode` 连接到音频输出口 `destination`
1. 执行 `.start(0)` 触发 `SourceNode` 开始播放声音
