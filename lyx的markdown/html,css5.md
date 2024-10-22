# day09-前端基础CSS第七天



## 字体图标（黑马102-105）
### 1、字体图标的下载
1、字库： http://icomoon.io
IcoMoon内容非常全面，遗憾是国外服务器，打开网速较慢
2、iconfont：http://www.iconfont.cn/  免费！

### 2、注意一下：
下载完毕之后，注意原先的文件不要删，后面会用。
把下载包里面的 fonts文件夹放入页面根目录下
- 注意：不同浏览器所支持的字体格式是不一样的，字体图标之所以兼容，就是因为包含了主流浏览器支持的字体文件。
1).TureType(  **.ttf**  )格式.ttf字体是Windows和Mac的最常见的字体，支持这种字体的浏览器有IE9+、Firefox3.5+、Chrome4+、Safari3+、Opera10+、iOS Mobile、Safari4.2+；
2).Web Open Font Format( **.woff** )格式woff字体，支持这种字体的浏览器有IE9+、Firefox3.5+、Chrome6+、Safari3.6+、Opera11.1+；
3).Embedded Open Type( **.eot** )格式.eot字体是IE专用字体，支持这种字体的浏览器有IE4+；
4).SVG(  .**svg**  )格式.svg字体是基于SVG字体渲染的一种格式，支持这种字体的浏览器有Chrome4+、Safari3.1+、Opera10.0+、iOS Mobile Safari3.2+；

### 3、通过css引入到我们页面中。
### 4、标签使用字体图标类名：iconfont icon-xxx（font class看类名）
### 5、给标签定义字体。
例：
  ```
   span {
     font-family: "icomoon";
   }
  ```
  注意：务必保证 这个字体和上面@font-face里面的字体保持一致 

### 6、 字体图标的追加
如果原来的字体图标不够用了，我们需要添加新的字体图标到原来的字体文件中。
把压缩包里面的 selection.json重新上传，然后选中自己想要新的图标，重新下载压缩包，并替换原来的文件


##  CSS 用户界面样式
### 1、 鼠标样式 cursor（具体的请问文小言）
### 2、轮廓线 outline
给表单添加 outline: 0;   或者  outline: none; 样式之后，就可以去掉默认的蓝色边框。
### 3、防止拖拽文本域 resize
```css
 textarea{ 
 	resize: none;
 }
```
### 4、vertical-align 属性应用

- 使用场景： 经常用于设置图片或者表单(行内块元素）和文字垂直对齐。
官方解释： 用于设置一个元素的垂直对齐方式，但是它只针对于行内元素或者行内块元素有效。
- 语法：
```css
vertical-align : baseline | top | middle | bottom 
```
- 图片、表单都属于行内块元素，默认的 vertical-align 是基线对齐。给图片、表单这些行内块元素的 vertical-align 属性设置为 middle 就可以让文字和图片垂直居中对齐了。

### 5、 解决图片底部默认空白缝隙问题
- bug：图片底侧会有一个空白缝隙，原因是行内块元素会和文字的基线对齐。
- 解决方法有两种：
1. 添加 vertical-align:middle | top| bottom 等。（提倡使用的）
2. 把图片转换为块级元素

## 7、常见布局技巧
### 1、margin负值的运用
1. 让每个盒子margin 往左侧移动 -1px 正好压住相邻盒子边框
2. 鼠标经过某个盒子的时候，提高当前盒子的层级即可（如果没有有定位，则加相对定位（保留位置），如果有定位，则加z-index）
### 2、文字围绕浮动元素（略）
### 3、 行内块的巧妙运用
页码在页面中间显示:
1. 把这些链接盒子转换为行内块， 之后给父级指定  text-align:center;
2. 利用行内块元素中间有缝隙，并且给父级添加 text-align:center; 行内块元素会水平会居中
### 4、 CSS 三角强化（去看黑马的案例吧！）

## 8、 CSS 初始化
为了消除不同浏览器对HTML文本呈现的差异，照顾浏览器的兼容，每个网页都必须首先进行 CSS初始化。
```
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}
li {
    list-style:none;
}
body{
    font:14px/1.5"Microsoft Yahei","Hiragino Sans GB","WenQuanYi Micro Hei",sans-serif;
    color:#333;

}

a{
    color:#333;
    text-decoration: none;
}
```
## 9、keyframes
1. 语法：
   ```css
   @keyframes animation-name{
    0%{
        <!-- 动画开始时的样式 -->
    }
    100%{
        <!-- 动画结束时的样式 -->
    }
   }
   ```
2. 要使用keyframes创建动画，还需要将动画绑定到具体的元素上，并设置动画的持续时间、播放方式等属性。这通常是通过CSS的animation属性来实现的。animation属性是一个复合属性，它包含了多个子属性，如animation-name（动画名称）、animation-duration（动画持续时间）、animation-timing-function（动画播放方式）、animation-delay（动画延迟时间）、animation-iteration-count（动画播放次数）和animation-direction（动画播放方向）等。