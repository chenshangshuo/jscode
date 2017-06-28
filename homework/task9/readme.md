#### 问题1
1.常见的块级元素：div、h1~h6、p、hr、form、ul、dl、ol、li、dd、dt、pre、table、th、td
2、常见的行内元素：em、span、strong、a、br、img、button、input、label、select、textarea、code、script
**块级元素及行内元素特性区别**
- 块级可以包含块级和行内，行内只能包含文本和行内
- 块级元素占据一整行，行内元素占据自身宽度空间
- 块级元素可设宽高，行内元素设宽高无变化
- 块级元素可设置margin、padding，行内元素只有margin在x轴方向上有效
![动手测试](http://upload-images.jianshu.io/upload_images/6470442-9d7e400e941d45be.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 问题2：css继承
**继承**：
1.优先级从高到低依次为：网页开发者定义的样式、网页阅读者定义的样式、浏览器的默认样式
2.对继承的元素来说，子元素自身的样式优先级高于从父级继承来的样式
3.当元素的一个**继承属性**没有指定值时，则取父元素的同属性的 计算值,只有文档根元素取该属性的概述中给定的初始值（这里的意思应该是在该属性本身的定义中的默认值）
4.当元素的一个**非继承属性**没有指定值时，则取属性的初始值该值在该属性的概述里被指定
>**哪些元素可继承:**
所有元素可继承：visibility和cursor。
内联元素可继承：letter-spacing、word-spacing、white-space、line-height、color、font、 font-family、font-size、font-style、font-variant、font-weight、text- decoration、text-transform、direction。
块状元素可继承：text-indent和text-align。
列表元素可继承：list-style、list-style-type、list-style-position、list-style-image。
表格元素可继承：border-collapse
**哪些元素不可继承：**
不可继承的：display、margin、border、padding、background、height、min-height、max- height、width、min-width、max-width、overflow、position、left、right、top、 bottom、z-index、float、clear、table-layout、vertical-align、page-break-after、 page-bread-before和unicode-bidi。

#### 问题3
块级水平居中：{maigin: 0 auto;}
行内水平居中：{text-align: center;}
#### 问题4

![三角形](http://upload-images.jianshu.io/upload_images/6470442-adc02d6312009032.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 问题5 实现单行文本溢出加.....
1.将单行文本变为块级元素，并设置有限的宽度
2.css写入：`white-space: nowrap;overflow: hidden;text-overflow: ellipsis;`
#### 问题6 px、em、rem的区别
- px为像素的固定单位
- em为相对单位，相对于父元素字体大小
- rem为相对单位，想到会有根元素（html）字体大小

---
#### 问题7 
1.body内文本字体大小12像素，文本行高为字体高度的1.5倍，字体查找按tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif顺序查找
2.中间有空格，不加引号浏览器解析时会误以为2种字体形式，其实就1种字体形式
3.unicode形式，表示宋体

---
#### 问题8
[8-1](http://js.jirengu.com/selit/4/edit?html,css,output)
[8-2](http://js.jirengu.com/mijeh/1/edit?html,css,output)
[8-3](http://js.jirengu.com/feso/3/edit?html,css,output)
[8-4](http://js.jirengu.com/sibo/1/edit?html,css,output)
[8-5](http://js.jirengu.com/diyis/1/edit?html,css,output)
