#### 1.html部分
**语义化**
- 语义化标签优先，如：`aside、main`等标签，再兼容性允许的情况下，尽量使用语义化标签。
- 基于功能命名、基于内容命名、基于表现命名，如下图所示
`<div class="success"></div>
<div class="theme-color"></div>
<a class="login" href="#"></a>`
- 简略、明了、无后患，省略不必要的标签，命名合理
- .所有命名都使用英文小写

推荐：`<div class="main"></div> `

不推荐： `<div class="Main"></div> `

- .命名用引号包裹

推荐：`<div id="header"></div> `

不推荐： `<div id=header></div> `

- .用中横线连接

推荐：`<div class="mod-modal"></div> `

不推荐： `<div class="modModal"></div> `

#### 2.CSS部分
- tab 用两个空格表示
- css的 :后加个空格， {前加个空格
- 每条声明后都加上分号
- 换行，而不是放到一行
- 颜色用小写，用缩写, #fff
- 小数不用写前缀, 0.5s -> .5s；0不用加单位
- 尽量缩写， `margin: 5px 10px 5px 10px -> margin: 5px 10px`
参考：
```
/* Not recommended */
.test {
  display: block;
  height: 100px
}
/* Recommended */
.test {
  display: block;
  height: 100px;
}
/* Not recommended */
h3 {
  font-weight:bold;
}
/* Recommended */
h3 {
  font-weight: bold;
}
```
