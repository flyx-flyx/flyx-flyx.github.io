# JavaScript2

## 1、算术运算符
算术运算符：与c语言类似
> 注意：在计算失败时，显示的结果是 NaN （not a number）

```javascript
// 算术运算符
console.log(1 + 2 * 3 / 2) //  4 
let num = 10
console.log(num + 10)  // 20
console.log(num + num)  // 20

// 1. 取模(取余数)  使用场景：  用来判断某个数是否能够被整除
console.log(4 % 2) //  0  
console.log(6 % 3) //  0
console.log(5 % 3) //  2
console.log(3 % 5) //  3

// 2. 注意事项 : 如果我们计算失败，则返回的结果是 NaN (not a number)
console.log('pink老师' - 2)
console.log('pink老师' * 2)
console.log('pink老师' + 2)   // pink老师2
```
// // 1. 前置自增
    // let i = 1
    // ++i
.log(i++ + 1)

## 2、赋值运算符
+= 加法赋值
-+ 减法赋值
*= 乘法赋值
/= 除法赋值
%= 取余赋值

## 3、自增/自减运算符
++：变量自身的值加1
--：变量自身的值减1
1. ++在前和++在后在单独使用时二者并没有差别，
2. ++在后我们会使用更多
3. 前置自增：先加；后置自增：后加 

## 4、比较运算符
1.>=：左边是否大于或等于右边
<=：左边是否小于或等于右边             
=== ：左右两边是否`类型`和`值`都相等（重点）
== ： 左右两边`值`是否相等                  
!=  ：左右值不相等                          
!== ：左右两边是否不全等

## 5、逻辑运算符
&&：并且
||：逻辑或
!：逻辑非：取反
逻辑运算符优先级： ！> && >  ||  

## 6、if分支语句
~~~javascript
if (条件表达式){
  // 满足条件要执行的语句
}
~~~
小括号内的条件结果是布尔值，为 true 时，进入大括号里执行代码；为false，则不执行
小括号内的结果若不是布尔类型时，会发生类型转换为布尔值
1. 除了0 所有的数字都为真
2. 除了 '' 所有的字符串都为真

## 7、if双分支语句
如果有两个条件的时候，可以使用 if else 双分支语句
~~~javascript
if (条件表达式){
  // 满足条件要执行的语句
} else {
  // 不满足条件要执行的语句
}
~~~

例如：
~~~javascript
 <script>
    // 1. 用户输入
    let uname = prompt('请输入用户名:')
    let pwd = prompt('请输入密码:')
    // 2. 判断输出
    if (uname === 'pink' && pwd === '123456') {
      alert('恭喜登录成功')
    } else {
      alert('用户名或者密码错误')
    }
  </script>
~~~

## 8、if多分支语句
略，和c语言类似

## 9、三元运算符
一些简单的双分支，可以使用三元运算符，一般用于取值
~~~javascript
条件 ? 满足条件执行的表达式 ： 不满足执行的表达式
~~~
### 27数字补0案例未看
## 10、switch语句（29未看）

使用场景： 适合于有多个条件的时候，也属于分支语句，大部分情况下和 if多分支语句 功能相同
注意：
1. switch case语句一般用于等值判断, if适合于区间判断
2. switchcase一般需要配合break关键字使用 没有break会造成case穿透
3. if 多分支语句开发要比switch更重要，使用也更多
例如：
~~~javascript
// switch分支语句
// 1. 语法
// switch (表达式) {
//   case 值1:
//     代码1
//     break

//   case 值2:
//     代码2
//     break
//   ...
//   default:
//     代码n
// }
   - switch…case语句通常处理case为比较**确定值**的情况，而if…else…语句更加灵活，通常用于**范围判断**(大于，等于某个范围)。
   - switch 语句进行判断后直接执行到程序的语句，效率更高，而if…else语句有几种判断条件，就得判断多少次
   - switch 一定要注意 必须是 ===  全等，一定注意 数据类型，同时注意break否则会有穿透效果
   - 结论：
     - 当分支比较少时，if…else语句执行效率高。
     - 当分支比较多时，switch语句执行效率高，而且结构更清晰。
<script>
  switch (2) {
    case 1:
    console.log('您选择的是1')
    break  // 退出switch
    case 2:
    console.log('您选择的是2')
    break  // 退出switch
    case 3:
    console.log('您选择的是3')
    break  // 退出switch
    default:
    console.log('没有符合条件的')
  }
</script>
~~~

## 11、断点调试
1. 按F12打开开发者工具
2. 点到源代码一栏 （ sources ）
3. 选择代码文件

## 12、循环语句

1. while循环
~~~javascript
while (条件表达式) {
   // 循环体    
}
~~~
#### 31while循环大练习

2. for 循环（重点）

## 13、中止循环
1. break 中止整个循环，一般用于结果已经得到, 后续的循环不需要的时候可以使用
if (条件) {
break}

2. continue 中止本次循环，继续下一轮循环，一般用于排除或者跳过某一个选项的时候

## 14、无限循环

1.while(true) 来构造“无限”循环，需要使用break退出循环。（常用）
2.for(;;) 也可以来构造“无限”循环，同样需要使用break退出循环。
```script
for (; ;) {
  let love = prompt('你爱我吗?')
  if (love === '爱') {
    break
  }
}
```
语法格式：for(起始值; 终止条件; 变化量) {}
跳出和终止循环:continue与break同js2

## 15、循环嵌套
例：记了三天单词，每天记5个
```html
// 1. 外面的循环 记录第n天 
for (let i = 1; i < 4; i++) {
    document.write(`第${i}天 <br>`)
    // 2. 里层的循环记录 几个单词
    for (let j = 1; j < 6; j++) {
        document.write(`记住第${j}个单词<br>`)
    }
}
```
多理解几遍！！

#### 33综合案例-ATM存取款机