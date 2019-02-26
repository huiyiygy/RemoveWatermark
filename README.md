# 仅供学习使用，请勿用于商用！

# 介绍
这是我本科的毕业设计，内容是基于机器学习研究图像中可视水印的提取与消除方法。我基于QT编写了桌面应用程序，将水印去除算法集成到软件中。

# 算法原理
可视水印的添加原理可以简单用下面这个公式表示：
<br/>
<a href="https://www.codecogs.com/eqnedit.php?latex=y=p*x&plus;(1-p)*m" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y=p*x&plus;(1-p)*m" title="y=p*x+(1-p)*m" /></a>
<br/>
y为添加水印后的图片，x为原图片，m为水印图片，p为混合度。所以当有一定数量的(x,y)时，就可以通过最小二乘法线性拟合计算出原始水印图片和混合度。
最终计算得出原始水印图像和混合度公式如下，n为图片数量：
<br/>
混合度：<a href="https://www.codecogs.com/eqnedit.php?latex=p=\frac{\sum_{i=1}^{n}x_iy_i-\frac{1}{n}*\sum_{i=1}^{n}x_i*\sum_{i=1}^{n}{y_i}}{\sum_{i=1}^{n}{x_i^2}-\frac{1}{n}*\sum_{i=1}^{n}{x_i}*\sum_{i=1}^{n}{x_i}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?p=\frac{\sum_{i=1}^{n}x_iy_i-\frac{1}{n}*\sum_{i=1}^{n}x_i*\sum_{i=1}^{n}{y_i}}{\sum_{i=1}^{n}{x_i^2}-\frac{1}{n}*\sum_{i=1}^{n}{x_i}*\sum_{i=1}^{n}{x_i}}" title="p=\frac{\sum_{i=1}^{n}x_iy_i-\frac{1}{n}*\sum_{i=1}^{n}x_i*\sum_{i=1}^{n}{y_i}}{\sum_{i=1}^{n}{x_i^2}-\frac{1}{n}*\sum_{i=1}^{n}{x_i}*\sum_{i=1}^{n}{x_i}}" /></a>
<br/>
<br/>
水印图片：<a href="https://www.codecogs.com/eqnedit.php?latex=m=\frac{\sum_{i=1}^{n}{y_i}-p*\sum_{i=1}^{n}x_i}{(1-p)*n}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?m=\frac{\sum_{i=1}^{n}{y_i}-p*\sum_{i=1}^{n}x_i}{(1-p)*n}" title="m=\frac{\sum_{i=1}^{n}{y_i}-p*\sum_{i=1}^{n}x_i}{(1-p)*n}" /></a>
<br/>

# 软件功能
假设有n张已经添加了水印的图片y，通过本软件提供的画板功能可以手动修复一部分图片得出估计的未添加水印的图片x'，然后通过提取水印功能，将水印图像与混合度计算出来。这样就可用计算出的结果达到批量去除水印的功能。

# 软件界面图
![软件界面图](https://github.com/huiyiygy/RemoveWatermark/blob/dev-ys/img/1.bmp)

# 软件操作示意图

![示意图1](https://github.com/huiyiygy/RemoveWatermark/blob/dev-ys/img/2.gif)
![示意图2](https://github.com/huiyiygy/RemoveWatermark/blob/dev-ys/img/3.gif)
