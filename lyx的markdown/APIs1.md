# Web API-1
## 1、DOM
文档树直观的体现了标签与标签之间的关系。

## 2、DOM节点

节点是文档树的组成部分，每一个节点都是一个 DOM 对象，主要分为元素节点、属性节点、文本节点等。

1. 【元素节点】其实就是 HTML 标签，如上图中 `head`、`div`、`body` 等都属于元素节点。
2. 【属性节点】是指 HTML 标签中的属性，如上图中 `a` 标签的 `href` 属性、`div` 标签的 `class` 属性。
3. 【文本节点】是指 HTML 标签的文字内容，如 `title` 标签中的文字。
4. 【根节点】特指 `html` 标签。

## 3、document
`document` 是 JavaScript 内置的专门用于 DOM 的对象，该对象包含了若干的属性和方法

```html
<script>
  // document 是内置的对象
  // console.log(typeof document);

  // 1. 通过 document 获取根节点
  console.log(document.documentElement); // 对应 html 标签

  // 2. 通过 document 节取 body 节点
  console.log(document.body); // 对应 body 标签

  // 3. 通过 document.write 方法向网页输出内容
  document.write('Hello World!');
</script>
```

## 4、获取DOM对象
1. querySelector   满足条件的第一个元素
 const 对象名 = document.querySelector('')
2. querySelectorAll  满足条件的元素集合 返回伪数组（有索引号有长度，但没有pop，push方法）
3. 简单了解即可
- getElementById：获取一类元素，专门获取元素类型节点，根据标签的 `id`  属性查找
- getElementsByTagName：类似标签选择器
- 任意 DOM 对象都包含 nodeType 属性，用来检检测节点类型

## 5、操作元素内容
1. `innerText` 将文本内容添加/更新到任意标签位置，文本中包含的标签不会被解析。
获取文字内容：console.log(对象.innerText)
修改：对象.innerText = '  '
2. `innerHTML` 将文本内容添加/更新到任意标签位置，文本中包含的标签会被解析。
总结：如果文本内容中包含 `html` 标签时推荐使用 `innerHTML`，否则建议使用 `innerText` 属性。

## 6、操作元素属性 
1、直接能过属性名修改
对象.属性 = ' '

2、控制样式属性，style来修改
对象.style.样式属性 = '值'
css 属性的 - 连接符与 JavaScript 的 减运算符冲突，所以要改成驼峰法

3、操作类名(className) 操作CSS
如果修改的样式比较多，直接通过style属性修改比较繁琐，我们可以通过借助于css类名的形式。
>注意：
>1.由于class是关键字, 所以使用className去代替
>2.className是使用新值换旧值, 如果需要添加一个类,需要保留之前的类名

4、通过 classList 操作类控制CSS
为了解决className 容易覆盖以前的类名，我们可以通过classList方式追加和删除类名
~~~javascript
        // 获取元素
        let box = document.querySelector('div')
        // 追加类（类名不加点，且为字符串
        // box.classList.add('active')
        // 移除类
        // box.classList.remove('one')
        // 切换类
        box.classList.toggle('one')
</html>
~~~

## 7、操作表单元素属性
表单很多情况，也需要修改属性，比如点击眼睛，可以看到密码，本质是把表单类型转换为文本框

正常的有属性有取值的跟其他的标签属性没有任何区别

获取:DOM对象.属性名

设置:DOM对象.属性名= 新值

~~~javascript
    // 1. 获取元素
    let input = document.querySelector('input')
    // 2. 取值或者设置值  得到input里面的值可以用 value
    // console.log(input.value)
    input.value = '小米手机'
    input.type = 'password'

    // 2. 启用按钮
    let btn = document.querySelector('button')
    // disabled 不可用   =  false  这样可以让按钮启用
    btn.disabled = false
    // 3. 勾选复选框
    let checkbox = document.querySelector('.agree')
    checkbox.checked = false
~~~

## 8、自定义属性
标准属性: 标签天生自带的属性 比如class id title等, 可以直接使用点语法操作比如： disabled、checked、selected

自定义属性：
在标签上一律以data-开头
在DOM对象上一律以dataset对象方式获取


## 9、间歇函数
`setInterval` 是 JavaScript 中内置的函数，它的作用是间隔固定的时间自动重复执行另一个函数，也叫定时器函数。

```html
<script>
  // 1. 定义一个普通函数
  function repeat() {
    console.log('不知疲倦的执行下去....')
  }

  // 2. 使用 setInterval 调用 repeat 函数
  // 间隔 1000 毫秒，重复调用 repeat
  setInterval(repeat, 1000)
</script>
```