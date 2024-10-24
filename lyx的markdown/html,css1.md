# css笔记（一）

## 一、快速写代码
- 输入标签名 按tab键即可   比如  div   然后tab 键， 就可以生成 <div></div>
- 多个相同标签  加上 * n
- 如果有父子级关系的标签，可以用 >  比如   ul > li就可以了
- 如果有兄弟关系的标签，用  +  就可以了 比如 div+p  
- 如果生成带有类名或者id名字的，  直接写  .demo  或者  #two   tab 键就可以了
- 如果生成的div 类名是有顺序的， 可以用 自增符号  $ 
- 如果想要在生成的标签内部写内容可以用  { }  表示
​- w200   按tab  可以 生成  width: 200px;
- 比如 lh26px   按tab  可以生成  line-height: 26px;
- Vscode  快速格式化代码:   shift+alt+f
- *可代表所有标签

- 也可以设置 当我们 保存页面的时候自动格式化代码:
1）文件 ------.>【首选项】---------->【设置】；
2）搜索emmet.include;
3）在settings.json下的【工作区设置】中添加以下语句：
​		"editor.formatOnType": true,
​		"editor.formatOnSave": true

## 二、css的复合选择器

### 1、常用的复合选择器
包括：后代选择器、子选择器、并集选择器、伪类选择器等

### 2、后代选择器
语法说明：
- 元素1 和 元素2 中间用空格隔开
- 元素1 是父级，元素2 是子级，最终选择的是元素2
- 元素2 可以是儿子，也可以是孙子等
- 元素1 和 元素2 可以是任意基础选择器

### 3、子选择器
语法说明：
- 元素1 和 元素2 中间用 大于号 隔开
- 元素2 必须是亲儿子，其孙子、重孙之类都不归他管

### 4、并集选择器 
语法说明：
- 元素1 和 元素2 中间用逗号隔开
- 逗号可以理解为和的意思
- 并集选择器通常用于集体声明

### 5、伪类选择器
伪类选择器书写最大的特点是用冒号（:）表示，比如 :hover 、 :first-child

​		a:link	没有点击过的(访问过的)链接
​		a:visited	点击过的(访问过的)链接
​		a:hover	鼠标经过的那个链接
​		a:active	鼠标正在按下还没有弹起鼠标的那个链接
注意：为了确保生效，请按照 LVHA 的循顺序声明 :link－:visited－:hover－:active。
记忆法：lv  hao

### 7、:focus 伪类选择器
定义：focus 伪类选择器用于选取获得焦点的表单元素。
焦点就是光标，一般情况input类表单元素才能获取

## 三、css的显示模式

### 1、什么是元素的显示模式
​		元素显示模式就是元素（标签）以什么方式进行显示，比如<div>自己占一行，比如一行可以放多个<span>。

### 2、元素显示模式的分类

**块元素**：
```<h1>~<h6>、<p>、<div>、<ul>、<ol>、<li>```

**块级元素的特点**：
- 独占一行。
- 高度，宽度、外边距以及内边距都可以控制。
- 宽度默认是容器（父级宽度）的100%。
- 是一个容器及盒子，里面可以放行内或者块级元素。
- 文字类的元素内不能放块级元素
- p标签主要用于存放文字，因此p里面不能放块级元素，特别是不能放div,同理，h1~h6等都是文字类块级标签，里面也不能放其他块级元素

**常见行内元素：**
```
<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>
```

**行内元素的特点：**
- 相邻行内元素在一行上，一行可以显示多个。

- 高、宽直接设置是无效的。

- 默认宽度就是它本身内容的宽度。

- 行内元素只能容纳文本或其他行内元素。

**注意：**
	链接里面不能再放链接
	特殊情况链接a里面可以放块级元素，但是给a转换一下块级模式最安全

**常见的行内块标签**：
```
<img />、<input />、<td>
```
**行内块元素的特点**：
- 和相邻行内元素（行内块）在一行上，但是他们之间会有空白缝隙。
- 默认宽度就是它本身内容的宽度（行内元素特点）。
- 高度，行高、外边距以及内边距都可以控制（块级元素特点）。

### 3、元素显示模式的转换
**转换方式**
- 转换为块元素：display:block;
- 转换为行内元素：display:inline;
- 转换为行内块：display: inline-block;

### 4、单行文字垂直居中的代码
让文字的行高等于盒子的高度  就可以让文字在当前盒子内垂直居中
## 四、css的背景
1. 背景颜色background-color
2. 背景图片background-image
3. 注意：背景图片后面的地址，千万不要忘记加 URL， 同时里面的路径不要加引号。
4. 背景平铺
background-repeat
5. 背景图片位置
- background-position
- 使用方式：参数代表的意思是：x 坐标和 y 坐标。 可以使用方位名词或者精确单位
- 如果指定的两个值都是方位名词，则两个值前后顺序无关，比如 left  top 和 top  left 效果一致
- 如果只指定了一个方位名词，另一个值省略，则第二个值默认居中对齐
- 如果参数值是精确坐标，那么第一个肯定是 x 坐标，第二个一定是 y 坐标
- 如果只指定一个数值，那该数值一定是 x 坐标，另一个默认垂直居中
- 如果指定的两个值是精确单位和方位名词混合使用，则第一个值是 x 坐标，第二个值是 y 坐标
6. background-attachment 属性设置背景图像是否固定或者随着页面的其余部分滚动。后期可以制作视差滚动的效果。
7. 合写
​background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置;
8. 背景色半透明
这里就不详细记录了哈，如果忘了的话就去问文小言吧