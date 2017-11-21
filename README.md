# 雪花飘落效果

#### [FallingView](https://github.com/AnliaLee/FallingView/blob/master/src/main/java/com/anlia/fallingview/FallingView.java)

* 教程博客：[Android自定义View——从零开始实现雪花飘落效果](http://www.jianshu.com/p/ce704b03f3f5)
* 简介：**循环绘制下落物体**的View，可以模拟**雪花、雨滴、金币等物体样式的飘落效果**
* 下落物体封装类：[**FallObject**](https://github.com/AnliaLee/FallingView/blob/master/src/main/java/com/anlia/fallingview/FallObject.java)，使用**Builder模式**进行初始化，初始化方法汇总：

| 方法名|参数解析|
|:-|:-|
|**setSpeed**(int speed)|**设置物体的初始下落速度**|
|**setSpeed**(int speed,boolean isRandomSpeed)|**设置物体的初始下落速度**，**isRandomSpeed**：物体初始下降速度比例是否随机|
|**setSize**(int w, int h)|**设置物体大小**|
|**setSize**(int w, int h, boolean isRandomSize)|**设置物体大小**，**isRandomSize**：物体初始大小比例是否随机|
|**setWind**(int level,boolean isWindRandom,boolean isWindChange)|**设置风力等级、方向以及随机因素**，**level**：风力等级，**isWindRandom**：物体初始风向和风力大小比例是否随机，**isWindChange**：在物体下落过程中风的风向和风力是否会产生随机变化|

* 初始化示例：
```java
//初始化一个雪花样式的fallObject
FallObject.Builder builder = new FallObject.Builder(getResources().getDrawable(R.drawable.ic_snow));
FallObject fallObject = builder
		.setSpeed(7,true)
		.setSize(50,50,true)
		.setWind(5,true,true)
		.build();

fallingView = (FallingView) findViewById(R.id.fallingView);
fallingView.addFallObject(fallObject,100);//添加50个下落物体对象
```

* 效果展示：

![](http://upload-images.jianshu.io/upload_images/4909537-28a80211d2457bef.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

***