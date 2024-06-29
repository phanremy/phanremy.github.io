---
layout: fragment
title: Android Image 里的 pixelStride 和 rowStride
tags: [android]
description: 理解 pixelStride 和 rowStride
keywords: Android, ImageReader, pixelStride, rowStride
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

当我们从屏幕上拿到截图：

```java
Image image = imageReader.acquireNextImage();
ImagePlane[] planes = image.getPlanes();

int width = image.getWidth();
int height = image.getHeight();

if (planes.length > 0) {
    int pixelStride = planes[0].getPixelStride();
    int rowStride = planes[0].getRowStride();
}
```

rowStride：每行数据的跨度；

pixelStride：相邻像素样本之间的距离；

所以理论上应该有 `rowStride / pixelStride == width`？

但实际上并非一定成立，也有可能 `rowStride > pixelStride * width`，在 width 像素右侧可能填充的有若干空白像素。

这个表现与具体设备有关。

参考：<https://blog.csdn.net/weixin_42510962/article/details/114215062>



前一阵更新 macOS 到 Sonoma 14.0 版本，然后遇到一个问题，Microsoft Edge 浏览器每次自动更新后，都会出现「你不能打开应用程序，因为它可能已损坏或不完整」的错误，Docker 栏的应用图标也会发生变化，如下图所示：

![](/images/fragments/macos-sonoma-cannot-open.png)

这种情况是因为应用自升级时，安装被系统阻止了（猜想）。

需要将设置中的「安全性与隐私」中的「允许从以下位置下载的应用」中开启「任何来源」，开启方法是在终端执行：

```sh
sudo spctl --master-disable
```

开启成功的效果如下图：

此时重新下载安装 Microsoft Edge 浏览器，以后再遇到自动更新，就可以正常使用了。
