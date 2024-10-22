# 一、js1
## 1、输出语法
- document.write()：向body输出，页面打印
- alert()
- console.log()

## 2、输入语法
prompt（）

## 3、常量
const,申明时必须赋值

## 4、变量
1. 申明用let/var，同一变量只能申明一次
2. 变量即盒子，用于储存
3. 临时变量temp
4. 变量名严格大小写，开头不能数字，能$、下划线

### 5、字符串
1. 单引号/双引号可以互相嵌套，但是不以自已嵌套自已
2. 必要时可以使用转义符 `\`，输出单引号或双引号

## 6、模版字符串
${变量名}
```
console.log('my name is ${username} and i am ${age}');
```

## 7、字符串内置方法
```
<!-- 大写 -->
console.log(s.touppercase());
<!-- 小写：tolowercase()
substring(,)：分割字符串
split(" "):将字符串分割成数组
 -->
 ```

## 8、数组 
1. 一组数据存在一个变量里
2. 声明数组：let 数组名 = [数据1, 数据2.....]
3. 使用数组：数组名[索引号]
```html
<script>
  // 1. 语法，使用 [] 来定义一个空数组
  // 定义一个空数组，然后赋值给变量 classes
  // let classes = [];
  // 2. 定义非空数组
  let classes = ['小明', '小刚', '小红', '小丽', '小米']
</script>
```

## 9、数据类型
1. 布尔类型boolean：true false
2. undefined：未定义
3. number：数字类型
4. null：空
5. string：字符串，要加单或双引号
需要看数据类型：console.log(typeof XXX)

## 10、类型转换
prompt中取过来的默认为字符串类型
1. 隐式转换
- 某些运算符被执行时，系统内部自动将数据类型进行转换，这种转换称为隐式转换。
- 加号会两边只要有一个字符串，就会把另一个也转为字符串
- 除了加号以外的会把数据转为数字类型
- 加号作为正号解析可以转换为数字型
2. 显式转换
通过 `Number` 显示转换成数值类型，当转换失败时结果为 `NaN`（Not a Number）即不是一个数字。
console.log(Number())
parseInt:取整数 parseFloat:浮点数

## 11、访问数组和数组索引
数据单元在数组中的编号称为索引值，也有人称其为下标。
```html
<script>
  let classes = ['小明', '小刚', '小红', '小丽', '小米']
  // 1. 访问数组，语法格式为：变量名[索引值]
  document.write(classes[0]) // 结果为：小明
</script>
```

#### 九九乘法表（b站39）42待学

## 12、操作数组（43-45）

数组做为对象数据类型，不但有 `length` 属性可以使用，还提供了许多方法：
1. 变量名[索引值] = 修改
2. push 动态向数组的尾部添加一个单元
3. unshit 动态向数组头部添加一个单元
4. pop 删除最后一个单元
5. shift 删除第一个单元
6. splice 动态删除任意单元

使用以上4个方法时，都是直接在原数组上进行操作，即原数组跟着发生相应的改变。并且在添加或删除单元时 `length` 并不会发生错乱。

```html
<script>
    // 定义一个数组
  let arr = ['html', 'css', 'javascript']
  // 1. push 动态向数组的尾部添加一个单元
  arr.push('Nodejs')
  console.log(arr)
  arr.push('Vue')

  // 2. unshit 动态向数组头部添加一个单元
  arr.unshift('VS Code')
  console.log(arr)

  // 3. splice 动态删除任意单元
  arr.splice(2, 1) // 从索引值为2的位置开始删除1个单元
  console.log(arr)

  // 4. pop 删除最后一个单元
  arr.pop()
  console.log(arr)

  // 5. shift 删除第一个单元
  arr.shift()
  console.log(arr)
</script>
```
### 综合案例47-49待学