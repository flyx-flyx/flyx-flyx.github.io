# css3

## 一、其他样式	

### 1、圆角边框
语法：
```css
 border-radius:length;    
```

- 参数值可以为数值或百分比
- 如果是正方形，想要设为圆，把数值修改为高度或者宽度的一半即可，或者直接写为 50%
- 该属性是一个简写属性，可以跟四个值，分别代表左上角、右上角、右下角、左下角
- 分开写：border-top-left-radius、border-top-right-radius、border-bottom-right-radius 和border-bottom-left-radius

### 2、盒子阴影
语法：
```css
 box-shadow: h-shadow v-shadow blur spread color inset; 
```
- h-shadow：水平阴影的位置，即阴影在x轴上的偏移量，有正有负哦！
- v-shadow：垂直阴影的位置
- blur：阴影的模糊半径。值越大，阴影越模糊。如果设置为0，则阴影是完全实心的，没有任何模糊效果。不支持负数。
- spread：阴影的扩展半径。正值表示阴影在元素的四个方向延伸，负值表示阴影缩小至比元素本身尺寸还要小。默认值为0，与元素大小相同。
- color：阴影的颜色。默认为黑色。
- inset（可选）：将阴影设置为内阴影。
### 3、文字阴影
语法：
```css
 text-shadow: h-shadow v-shadow blur color;
```
参考盒子阴影
## 二、浮动
### 1、特性
1. 标准流（普通流/文档流）即默认。
2. 回顾一小下吧：块级元素会独占一行，常用元素：div、hr、p、h1~h6、ul、ol、dl、form、table。行内元素从左到右顺序排列，碰到父元素边缘自动换行。常用元素：span、a、i、em 等
4. 浮动：多个块级元素一行内排列显示；属性名：float；属性值：left和right
5. 网页布局准则：多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动。
6. 浮动的元素会具有行内块元素的特性，如果父级宽度装不下，多出的盒子会另起一行，解决办法：margin设为0
### 2、注意
1. 浮动和标准流的父盒子搭配。先用标准流的父元素排列上下位置, 之后内部子元素采取浮动排列左右位置
2. 一个盒子里面有多个子盒子，如果其中一个盒子浮动了，其他兄弟也应该浮动，以防止问题。
3. 浮动的盒子只会影响浮动盒子后面的标准流,不会影响前面的标准流.

### 3、清除浮动
​1、原因：由于父级盒子很多情况下，不方便给高度，但是子盒子浮动又不占有位置，最后父级盒子高度为 0 时，就会影响下面的标准流盒子。浮动的子标签无法撑开父盒子的高度。
2、注意：
- 如果父盒子本身有高度，则不需要清除浮动
- 清除浮动之后，父级就会根据浮动的子盒子自动检测高度。
3、方法
1. 在浮动元素末尾加额外标签
 ```css
 .clearfix{clear:both;} 
```

```html
 <div class="clearfix">
 ```
2. 单伪元素法：
```css
 .clearfix:after {  
   content: ""; 
   display: block; 
   height: 0; 
   clear: both; 
   visibility: hidden;  
 } 
 .clearfix {  /* IE6、7 专有 */ 
   *zoom: 1;
 }   
```
3. 双伪元素法（常用）：
```css
 .clearfix:before,.clearfix:after {
   content:"";
   display:table; 
 }
 .clearfix:after {
   clear:both;
 }
 .clearfix {
    *zoom:1;
 }   
```
4. 父级添加 overflow 属性，属性值设置为 hidden、 auto 或 scroll 。
```css
overflow:hidden | auto | scroll;
```

## 三、flex（比浮动更好用）
1. 用法：父元素加display：flex，子元素可自动挤压拉伸
2. 主轴对齐方式：
 属性名：justify-content（也是给父级加哦！）
 属性值
- center
- space-between：弹性盒子之间有空白间距
- space-around：两侧有空白
- space evenly：每个间距都相等
3. 侧轴对齐方式：
  属性名：1.align-items（所有）2.align-self（某个）
  属性值：1.stretch（侧轴方向没有尺寸时拉伸）2.center 3.flex-start 4.flex-end
4. 改主侧轴方向（主轴默认水平）
 属性名：flex-direction
 属性值：colume
5. 弹性伸缩比（这一块注意理解一下！） 
 属性名：flex
 属性值：整数
 6. 换行
  属性名：flex-wrap
  属性值：wrap（nowrap不换行）
 7. 行对齐方式  align-content
  - space-between/around/evenly
  - center
  
## 2. CSS属性书写顺序
1. **布局定位属性**：display / position / float / clear / visibility / overflow（建议 display 第一个写，毕竟关系到模式）
2. **自身属性**：width / height / margin / padding / border / background
3. **文本属性**：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. **其他属性（CSS3）**：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient
