# 5-2. Panner - 3D立体环绕音效

[**【Demo】**](https://benzleung.github.io/web-audio-api-demo/panner.html)

把声音的声源移动到3D空间中指定的点 \(x, y, z\)，模拟3D空间音效。

可以在声音播放期间实时调整空间坐标值 \(x, y, z\)，让声音绕着你转圈圈。

**对象创建方法：**`ctx.createPanner()`

**常用属性方法：**

* **PannerNode.setPosition\(x, y, z\)**
  * 设置声源空间位置 \(x, y, z\)。\(x, y, z\)是代表位置的坐标值。
* **PannerNode.setOrientation\(x, y, z\)**
  * 设置声源的朝向 \(x, y, z\)。\(x, y, z\)是代表方向的向量值。一个人背对你说话和正对你说话，效果是不一样的。
* **PannerNode.setVelocity\(x, y, z\)**
  * 设置声源的运动方向和速度 \(x, y, z\)。\(x, y, z\)是代表方向和速度的向量值。一个人站着说话和一边跑步一边说话，效果也是不一样的。



