**问题1**
**css全称**：层叠样式表（Cascading Style Sheets）

---
**问题2**
1.**CSS的三种引入方式**
- 行内引入（内联样式）：当特殊的样式需要应用到个别元素时，就可以使用内联样式。
- 内部引入（内部样式表）：单个文件需要特别样式时，就可以使用内部样式表。
- 外部引入（外部样式表）：当样式需要被应用到很多页面的时候，外部样式表将是理想的选择。
2.** link 和@import的主要区别**
- link属于XHTML标签，@import完全是CSS提供的一种方式
- link标签除了可以加载CSS外，还可以做很多其它的事情，比如定义RSS，定义rel连接属性，@import就只能加载CSS了
- 加载顺序的差别。当一个页面被加载的时候，link引用的CSS会同时被加载，而@import引用的CSS会等到页面全部被下载完再被加载。所以有时候浏览@import加载CSS的页面时开始会没有样式（就是闪烁）
- 兼容性的差别。低版本浏览器不支持@import，而link标签无此问题。
- 使用dom控制样式时的差别。当使用js控制dom去改变样式的时候，只能使用link标签
---
**问题3**

路径 | 存放位置 |代表含义
:---: |:---: |:---: |
css/a.css | 位于相邻css文件夹中的a.css | 从相邻的css文件夹中引入a.css
./css/a.css | 位于相邻css文件夹中的a.css| 从相邻的css文件夹中引入a.css
b.css | 位于同一文件夹下的b.css | 从html位于的本文件夹下引入b.css
../imgs/a.png | 位于上级imgs文件夹下的a.png | 从上级imgs文件夹中引入a.png 
/Users/hunger/project/css/a.css | 位于Users文件夹下hunger下projec下css中的a.css | 引入该路径下的a.css
/static/css/a.css | 位于static文件夹下css中的a.css | 引入该路径下的a.css
http://cdn.jirengu.com/kejian1/8-1.png  | 位于http://cdn.jirengu.com网站中kejian目录下的8-1.png | 引入该路径下的8-1.png

**问题4**
在js.jirengu.com上展示一个图片：在GitHub上新建images文件夹存放图片，图片可通过gitbash推送上远程仓库，使用图片时，复制图片地址即可。
![示例](http://upload-images.jianshu.io/upload_images/6470442-b9b7326a373c3135.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**问题5**
**html和 css 的书写规范**
- 字母宜小写
- 标签应闭合
- 不宜使用内联样式
- 在页面的head标签中引入所有的样式表文件
- css中选择器 与 { 之间必须包含空格，属性名 与之后的 : 之间不允许包含空格， : 与 属性值 之间必须包含空格
- css属性定义后必须以分号结尾
