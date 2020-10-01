#  **	CSS2**

# 1. 文本、段落样式

```javascript
// 文本对齐方式
text-align: left(default)/center/right;
// 文本修饰（上-中-下划线），不能分开重复设置
text-decoration: none(default)/overline/line-through/underline;
text-decoration: underline line-through overline #ff142b; // 上 中 下 颜色
// 文本块首行文本的缩进
text-indent: 10px/50%/10em/10rem/inherit;
// 控制元素中的字母: 默认格式/每个单词开头大写/全部大写/全部小写/继承父元素
text-transform: none(d)/capitalize/uppercase/lowercase/inherit;
/**
* 文本阴影效果，最有用的
* : h-shadow v-shadow blur color;
* h-shadow：必需。水平阴影的位置。允许负值
* v-shadow：必需。垂直阴影的位置。允许负值
* blur：可选。模糊的距离
* color: 可选。阴影的颜色
*/
text-shadow: 30px -30px 5px red;

// 行高：行与行之间距离 （1em：相当于继承自父元素）
line-height: normal(d)/10px/50%/10em/10rem/inherit;
// 字符之间间距: 默认（字符之间没有额外间距）
letter-spacing: normal(d)/10px/50%/10em/10rem/inherit;
// 单词句子之间间距：默认（单词句子之间没有额外间距）
word-spacing: normal(d)/10px/50%/10em/10rem/inherit;
// 文本空白处理方式：
	默认：浏览器忽略空白，在浏览器中显示时会自动换行
   	nowrap: 不会自动换行，在一行显示所有文件
    pre: 同html中<pre>标签作用，整体同在html文档中相同格式显示
	pre-line：去掉空白符序列，但是保留换行符
	pre-wrap: 保留空白符序列，并进行正常的换行
white-space: normal(d)/nowrap/pre/pre-line/pre-wrap/inherit;

```

> 相对 `font-size` 计算值的倍数长度单位 -- 本质上单位还是 px
>
> em相对于父元素，rem相对于根元素(注意：一定是html)
>
> em,rem相对的都是父元素或者 html 元素的 font-size 数值
>
> inherit：继承永远都是默认继承的，只要父元素设置了该属性，则子元素一定会继承该属性，除非子元素自身覆盖它；如果父元素未设置，则父元素与子元素均取默认值
>
> css中不能针对一个选择器写两个相同的属性，如果相同的话，后面的设置会覆盖前面的设置

```css
// 在块元素中使用，
// 默认值。内容不会被修剪，会呈现在元素框之外
// 内容会被修剪，并且其余内容是不可见的
// 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容,意思是不管是否溢出，都有滚动条
// 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容，意思是只有在溢出的情况下才会有滚动条
overflow: visible(d) / hidden / scroll / auto / inherit
// 处理溢出盒子模型的文字元素：省略号
overflow: hidden;
text-overflow: clip(修剪文本) / ellipsis(省略号);
// 溢出自动换行：不换行 / 允许在单词内换行
word-break: normal / break-all;
```

# 2. 字体样式

```javascript
// 字体颜色
// 取值：颜色单词/16进制颜色代码表示法(分别代表rgb)/rgb/rgba/hsl
color: red/#AABBCC/rgb(255,255,255)/rgbs(255,255,255,0.5)/hsl(360, 100%, 100%);
// 字体大小
font-size: normal(d)/10px/50%/10em/10rem/inherit;
// 字体类型：使用字符串设置
font-family: "楷体"/"黑体"/"Times New Roman";
// 字体加粗：100~900/bold(900)/lighter(100)
font-weight: normal(d)/100~900/bold/lighter;
// 字体倾斜：italic用的最多
font-style: normal(d)/italic/oblique/inherit;
```

# 3.  背景样式

```javascript
// 背景颜色：颜色单词/16进制颜色代码表示法(分别代表rgb)/rgb/rgba(a透明度：0~1)/hsl/transparent
background-color: red/#AABBCC/rgb(255,255,255)/rgba(255,255,255,0.5)/hsl(360,100%,100%);
// 指定背景区域
// border-box(d): 默认值，包括边框
// padding-box: 不包括边框，包括内边距
// content-box: 不包括内边距，只包括 content 区域
background-clip: border-box(d) / padding-box / content-box

// 背景图片：url地址("网络地址/本地相对地址/本地绝对地址")
// 图片默认按正常大小显示：
// 盒子太小 -- 显示部分图片，从左到右，从上到下   盒子太大 -- 重复显示，从左到右，从上到下
background-image: url("地址") ;
// 背景图片是否重复：不重复/x-y方向重复/x方向重复/y方向重复
background-repeat: no-repeat/repeat(d)/repeat-x/repeat-y;
// 背景图片是否固定或随着页面滚动：随页面滚动/固定不动（类似流氓广告）/inherit
background-attachment: scroll(d)/fixed/inherit;
// 背景定位(融合-x，-y)：相对点很有意思，与空白有关系
background-position: 50px 100px/50% 50%/center center/left top/right bottom;
// 设置水平位置：相对于左上角原点/居中/居中/左边/右边
background-position-x: 50px/50%/center/left/right;
// 设置垂直位置：相对于左上角原点/居中/居中/上面/底部
background-position-y: 100px/50%/center/top/bottom;

// 聚合（复合 ）属性：融合下面所有相关的background属性
// 符合属性的顺序没有关系
background: {
    color: red;
    image: url("地址") ;
    repeat: no-repeat;
    attachment: scroll;
    position: 50px
}
background: red url("地址") no-repeat scroll center center;
```

> 1. **<html>、<body>的width、height问题？**
>
>    width、height 不具有继承型，因此向上遍历的时候只要有一个父元素未设置高度或者设置auto（意味着此时该父元素不能确定一个height）,此时百分比就会失效
>
>    一个div块级元素没有主动为其设置宽度和高度，浏览器会为其分配可使用的最大宽度(比如全屏宽度、父元素宽度)，但是不负责分配高度，块级元素的高度是由子元素堆砌撑起来的。**
>
>    那么，html和body标签的高度也都是由子级元素堆砌撑起来的。
>
>    **元素高度百分比需要向上遍历父标签要找到一个定值高度才能起作用，如果中途有个height为auto或是没有设置height属性，则高度百分比不起作用**，
>
>    此时的情况是父元素高度依赖子元素堆砌撑高，而子元素依赖父元素的定高起作用，互相依赖，却都无法依赖，死循环了，那如何解决这个问题呢，可以让子元素先定高，这样是可以解决；但是如果子元素一定要依赖父元素高度呢？
>
>    div的父元素是body，body的父元素是html，通过height:100%层层向上，找到顶级获取定高。所以出现了html和body同时设置height:100%，那html的上级是谁呢？
>
>    **浏览器负责分配块级元素宽度，那么浏览器也一定可以分配高度(只是没有做)，那么浏览器本身是有宽度和高度的，设置html的height:100%，就可以获取浏览器的定高了，后面的body和div也就有了依赖。**
>
>    ==display: inline （所有的 inline 元素），不会阻挡 width: 50% 向上查找父元素：==
>
>    ==理由: inline 元素不存在 宽度，和高度，所以向上查找的时候会自动忽略==
>
>    ==又因为它的宽高为 auto，所以子元素反过来依旧可以膨胀该父元素==
>
>    一般操作：
>
>    ```javascript
>    html, body {
>    	height: 100%;
>    }
>    ```
>
> 2. **<html>、<body>的背景色问题？**
>
>    **当 html 标签无背景样式时，浏览器获取 body 的背景色作为浏览器底板的背景色**
>
>    **当 html 标签含有背景色，浏览器获取 html 标签的背景色作为浏览器地板背景色**
>
>    不论怎样，html 和body 在自身的尺寸内按正常背景色显示（有时候感觉不正常是由于浏览器的背景色和它们的背景色相同，所以看不出来效果，实际上是起作用的）

> 精灵图：将多张图片合并到一张图片，通过定位的方式进行展示

> background-color 包括 padding 区域
>
> width、height 只说明 content 区域的 宽度 和 高度

ps. 样式优先级

1. 行内样式 > 内部样式 > 外部样式
2. id 选择器 > 类选择器 > 标签选择器
3. 总体规则：
   - 行内样式（已经在行内了，就不存在选择器的问题）
   - 内部样式（id 选择器 > 类选择器 > 标签选择器）
   - 外部样式（id 选择器 > 类选择器 > 标签选择器）

```css
// 颜色背景
// content 区域尺寸
width: 800px;
height: 400px;
// 内边距尺寸
padding: 30px;
// 边界格式
border:  20px dotted black;
// 背景颜色
background-color: red; // 也能够设置渐变
// 背景范围： 包括边界（默认） / 包括内边距 / 包括 content
background-clip: border-box(d) / padding-box / content-box

// 只对背景图片有效的背景属性
// 设置背景图片
background-image: url("./test.jpg");
// 设置背景图片大小尺寸            取宽高较小值   取宽高较大值
// 背景尺寸: 宽width  高height / 宽度方向填满 / 填满区域（不保证图片显示完全）
// 这里使用 contain / cover 自动填充的时候要考虑到 background-origin 影响
// 填充的区域与 background-origin 的取值相对应
background-size: 100px/100px 200px / contain / cover
// 设置是否重复
background-repeat: no-repeat;
// 设置背景图片显示的原点
// 注意：和 background-clip 不同，这里不是设置区域，只是设置初始显示的原点，
// 如果 允许重复的化，背景图片始终会覆盖 边界 、内边距、 content 这三个区域
background-origin: content-box/padding-box(d)/border-box
// 设置背景图片位置（相对背景图片原点）
background-position: 25px 50px;
// 背景图片是否固定或随着页面滚动：随页面滚动/固定不动（类似流氓广告）/inherit
background-attachment: scroll(d)/fixed/inherit;
```

## 3.1 width: auto / height: auto / 100%

```css
width / height: auto; // 具体的值由 子元素 决定，由子元素来负责撑开父元素
// 特殊情况： 
// 当元素为 block 元素时，width: auto 为父元素决定; 
// 父元素的宽度 = 子元素 margin + border + padding + content(实际的 width)

width / height: 100%;
// 值由父元素的宽度决定，相当于：子元素width = 父元素 width * 该值
// 其余的 margin / border / padding 另算，该溢出按溢出处理
```

# 4. 链接/列表/表格

```javascript
// a 链接样式
// 改变超链接字体颜色
color: red;   // 单独设置字体颜色
// 去掉超链接下路线
// 文本修饰（上-中-下划线），不能分开重复设置
// 设置是否有下划线及下划线的颜色
text-decoration: underline(d) #ff142b; 
text-decoration: none 
// 修改超链接字体属性
利用 2 中的字体样式通用属性
```

```javascript
// ul -- 无序/ol -- 有序/li -- 单条列表项 列表样式
// 二者作用相同，设置每条列表项前面的引导符号：无/圆点/方点/三角形
list-style-type: none/circle/square/triangle;
list-style: none/circle/square/triangle;
// 在每条列表项前面添加自定义的引导符号: url地址("网络地址/本地相对地址/本地绝对地址")
list-style-image: url("地址");
```

```javascript
// table -- tr -- td 表格样式
// 表格边框样式: 边框粗细/线型/颜色
border: 1px solid red;
// 表格背景颜色
background-color: red/#AABBCC/rgb(255,255,255)/rgba(255,255,255,0.5)/hsl(360,100%,100%);
// 每个表格项的边框是否合并：独立(d)/合并/继承
// 边框默认是分开的
border-collapse: seperate(d)/collapse/inherit;
```

```html
 // 控制 td 表格中的内边距 和 表格之间的间隙（间隔）
  <table  cellpadding="15">

    <caption>我的标题</caption>

    <thead>
      <tr> <td rowspan="2">文章标题1</td> <td>介绍1</td> <td>描述1</td> </tr>
      <!-- <tr> <td>文章标题2</td> <td>介绍2</td> <td>描述2</td> </tr> -->
      <!-- 因为合并挤占，删除合并掉的 表格 -->
      <tr>  <td>介绍2</td> <td>描述2</td> </tr>    
    </thead> 

    <tbody>
      <!-- <tr> <td>文章标题1</td> <td>介绍1</td> <td>描述1</td> </tr> -->
      <!-- 因为合并挤占，删除合并掉的 表格 -->
      <tr> <td colspan='2'>文章标题1</td>  <td>描述1</td> </tr>
      <tr> <td>文章标题2</td> <td>介绍2</td> <td>描述2</td> </tr>
    </tbody>

    <tfoot>
      <tr> <td>文章标题1</td> <td>介绍1</td> <td>描述1</td> </tr>
      <tr> <td>文章标题2</td> <td>介绍2</td> <td>描述2</td> </tr>
    </tfoot>

  </table>
```

```css
table {
    display: table;
    
    // 处理 table ，其他都不能设置 margin 属性，即使设置了也是无效的
    // 要想控制 cell 表格单元之间的间距，一般通过 table 元素属性 cellspacing 来设置
    display: table-caption;
    
    display: table-header-group;
    display: table-row-group;
    display: table-footer-group;
	
    display: table-row;
    display: table-cell;
}
```



# 5. 伪类/伪元素

```css
// 伪类
// a 超链接相关伪类：以下四个要严格包装顺序
// 用户未访问（点击）过的链接（这个属性基本没什么用）
a:link {
	color: red;
	...
}
// 用户已经访问（点击）过的链接
a:visited {
	color: blue;
	...
}
// 用户鼠标移动到上面的链接
a:hover {
	color: black;
	...
}
// 用户当前选中的链接（左键点击/按下时，放开后就恢复）
a:active {
	color: purple;
	...
}

// 表示用户点击某个元素的时候
x:active {
    
}

// input 输入框相关伪类
// 获取焦点的输入框
input:focus {
	background: yellow;     // 获取焦点时的背景颜色
	...                     // 其他样式都可以修改
}

// 元素顺序选择器（伪类选择器）
// x(指想要控制的那个元素) -- div/li/...   :  第一个子元素/第n个子元素/最后一个子元素   
x:first-child/nth-child(n)/last-child {
	...
}

// 改变选中文字的背景色
x:selection {
	background-color: red;
}
```

```javascript
// 伪元素
// x -- p/span/h1/a... :: 在文本不同位置添加一些效果

// 在文本前面/后面添加内容，添加的元素在页面上不能选中
x::before/after {
	content: "在文本前面/后面添加的内容";   	   // 在文本前面/后面添加文本
	content: url("地址");                 // 在文本前面/后面添加图片
	// 在文本前面/后面添加块（要想下面这些属性起作用，必须要有 content 这个属性）
	display: block;
	background-color: red;
	width: 500px;
	height: 500px;
}
// 设置文本首行样式，只能是第一行
x::first-line {
	color: blue;
	...
}
// 设置文本第一个字符样式
x::first-letter {
	color: blue;
	...
}
```

> ps. before/after 伪元素
>
> 1. before 文本内容 after 都是放在 盒子模型的 content 中
> 2. before / after 本质上也是一个盒子模型
> 3. 如果想将 before / after 元素当作块元素来处理，必须不能省略 content: '' 属性

# 6. 盒子模型

> 所有的 html 元素可以看作是一个盒子
>
> 盒子尺寸（ width/height ）： content-size
>
> ​	* 当指定 CSS 元素宽度和高度的属性时，只是设置了 content 内容区的宽度和高度

```javascript
// body 元素会有一个默认的 margin: 8px
// body {
//    display: block;
//    margin: 8px;
// }
// margin -- 外边距：四个方向/上下、左右/上、左右、下/上、右、下、左
margin:  10px/10px 10px/10px 12px 14px/10px 12px 14px 16px;
margin-top: 10px;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 10px;

// border -- 边框：宽度 线型 颜色
border: 5px solid red;
// 边框线条颜色
border-color: red;
// 边框线型
border-style: solid;
// 边框宽度
border-width: 5px;
// 上/右/下/左边框的宽度/线性/颜色属性：同 border
border-top/right/bottom/left-width/style/color: 5px dashed red;

// padding -- 内边距：四个方向/上下、左右/上、左右、下/上、右、下、左
padding:  10px/10px 10px/10px 12px 14px/10px 12px 14px 16px;
padding-top: 10px;
padding-right: 10px;
padding-bottom: 10px;
padding-left: 10px;

// content -- 内容：宽度/高度、文本样式、字体样式、背景样式
width: 100px;
height：50px;
// 最大宽度、高度
max-width: 800px;
max-height: 700px;
// 最小宽度、高度
min-width: 500px;
min-height: 600px;
文本样式：...；
字体样式：...;
背景样式：...;
```

## 6.1 块状元素中文字换行

> 1. css 空白字符（空格、制表、回车换行）处理
>
>    针对 block、block-inline、inline 三种 display 值处理原则相同
>
>    - 行首空白字符（空格符，制表符），行尾空白字符（空格符，制表符）默认不会处理 
>    - 所有的换行符（回车）都不会显示（行首、行中、行尾）
>    - 行中的空白符（空格、制表）只会显示一个空格间距
>
> 2. css 溢出换行处理
>
>    display: inline 不存在溢出换行处理的问题
>
>    display: block / block-inline 需要考虑溢出换行处理问题
>
>    - 连续的字母数字不会自动换行，利用 overflow 来处理溢出字符的显示
>
>      ```css
>      // overflow -- 溢出处理: 隐藏/滚动（显示滚动条）/可见（默认）
>      overflow: hidden/scroll/visible(d)/inherit
>      // text-overflow 必须和overflow: hidden一起使用才有效果
>      overflow: hidden;
>      text-overflow: clip(修剪文本) / ellipsis(省略号);
>      ```
>
>    - 遇到空白字符（空格）、汉字默认会自动换行（在不换行就会溢出的情况下，反之如果不换行也不会溢出就不会自动换行）: 换行的位置，从后往前找第一个可以换行的地方换行

```css
// 文本空白处理方式：
	normal-默认：溢出自动换行 --- 最常用
	  1. 去掉首尾空白字符 2. 多个空白字符（空格、制表）、回车转换成一个 空白字符 3. 不保留回车
   	nowrap: 溢出不会自动换行 -- 比较有用
	  1. 去掉首尾空白字符 2. 多个空白字符（空格、制表）、回车转换成一个 空白字符 3. 不保留回车

	pre-line：溢出自动换行
	  1. 去掉首尾空白字符 2. 多个空白字符（空格、制表）转换成一个 空白字符 3. 保留回车(首个回车)
	pre-wrap: 溢出自动换行
      1. 保留所有空白字符（空格，制表、换行） 2. 保留回车(包括首个回车)

	pre: 同html中<pre>标签作用，整体同在html文档中相同格式显示，溢出不会自动换行
white-space: normal(d)/nowrap/pre/pre-line/pre-rap/inherit;
```

```
// 溢出自动换行：不换行 / 允许在单词内换行（无视溢出换行的规则，从溢出地方开始换行）
word-break: normal / break-all;
```

# 7. 可见性/区块/内联

|                     | `是否允许其他元素同处一行` | `width和 height 是否起作用` |
| ------------------- | -------------------------- | --------------------------- |
| `块状元素 -- <div>` | `no`                       | `yes`                       |
| `内联元素 -- <a>`   | `yes`                      | `no`                        |

```js
// 控制是否显示
// 可见性：none -- 显示(隐藏之后就不会再占据空间)
// 块状元素转化为内联元素：inline(所设置的宽度、高度无效)
// 融合块状、内联元素二者属性(宽度、高度有效)：inline-block(最常用，让两个块放置在同一行)
// 内联元素转化为块状元素：block 
// 内联元素中，margin/border/padding 属性依旧是有效的，只是效果会有所不同
display: none/inline/inline-block/block
// 可见性（同display最大区别：隐藏之后依旧占据空间）：可见/隐藏/隐藏表格项（不影响表格布局）/继承
visibility: visible/hidden/collapse/inherit
```

# 8. 文档流

> 标准文档流：
>
> ​	元素的排版布局过程中，元素会默认的自动从左往右（内联标签），从上往下的流式布局（块状标签）
>
> 非标准文档流：
>
> ​	元素脱离文档里之后将不再在文档流中占据空间，而是处于浮动状态（可以理解为漂浮在文档流的上面）

# 9. 定位

> static: 按照标准文档流进行定位
>
> relative: 相对于标准文档流的位置进行定位，并没有脱离标准文档流

```css
// position -- 位置
// （使用 top, bottom, left, right 或者 z-index 进行定位）
// fixed: 固定定位，相对于浏览器窗口进行定位，生成绝对定位元素，
//		  脱离标准文档流，相当于漂浮在页面上方（由于相对于浏览器窗口，不会随着滚动条滚动）
//        应用：流氓广告、回到顶部按钮
// absolute: 绝对定位，相对于 static 定位以外的（或者 body）第一个父元素进行定位，生成绝对定
// 位元素,脱离标准文档流，相当于漂浮在页面上方
// relative: 相对于其正常位置进行定位，生成相对定位的元素，并未脱离标准文档流，也就意味着不管通
// 过怎么改变元素位置，元素所占据的位置都是默认的标准文档流位置
// static: 默认值。没有定位，元素出现在正常的流中
//        （忽略 top, bottom, left, right 或者 z-index 声明）
position: fixed/absolute/relative/staic(d)/inherit
// 常规用法
// 子绝父相：子元素的绝对定位实际上相对的是 父元素的实际位置（而不是父元素在文档流中占据的固定位// // 置）
// 2. 相对的是父元素的 context 区域位置来进行 absolute 定位
// 定位层级：相当于 z 轴坐标，设置元素的堆叠顺序
// 只有元素定位为 absolute、fixed，relative 时z-index设置才有效（这些情况下有可能发生堆叠）
z-index: 数值/0(d)/1/-1
```

> 理解 position 定位坐标系
>
> "left: 20px" : 向元素的 LEFT 位置添加 20 像素                                    |  20px   ■
>
> "right: 20px" : 向元素的 RIGHT位置添加 20 像素                                       ■ 20PX |
>
> 如果是 %，参照物是当前元素的父元素
>
> transform： 设置的值为 % 时，参照物是自身大小
>
> 总结：盒子向内方向为正

```css
// overflow -- 溢出处理: 隐藏/滚动（显示滚动条）/可见（默认）
overflow: hidden/scroll/visible(d)/inherit
```

```css
// 
float -- 浮动（脱离标准文档流），设置 z-index 无效，浮动意味着漂浮在上面，脱离标准文档流
// 浮动的框可以向左或者向右移动，直到他的外边缘碰到自身包含框或另一个浮动框的边框为止
// float 使用起来问题还是比较多的，慎用。。。。。。。。。。。。。。
// 虽然脱离了标准文档流，但还是会占据一定的位置的
// float 只能与 display: block 元素在一起使用，此时 块元素之间可以相互重叠在一起
// float 与 display: inline / inline-block 在一起使用效果很不好，相互之间不能重叠
// 左浮动/右浮动
float: left/right
// 清除浮动
clear: left/right/both
// 关键总结：
// 1. 一旦设置了 float 属性，则 元素的盒子模型 基本上可以说相当于 display: inline-block,
//    此时再去利用 display 设置盒子模型无效
// 2. 利用 float实现浮动的元素，虽然脱离了标准文档流，但该浮动元素能够与 display: block 元素
//    重叠，与 display: inline / inline-block 元素不能重叠，如果将发生重叠，则元素之间会发生
//    自适应的错位，以避免重叠
// 3. float 元素一定开始独占一行，后续其他元素在占有的这一行上布局
		如果不能独占一行，则会另起一行
```

> 浮动塌陷：浮动元素不会撑开高度为 auto 的父元素
>
> a. 直接设置父元素高度
>
> b. 通过伪元素实现： x::after { display: block;  content: '';   }
>
> ps: width / height : 设置为 auto，相当于 不设置

display: flex 中 子1flex 子2float 共存问题

> 父元素为 display: flex时，如果子元素有 float 布局，无效
>
> 父元素为 display: flex 时中子元素中的 float 布局无效

```html
    <style>
        .div1 {
            width: 600px;
            height: 300px;
            background-color: red;
            display: flex;
        }

        .div2 {
            width: 400px;
            height: 200px;
            background-color: blue;
            flex: 1;
        }

        .div3 {
            float: left;
            width: 200px;
            height: 250px;
            background-color: yellow;
            flex: 1;
        }
    </style>
```



# 10. 对齐方式

```css
/***************************** 块级对齐方式 ***************************/
// 外边距水平居中
style {
    margin: 0 auto;
}
// 定位居中
style {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}
// 子绝父相中，子元素 right / top 等值 百分比的时候，参考的是继承的 相对定位的 父元素，而不是
// 其自身的直接父元素（虽然大部分情况是直接父元素）
// position: relative 为百分比的时候，相对的是其自身直接父元素的值，而不是自身的宽高

/***************************** 文本对齐方式 ***************************/
// 内边距垂直居中
style {
    text-align: center;
    line-height: x(默认的 content 的 height);
}
```

# 11. 高级选择器

> 基本选择器
>
> a. id 选择器： #id { }
>
> b. 类选择器： .class { }
>
> c. 标签选择器：p { }
>
> d. 并集选择器： p, a { }
>
> e. 交集选择器：p.class { }   // 第一个为标签选择，第二个为类选择器，之间不能有空格，很少使用
>
> f. 元素顺序选择器：a:first-child/nth-child(x)/last-child { }
>
> f1.  元素顺序选择器：a:nth-child(3n)：3的倍数的元素

> 高级选择器
>
> a. 后代选择器：div p { }          // 不考虑层级，只要是子元素就可以
>
> b. 子元素选择器：div>div2>a { }    // 必须是直接子元素，只能选中直接子元素，选择不到孙子级别
>
> c. 相邻兄弟选择器：div>a:nth-child(5)+.a6 { }        // 特指第六个元素
>
> d. 后续兄弟选择器：div>a:nth-child(5)~a { }           // 第五个元素后面的所有 <a> 元素
>
> f. 属性选择器：
>
> ​			a[属性名(class) = 属性值("div2")]   {  }

​				p[属性名(class) ^= 属性值("d")]   {  }    // 属性值以 "d" 开头的元素

​				div[属性名(class) $= 属性值("d")]   {  }    // 属性值以 "d" 结尾的元素

​				button[属性名(class) *= 属性值("d")]   {  }    // 属性值包含 "d" 的元素

# 12. 透明度与高斯模糊

```css
// 实现背景透明效果

// 三种效果完全相同：背景透明
// 透明度：0 ~ 1
opacity: x
// α 通道: 0 ~ 0.5 
background-color: rgba(x, x, x, a)
// 滤镜：0% ~ 100%
filter: opacity(x)

// 高斯模糊: xpx  值越大，模糊程度越大
filter: blur(4px)
```

```
// transform -- 移动变换
// 以自身盒子模型的中心作为移动变换中心
transform: 
	translate(x, y)/    translate3d(x, y, z)/transform(X/Y/Z)(x/y/z)
	scale(x,y)/         scale3d(x,y,z)/scale(X/Y/Z)(x/y/z)
	rotate(angle)/      rotate3d(x, y, z)/rotate(X/Y/Z)(x/y/z)
	skew(angle)  // 斜切，相对来说用的较少
```

```css
// 用于设置或检索弹性盒子元素在主轴（横轴）方向上的对齐方式。
justify-content: 
flex-start/center/flex-end: 项目位于容器的开头/中心/结尾
space-between: 项目在各行均匀分布，首尾没有间隙
space-around: 项目在各行均匀分布，首尾也各有 1/2 间隙
// 示例用法: 在弹性盒对象的 <div> 元素中均匀分布，并在各项周围留有空白
div
{
    display: flex;
    justify-content: space-around;
}
```

# 重要补充

# 1. 基线

```
标准四线格格式
---------------------------------------------  顶线

---------------------------------------------  中线
---------------------------------------------  基线
---------------------------------------------  底线

```

> 只有 display: inline-block  / inline 元素存在基线概念（block元素不可能并排放置）

### 1.1 display: inline-block 基线

> 1. 如果该元素中有 inline(文本) 元素，基线就是最后一行内联元素的基线。
> 2. 如果该元素内没有内联元素或者overflow不是visible，其基线就是margin的底边的外边缘。
>
> - 最终总结：等于行内所有行内元素中最低的基线
> - 基线由元素之间固有的关系决定，和 vertical-align 属性没有关系
> - 不要轻易变更决定 基线 的那个元素的位置和 vertical-align 属性值

### 1.2 display: inline 基线

> 1. 文本之类内联元素中，基线是字符x的下边缘位置 （标准基线位置）
> 2. 像`img`元素中基线就是下边缘（不常见）

# 2. 垂直对齐方式：vertical-align:

```css
// 线类，如 baseline、top、middle、bottom；
		top: 把元素的顶端与父元素的 content 区域的上边框对齐 -- 常常是父元素上边框
		middle: 把元素的中线与行中元素基线对齐
		baseline(d): 基线对齐
		bottom: 把元素的底端与行中最低的底素的对齐
// 文本类，如 text-top、text-bottom；
		text-top: 元素的顶端与父元素字体的顶端对齐
		text-bottom: 把元素的底端与父元素字体的底端对齐。
// 上标下标类，如 sub、super；
// 数值百分比类，如 10px、1em、5%；
vertical-align: 
```

# **CSS3**

# 13. 边框和背景

```css
// 边框
/**
* 盒子阴影效果: 外阴影  内阴影
* :inset h-shadow v-shadow blur color;
* h-shadow：必需。水平阴影的位置。允许负值 x轴
* v-shadow：必需。垂直阴影的位置。允许负值 y轴
* blur：可选。模糊的距离
* color: 可选。阴影的颜色
*/
box-shadow: 30px -30px 5px red;
// 边界圆角：圆角半径(默认没有圆角)
border-radius: normal(d)/10px/50%/10em/10rem/inherit;
border-(top-left/top-right/bottom-left/bottom-right)-radius: 单独设置每个角
// 图片边界: url地址("网络地址/本地相对地址/本地绝对地址")   重复/拉伸/铺满
border-image: url地址 repeat/stretch/round center center

// 背景
// 能够设置多张背景图片，以逗号分隔
background: 
	url("地址1") no-repeat top center,
	url("地址2") no-repeat center center,
	url("地址3") no-repeat bottom center;
// 背景尺寸: 宽width  高height/宽度方向填满/填满区域（不保证图片显示完全）
background-size: 100px/100px 200px/contain/cover
// 背景图片定位（只是定位方式，并不是能够填充的范围）: 根据 content 区域进行定位/ 包括内边距 / 包括边框
background-origin: content-box/padding-box/border-box
// 规定背景的绘制区域：
background-clip: content-box/padding-box/border-box(d)
sytle {
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
}
```

**私有前缀**

> - -webkit-       谷歌
> - -khtml-          老谷歌
> - -moz-            火狐
> - -ms-               IE
> - -O-                  欧鹏

# 14. 渐变

```css
// 线性渐变 -- 
// linear-gradient(to bottom/top left/right / 角度, c1, c2, c3,...)(默认从上到下)
background: linear-gradient(to bottom right/90deg, red, blue, green， gray, ...)
// 径向渐变（用的很少）-- radial-gradient
background: radial-gradient(red 40%, blue 40%， gray 20%)
```

# 15. 扩展小样式

```css
// 关闭默认样式
input/... {
    outline: none;  
}
// 使字体不能被选中
div {
    user-select: none;    // 可以继承
}
// 使多行文本块不能拖大/拖小
textarea {
    resize: none;
}

// !!!!! 很有用
// width/height: 默认是指 content 区域的宽和高
// 修改 width/height 所指：包括：boder + padding + content
box-sizing: border-box;
```

# 16. CSS3 过渡以及2D转换和3D转换

```css
// 复合属性：动画样式的过渡时间
//           all      0.5s      linear       0.1s 
transition: property duration time-function delay
// 规定设置过度效果的 css 属性的名称
transition-property: all/transform/width/height;
// 规定完成过渡效果所需要的时间
transition-duration: 0.5s;
// 规定速度效果的速度曲线
transition-time-function: linear/ease-in/...;
// 定义过渡效果何时开始
transition-delay: 
```

```
// 2d 转换
// transform -- 移动变换
// 以自身盒子模型的中心作为移动变换中心
transform: 
	translate(x, y)/    translate3d(x, y, z)/transform(X/Y/Z)(x/y/z)
	scale(x,y)/         scale3d(x,y,z)/scale(X/Y/Z)(x/y/z)
	rotate(angle)/      rotate3d(x, y, z)/rotate(X/Y/Z)(x/y/z)
	skew(angle)  // 斜切，相对来说用的较少
	perspective(500px)  // 透视距离，近大远小
// 旋转中心点：盒子模型的中心为旋转点
transform-origin: 0% 0%(默认是 50% 50%);

transform-style: preserve-3d;
```

# 17. 动画属性

# 18. 弹性布局

```css
// float -- 浮动（脱离标准文档流），浮动意味着漂浮在上面，脱离标准文档流
// 左浮动/右浮动
// 效果：一行放不下的时候，会自动换到下一行，元素之间无间隙
float: left/right

// 未脱离标准文档流
// 效果：一行放不下的时候，会自动换到下一行，元素之间会有间隙
display: inline-block

// 弹性容器：只能设置在父元素中(水平方向排列时自适应父元素宽度，竖直方向排列时则不会)
// 布局行为有点类似 display: block，都是必须独占一行
// width: auto 是宽度为父元素的宽度
display: flex; 
// 控制弹性容器的排列方向：从左到右 / 从右到左 / 从上到下 / 从下到上
flex-direction: row(d) / row-reverse / column / column-reverse
// 在主轴上规定元素排列方式
// 控制弹性容器的内容对齐：紧挨行头填充 / 紧挨行尾填充 / 居中 / 平均分布(行头无间隙 / 行头有间隙)
justify-content: flex-start(d) / flex-end / center / space-between / space-around
// 在垂直纵轴方向规定排列方式，纵轴内容对齐
// 控制弹性容器的内容对齐：在最上面对齐 / 在最下面对齐 / 竖直方向居中 （都是在父元素内） 
// 整个弹性盒子的整理内容上移、居中、下移，和 flex-direction: column 作用不同，他是把每个元素
// 保持竖直排列
align-items: flex-start / flex-end / center 
// ！！！！！！！！ 有点意思
flex-direction: 决定子元素的分布方向
justify-content: 控制在分布方向主轴上的位置（不一定是水平,也可能是竖直，由flex-direction决定）
align-items：控制在主轴垂直方向上的位置（相对于主轴垂直方向）
// 在子元素中设置，父元素设置了 flex-wrap 后该属性无效
// 子元素侧轴自身对齐方式，只对该子元素有效
// 相当于 justify-content / allign-items 的作用
align-self: 
// 上对其 / 下对其 / 居中 /
flex-start(d) / flex-end / center / baseline/ stretch

// 弹性元素换行: 不换行(一行排列，压缩子元素，默认) / 正常换行（不压缩） / 翻转
flex-wrap: nowrap(d) / wrap / wrap-reverse / initial / inherit
// 一般与 flex-wrap 联合使用，效果等同于 align-items 
// 针对换行后的各行，而不是针对各个元素
align-content:  // 专门用来处理换行后的整体布局（作为 flex-wrap 的补充）
flex-start(d) / flex-end / center / space-between / space-around / stretch

// 子元素占比与顺序
flex: 1; // 左右子元素加起来，产生每个子元素所占的比例
// 优先级：数值越小，优先级越高，排列越靠前
order: 1;
 
// 控制是否显示
// 可见性：none -- 显示(隐藏之后就不会再占据空间)
// 块状元素转化为内联元素：inline(所设置的宽度、高度无效)
// 融合块状、内联元素二者属性(宽度、高度有效)：inline-block(最常用，让两个块放置在同一行)
// 内联元素转化为块状元素：block 
display: none/inline/inline-block/block
display: flex;  // 将整个布局设置为 弹性布局
```

```css
// flex 是一个组合属性
// flex-grow  flex-shrink flex-basis
// auto: 	1 1 auto
// none:    0 0 auto
// 数值： 数值 1 0%
// 默认值： 0 1 auto;  // 不扩展，保留自身设置宽度  按比例压缩 。。。
// flex-grow: 0; // 代表不扩展
// flex-shrink: 0; // 代表不压缩
膨胀：多出元素按比例膨胀，与自身长度无关
压缩：自身长度之比 与 设置比例 的乘积
flex: 
// flex 属性用于设置或检索弹性盒模型对象的子元素如何分配空间。
// flex 属性是 flex-grow、flex-shrink 和 flex-basis 属性的简写属性
// 膨胀分配是把  数量按比例分配膨胀
flex-grow: flex-grow 属性用于设置或检索弹性盒子的扩展比率;只按照设置的比例扩展，跟自身大小无关
			只有一个因素：该属性设置的值（和自身大小无关）
			默认值为 0；
            让第二个元素的宽度为其他元素的三倍：
            div:nth-of-type(1) {flex-grow: 1;}
            div:nth-of-type(2) {flex-grow: 3;}
            div:nth-of-type(3) {flex-grow: 1;}
// 
flex-shrink: flex-shrink 属性指定了 flex 元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 flex-shrink 的值。
	简单来说：超出父元素宽度时需要压缩，每个元素的压缩值按照超出总量按该值设置的比例分配
			两个因素：自身宽度 和 该属性设置的值
            flex-shrink的默认值为1
flex: flex-basis 属性用于设置或检索弹性盒伸缩基准值。
	设置了该值之后，相当于所设置的宽度无效了
	默认值： auto，长度由自身原生的长度决定
```



# 19. 字体图标库

1. font awesome **图标**

```html
// 字体图标，本质上还是属于字体，因此应用于字体的属性都可以用于子图图标
<i class="fa fa-car" />
<span class="fa fa-car" style="color: red;"/>
```

2. 阿里巴巴矢量图

# 20. 其余

1. 滚动标签: 用的不是特别多

```html
<marquee 
   style="height: 30px; line-height: 30px; background-color: red;"
   scrollamount="1"   // 动画速度
   direction="left"   // 执行方向 right up left down
/>
```

2. width /height 有效性：在标准文档流之外一定是有效的，之所以无效是由于处于标准文档流之内

> - width / height 其实一直是有效的，只有在
>
>   - 标准文档流 
>   - display: inline
>
>   时才会无效
>
> - 一旦盒子模型脱离标准文档流，即使是 内联元素，width / height 也是有效的

3. 盒子模型默认 display

> - div 默认：block
> - span 默认： inline
> - ::before / after 默认： inline



重中之重：

> font-size：指的是字体的高度，包括 中文和英文都一样
>
> 单纯的<span>高度由字体高度上下加3px组成
>
> 例如：font-size: 21px，则 <span> 高度为 21 + 6 = 27px
>
> 这里的高度属于 文本区

> 行高度还包括上下两层空白高度
>
> line-height: 30px;
>
> font-size: 20px; (26px)
>
> 上下两层空白为 3px
>
> 当未设置 height 的时候，line-height 可以起到 height 的作用，前提是盒子元素中必须有文本，
>
> 否则单纯的只设置 line-height 是起不到 height 的作用的

