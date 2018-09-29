# 5-3. BiquadFilter - 滤波器、均衡器

**[【Demo】](https://benzleung.github.io/web-audio-api-demo/eq.html)**

过滤或增益指定频率的声波。

**对象创建方法：**`ctx.createBiquadFilter()`

**常用属性方法：**

- **BiquadFilterNode.type**
	- 指定滤波器类型（详见下表）
- **BiquadFilterNode.frequency**
	- 指定一个频率（详见下表）
- **BiquadFilterNode.Q**
	- 设定容许度（详见下表）
- **BiquadFilterNode.gain**
	- 设定增益值（详见下表）

| type | 用途 | frequency | Q | gain |
| ---- | --- | --------- | - | ---- |
| lowpass | 低通滤波，只允许低频声音通过。 | 能通过的频率值界线（Hz），例如440，即只让 0-440Hz 的声音通过，削减掉 440-99999Hz 的声音。 | 削减度，数值越小则声音削减越厉害。 | 不可用。 |
| highpass | 高通滤波，只允许高频声音通过。 | 能通过的频率值界线（Hz），例如440，即只让 440-99999Hz 的声音通过，削减掉 0-440Hz 的声音。 | 削减度，数值越小则声音削减越厉害。 | 不可用。 |
| peaking | 峰值滤波，增益或削减某一频率的声音 | 要增益或削减的频率值**中间点**（Hz）。 | 范围，例如频率 440Hz，范围Q是20，那么范围就是 430-450Hz。 | 增益或削减度，正值增益，负值削减。 |
| bandpass, lowshelf, highshelf, notch, allpass | 带通滤波, 低架滤波, 高架滤波, 陷波器, 全通滤波 | 不常用，略 | 不常用，略 | 不常用，略 |

