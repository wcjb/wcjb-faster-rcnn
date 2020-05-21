# wcjb-faster-rcnn
&emsp;&emsp;本项目主要基于Python+Tensorflow 2.1 实现faster rcnn算法进行目标检测，模型由一张RTX2070显卡进行训练。



## VOC数据集

[VOC](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/#data)数据集主要用于现实场景的多对象识别，该数据集提供了含20个对象的图像训练集：

- *Person:* person
- *Animal:* bird, cat, cow, dog, horse, sheep
- *Vehicle:* aeroplane, bicycle, boat, bus, car, motorbike, train
- *Indoor:* bottle, chair, dining table, potted plant, sofa, tv/monitor

---

&emsp;&emsp;在官网下载数据集解压后的文件目录如下：

![解压后的目录](https://tva1.sinaimg.cn/large/007S8ZIlly1gf0gspnuz7j30bi03ymys.jpg)

&emsp;&emsp;对于本项目，由于只需进行目标检测，只需用到Annotations、ImageSets、JPEGImages这三个目录下的数据。下面进行详细说明：

### Annotations

&emsp;&emsp;存放相关标注信息，每一张图片对应一个xml文件，具体xml内容如下:

```xml
<annotation>
  <folder>VOC2012</folder>
  <filename>2007_000033.jpg</filename>
  <source>
    <database>The VOC2007 Database</database>
    <annotation>PASCAL VOC2007</annotation>
    <image>flickr</image>
  </source>
  <size>
    <width>500</width>
    <height>366</height>
    <depth>3</depth>
  </size>
  <segmented>1</segmented>
  <object>
    <name>aeroplane</name>
    <pose>Unspecified</pose>
    <truncated>0</truncated>
    <difficult>0</difficult>
    <bndbox>
      <xmin>9</xmin>
      <ymin>107</ymin>
      <xmax>499</xmax>
      <ymax>263</ymax>
    </bndbox>
  </object>
  <object>
    <name>aeroplane</name>
    <pose>Left</pose>
    <truncated>0</truncated>
    <difficult>0</difficult>
    <bndbox>
      <xmin>421</xmin>
      <ymin>200</ymin>
      <xmax>482</xmax>
      <ymax>226</ymax>
    </bndbox>
  </object>
</annotation>
```

&emsp;&emsp;可以看到，里面保存图片的基本信息和标注信息。

### ImageSets

&emsp;&emsp;本项目只会用到ImageSets/Main下train.txt , val.txt, test.txt这三个文件，里面存储对应训练集，验证集，测试集的图片名称。

###  JPEGImages

&emsp;&emsp;存储所有的图片数据

---

&emsp;&emsp;为了便于后续计算，需要先将VOC数据集解析为如下格式：

![](https://tva1.sinaimg.cn/large/007S8ZIlly1gf0h5p72yzj311a09itkd.jpg)

后续的数据处理和算法请参考代码，代码中有具体的说明。
