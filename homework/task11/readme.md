#### 问题1：浮动元素有什么特征？对父容器、其他浮动元素、普通元素、文字分别有什么影响?
**特征：**
- 脱离文档的普通流
- 不被其他块级元素所感知，但可被块级元素中的文本、图像等行内元素所感知。
- 直到碰到父元素的包含框或子元素的包含框才停止

**影响：**
- 父容器感知不到浮动元素的存在，父容器的高度会塌陷
- 其他浮动元素碰到该浮动元素时，会停止浮动
- 普通元素感知不到浮动元素，继续按文档流排列，浮动元素覆盖普通元素，类似下图
![浮动元素覆盖普通元素](http://upload-images.jianshu.io/upload_images/6470442-556c3cfeafb5ad7f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 文字受到浮动元素的影响，移动以留出空间，围绕浮动元素排列（行框缩短）

---
#### 问题2：清除浮动指什么? 如何清除浮动? 两种以上方法
**清除浮动**:在非IE浏览器（如Firefox）下，当容器的高度为auto，且容器的内容中有浮动（float为left或right）的元素，在这种情况下，容器的高度不能自动伸长以适应内容的高度，使得内容溢出到容器外面而影响（甚至破坏）布局的现象。这个现象叫浮动溢出，为了防止这个现象的出现而进行的CSS处理，就叫CSS清除浮动。
**方法：**
- 在父元素最后添加一个空的div标签，对它清理浮动。
- 对父元素设置`float:left/right`或 `display：inline-block`或者`position:absolute/fixed`或`overflow：hidden`
#### 问题3：有几种定位方式，分别是如何实现定位的，参考点是什么，使用场景是什么？
**CSS 有三种基本的定位机制：普通流、浮动和绝对定位。**
- 普通流是默认的定位方式，在普通流中元素框的位置由元素在html中的位置决定，元素position属性为static或继承来的static时就会按照普通流定位，这是我们常见方式。
- 浮动，`float:left`、`float:right`两个常用属性，参考点为其父元素。
- `position:absolute`生成绝对定位元素，绝对定位元素的位置**相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于最初的包含块**。绝对定位的元素框从文档流完全删除，因此不占据空间.
**position定位几种方式**
- `position:static`该关键字指定元素使用正常的布局行为，即元素在文档流中当前的布局位置。此时 top, right, bottom, left 和 z-index 属性无效。
- `position:relative` 该关键字下，元素先放置在未添加定位时的位置，再在不改变页面布局的前提下调整元素位置。**不脱离文档流，相对于自身原本位置定位。**
**常作用于父元素中，给绝对定位的子元素当定位参考**
- `position:absolute`脱离文档流，通过指定元素相对于最近的非 static 定位祖先元素的偏移，来确定元素位置，**偏移是参考其第一个定位父元素**。
- `position:fixed`不为元素预留空间，而是通过指定元素相对于屏幕视口（viewport）的位置来指定元素位置。元素的位置在屏幕滚动时不会改变，**偏移是参考浏览器窗口**。
- `position:sticky`盒位置根据正常流计算(这称为正常流动中的位置)，然后相对于该元素在流中的 flow root（BFC）和 containing block（最近的块级祖先元素）定位。
---
#### 问题4：z-index 有什么作用? 如何使用
- > z-index 属性指定了一个元素及其子元素的 z-order。 当元素之间重叠的时候，z-order 决定哪一个元素覆盖在其余元素的上方显示。 通常来说 z-index 较大的元素会覆盖较小的一个。
对于一个已经定位的元素（即position属性值是非static的元素），z-index 属性指定：
元素在当前堆叠上下文中的堆叠层级。
元素是否创建一个新的本地堆叠上下文。

**z-index属性只对定位元素有效**
![动手练习](http://upload-images.jianshu.io/upload_images/6470442-6c5fae656ecfe49f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 问题5：`position:relative`和负`margin`都可以使元素位置发生偏移?二者有什么区别
`position:relative`是在自身的文档流中让自己显示上发生偏移，文档流中其他元素不会因为它的偏移而产生位置上的变化；`负margin`是让元素的外边框产生空隙从而发生偏移，此偏移会影响到元素后面的元素的位置。
![position:relative定位居中](http://upload-images.jianshu.io/upload_images/6470442-d6a7a88427750440.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![margin定位居中](http://upload-images.jianshu.io/upload_images/6470442-e6fddce380df8789.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 问题6：BFC 是什么？如何生成 BFC？BFC 有什么作用？举例说明
1.BFC（Block Format Content）:BFC的全称是Block Format Content——块级格式化上下文：浮动、绝对定位的元素(absolute、fixed定位)、块容器(display属性为inline-block,table-cells,table-captions)、以及带有overflow属性(该属性值不为visible)的display为block的块级元素会建立新的块级格式化上下文——元素们处于同一个块级格式化上下文时，会遵守相同的规则/格式(例如垂直排列的两个元素的margin会重叠)，但是处于不同的块级格式化上下文时，元素的排列展示遵守的规则/格式是不同的(处于不同BFC的垂直排列的两个元素的margin是不会重叠的)
2.对父元素设：
- float:left/right
- display：inline-block
- position:absolute/fixed 
- overflow：hidden
3.见下面三个例子
**阻止垂直外边距折叠**
在p的父元素div上设置bfc，可以把它的背景颜色给显示出来。
![父子外边距合并](http://upload-images.jianshu.io/upload_images/6470442-b4a56684972cd2a2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**包含浮动**
设置父元素为bfc，高度恢复。
![父元素高度塌陷](http://upload-images.jianshu.io/upload_images/6470442-e1d62772e4f39a77.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**不会重叠浮动元素**
![浮动元素不重叠](http://upload-images.jianshu.io/upload_images/6470442-5f59c05e7c050428.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 问题7：在什么场景下会出现外边距合并？如何合并？如何不让相邻元素外边距合并？给个父子外边距合并的范例
- 处在同一个BFC的两个且同处于普通流（非float和绝对定位）中的垂直相邻元素
- 空元素
- 父子元素的外边距合并
![空元素合并](http://upload-images.jianshu.io/upload_images/6470442-3a64afe86eae7d5b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
上图中，去除border，p元素间距为100px，空元素的上下margin值合并。
- 阻止相邻元素外边距合并：使其中一元素生成bfc，display：inline-block
- 父子外边距合并范例，见问题6中的3-1。

[效果范例1](http://js.jirengu.com/tumat/3/edit?html,css,output)
[效果范例2](http://js.jirengu.com/qinux/5/edit)
[效果范例3](http://js.jirengu.com/wogan/5/edit)
[效果范例4](http://js.jirengu.com/nazeg/3/edit?html,css,output)
