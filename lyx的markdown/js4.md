# JavaScript4
## 1、对象
对象是数据类型的一种，由属性和方法组成，无序
## 2、语法
```
let 对象名 = {
  属性名：属性值，
  方法名：函数}
```
1. 属性都是成 对出现的，包括属性名和值，它们之间使用英文 `:` 分隔
2. 多个属性之间使用英文 `,` 分隔
3. 属性就是依附在对象上的变量
4. 属性名可以使用 `""` 或 `''`，一般情况下省略，除非名称遇到特殊符号如空格、中横线等
5. 属性访问：声明对象，并添加了若干属性后，可以使用 `.` 或 `[]` 获得对象中属性对应的值
6. 增与改的语法:对象名.属性=新值
7. （了解一下就行了）删：delete 对象名.属性

扩展：也可以动态为对象添加属性，动态添加与直接定义是一样的，只是语法上更灵活。
```javascript
  // 声明一个空的对象（没有任何属性）
let user = {}
  // 动态追加属性
  user.name = '小明'
  user['age'] = 18  
```

## 3、方法和调用
数据行为性的信息称为方法，一般是动词性的，其本质是函数。
1. 方法是由方法名和函数两部分构成，它们之间使用 : 分隔
2. 多个属性之间使用英文 `,` 分隔
3. 方法是依附在对象中的函数
4. 方法名可以使用 `""` 或 `''`，一般情况下省略，除非名称遇到特殊符号如空格、中横线等

方法调用的语法：
对象名.方法名（）

扩展：也可以动态为对象添加方法，动态添加与直接定义是一样的，只是语法上更灵活。

```javascript

    // 声明一个空的对象（没有任何属性，也没有任何方法）
	let user = {}
    // 动态追加属性
    user.name = '小明'
    user.['age'] = 18
    
    // 动态添加方法
    user.move = function () {
      console.log('移动一点距离...')
    }
    
```
小经验：大括号外用=内用：
注：无论是属性或是方法，同一个对象中出现名称一样的，后面的会覆盖前面的。

## 4、null

null通常只用它来表示不存在的对象。使用 typeof 检测类型它的类型时，结果为 `object`。

## 5、遍历对象
for k in obj:获得对象属性是k,获得对象值是obj[k]
k是属性名，对象名[k]是获得属性值
~~~javascript
let obj = {
    uname: 'pink'
}
for(let k in obj) {
    // k 属性名  字符串  带引号    obj.'uname'     k ===  'uname'
    // obj[k]  属性值    obj['uname']   obj[k]
}
~~~
for in 不提倡遍历数组 因为 k 是 字符串  

## 6、内置对象

`console.log`，`console`其实就是 JavaScript 中内置的对象，该对象中存在一个方法叫 `log`，然后调用 `log` 这个方法，即 `console.log()`。

## 7、Math
Math 是 JavaScript 中内置的对象，称为数学对象。
可在mdn中看
- Math.random生成 0 到 1 间的随机数
- Math.ceil()数字向上取整
- Math.floor()数字向下取整
- Math.round()四舍五入取整
- Math.max()在一组数中找出最大的
- Math.min()在一组数中找出最小的

```javascript
// 找出最小值
Math.min(24, 18, 6, 19, 21)
```

- Math.pow幂方法
```javascript
// 求某个数的多少次方
Math.pow(4, 2) // 求 4 的 2 次方
```

- Math.sqrt平方根

```javascript
// 求某数的平方根
Math.sqrt(16)
```
#### 记得看黑马程序员72-76
## 8、splice
splice() 方法用于添加或删除数组中的元素。
splice(起始位置， 删除的个数)
比如：1
~~~javascript
let arr = ['red', 'green', 'blue']
arr.splice(1,1) // 删除green元素
console.log(arr) // ['red, 'blue']
~~~

添加元素：
splice(起始位置，删除个数，添加数组元素)
~~~javascript
let arr = ['red', 'green', 'blue']
//arr.splice(1, 0, 'pink') // 在索引号是1的位置添加 pink，0表示的是不会删除元素
//console.log(arr) // ['red', 'pink', 'green', 'blue']
arr.splice(1, 0, 'pink', 'hotpink') // 在索引号是1的位置添加 pink  hotpink
console.log(arr) // ['red', 'pink', 'hotpink', 'green', 'blue']
~~~

注意：这种方法会改变原始数组。

删除数组：
~~~javascript
let arr = ['red', 'green', 'blue']
arr.splice(2,1) // 在索引号是2的位置开始删除一个元素
console.log(arr) // ['red', 'pink', 'hotpink', 'green', 'blue']
~~~
