#### （一）CSS hack
不同厂商的浏览器或同一厂商的浏览器的不同版本，对CSS的解析认识不完全一样，因此会导致生成的页面效果不一样，得不到我们所需要的页面效果。
CSS hack就是针对不同的浏览器去写不同的CSS，让它能在不同的浏览器中也能得到我们想要的页面效果。
#### （二）浏览器兼容的思路
1.产品的角度思考，该产品面对的受众群体，他们使用哪种类型的浏览器多点，重点是页面的效果还是网站基本功能的搭建
2.该产品做到什么程度，需要让哪些浏览器支持哪些效果
3.根据兼容需求选择对应的技术框架/库（jquery），根据兼容需求选择兼容工具，再利用条件注释、css hack、js能力检测做些修补
4.渐进增强和优雅降级的选择

#### （三）浏览器兼容的写法
- CSS属性前缀法
`.box{
color: red;
-color:blue;/*ie6*/
*color:pink;/*ie67*/
color:yellow\9;/*ie/edge 6-8*/
}`
- IE条件注释法
`<!--[if IE 7]>
<link rel="stylesheet" href="ie7.css" type="text/css"/>
<![endid]>`

- 选择器前缀法
`*html *前缀只对IE6生效`
`*+html *+前缀只对IE7生效`
`@media screen\9{...}只对IE6/7生效`
`@media \0screen {body { background: red; }}只对IE8有效`
`@media \0screen\,screen\9{body { background: blue; }}只对IE6/7/8有效`

- 合适的框架
1.Bootstrap(>=ie8);
2.jQuery1.~(>=ie6),jQuery2.~(>=ie9);
3.Vue(>=ie9)

- 针对各浏览器内核css写法
1.-webkit- ，针对safari，chrome浏览器的内核CSS写法;
2.-moz-，针对firefox浏览器的内核CSS写法;
3.-ms-，针对ie内核的CSS写法;
4.-o-，针对Opera内核的CSS写法.


#### （四）解释名词
- 条件注释 (conditional comment) 是于HTML源码中被IE有条件解释的语句。条件注释可被用来向IE提供及隐藏代码。
- IE Hack：针对IE浏览器编写特定的CSS，可以在IE浏览器中也得到想要的效果
- js 能力检测：浏览器的能力检测目标不是检测特定的浏览器，而是检测浏览器的能力。这样，只需要检测浏览器是否支持特定的能力，就可以给出特定的解决方案。这一部分检测是解决浏览器兼容问题的主要检测。
- html5shiv.js：用于解决IE9以下版本浏览器对HTML5新增标签不识别，并导致CSS不起作用的问题
- respond.js：一个小脚本，用于为 IE6-8 以及其它不支持 CSS3 媒体查询功能的浏览器提供媒体查询的 min-width 和 max-width 特性，实现响应式网页设计。
- css reset：重新定义标签样式，覆盖浏览器的css默认属性
- normalize.css：是一个可以定制的CSS文件，它让不同的浏览器在渲染网页元素的时候形式更统一。保留有用的默认值，不同于许多 CSS 的重置；标准化的样式，适用范围广的元素；纠正错误和常见的浏览器的不一致性；一些细微的改进，提高了易用性；使用详细的注释来解释代码。
- Modernizr：提供了一种简单的方式检测任意新特性，从而让我们可以采取相应的操作
- postCSS：它可以被理解为一个平台，可以让一些插件在上面跑，它提供了一个解析器，可以将CSS解析成抽象语法树，通过PostCSS这个平台，我们能够开发一些插件，来处理CSS。热门插件如autoprefixer，它可以帮我们处理兼容问题，只需正常写CSS，autoprefixer可以帮我的自动生成兼容性代码
#### （五）查询属性兼容性的网站
https://caniuse.com/
