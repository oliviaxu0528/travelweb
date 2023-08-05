# JavaScript - 第五天

## 一. 元素对象(dom elements  API)

###   1.1获取元素对象（get dom elements)

```javascript
doucment.getElementById('id名称')     //通过id名获取元素（一个）
document.getElementsByTagName('标签名称')   //通过标签名获取元素（一组）
document.getElementsByName('name名称')     //通过name属性获取元素（一组）
document.getElementsByClassName('class名称')  //通过classname获取元素（一组）
document.querySelector（'.class名称/#id名称/tagname'）  //通过id/classname/tagname获取元素（获取第一个符合条件的元素）
document.querySelectorAll('.class名称/#id名称/tagname')  //通过id/classname/tagname获取元素(获取符合条件的元素的集合，返回一个数组)
```

### 1.2 增加元素对象（add  element）

（1） 创建

```javascript
- document.createEelement('div') 创建元素节点
- document.createTextNode('一个TextNode') 创建文本节点
- innerHTML
- innerText
- 要克隆的元素.cloneNode(true)  
```

（2）加入

```javascript
- appendChild 追加到结尾处
- innerHTML
父元素.innerHTML = "要插入的内容"
- insertBefore 用法：将元素插入到某一个元素的前面
父元素.insertBefore( 新元素, 旧元素 );         // 将 新元素 插入到 旧元素 的前面
```

### 1.3 删除元素对象（remove   element）

```javascript
element.removeChild(child);        //删除子元素
```

### 1.4 修改元素对象   (Modify  element)

- 删除节点再加入

- innerHTML

- innerText

- replaceChild

  ```javascript
  parent.replaceChild(newChild,oldChild);
  //newChild是替换的节点，可以是新的节点，也可以是页面上的节点，如果是页面上的节点，则其将被转移到新的位置
  // oldChild是被替换的节点
  ```

## 二. 函数的特殊使用(Special use of functions)

   (**1**) **递归(recursion)**: 自身调用(复习)
       注意：

```javascript
       function fn(num){
           if(num<5){
               fn(num+1)
           }
           console.log(num)
       }

		* 递归函数
                  * 递归是循环(必须有循环终止条件)
                  * 文件操作 算法
```

   (**2**) **闭包(closure)**：闭包就是能够读取其他函数内部变量的函数
        注意：

```javascript
       * 闭包的返回值是函数
                  * 作用：将局部变量贮存在内存中,延长变量作用域。
                  * 使用：局部变量的累加计数,缓存

    由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露。解决方法是，在退出函数之前，将不使用的局部变量全部删除。

    严格来说，闭包需要满足三个条件：

            【1】访问所在作用域

            【2】函数嵌套

            【3】在所在作用域外被调用
```

   (**3**) **回调函数(callback function)**(重点)

```javascript
  1）回调函数:一个函数名作为另一个函数的参数使用
     注意：
        * callback函数作为参数
        * 算法都交给 callback 去完成

        * 使用： 
        arr.sort(function(a,b){
            return b-a
        })

   1) 回调函数使用
      定时器：

         (1) setTimeout: 单次定时器
             调用：延时n毫秒执行唯一的一次
             id=  setTimeout(fn名,毫秒数);
             id=  setTimeout(function(){...},毫秒数);
             清除定时器
               clearTimeout(定时器id);
         (2) setInterval:循环定时器(无限次)
             调用：每隔n秒执行定时器
             id = setInterval(fn名,毫秒数);
             id = setInterval(function(){...},毫秒数);

              清除定时器
               clearInterval(定时器id);
         注意：
             a. setTimeout,setInterval返回 id号，
               将来用来清除定时器用的

             b. setTimeout,setInterval 异步执行
```

## 三. 对象(object)

​	对象就是一个键值对的集合

```javascript
(1) 对象(object): js一切皆对象,客观存在的具体事物

   例如:

      女朋友：
         特性(属性:变量): 大眼睛 长头发 身高
         行为(方法:函数):
                长跑冠军
                会做饭
                会唱歌

      别人的汽车 ：
          特性(属性:变量):颜色,轮胎型号,油耗...
          行为(方法:函数):
                  时速

(2) 类(class)：抽象出的一类事物

       人类   男生类   女生类

       车类   宝马车类  保时捷车类

       动物类  猫科类
```

   (3) 类和对象关系：

```javascript
      类模板 , 对象实例
      所以： 获得对象必须用实例化对象
     //$boy = new Person();
```

   (4) js 对象

```javascript
     一切皆对象 都可以用  var obj = new Object(); 实例化出一个对象

注意：

      Object 超类 基类, 会找js封装系统的各种数据类型对象下面的 属性和方法
```

#### js 对象（Object）

   对象是一个复杂数据类型,其实说是复杂，但是没有很复杂，只不过是存储了一些基本数据类型的一个集合。

​	任何不是基本类型（string,number,boolean,null,undefined）的值都是对象。

   (1)一切皆对象
    注意：所有可以 new Object() 实例化出任意 类型的对象
    例如： 已经存在 ：Number对象  String对象,Boolean对象

   (2) 自定义对象

​	**字面量的方式创建一个对象(object literal syntax)**

```javascript
// 创建一个空对象
var obj = {}

// 像对象中添加成员
obj.name = 'Jack'
obj.age = 18
obj['age'] = 19

//删除对象中的成员
delete obj.name
```

​	**内置构造函数的方式创建对象(built-in constructor syntax )**

```javascript
// 创建一个空对象
var obj = new Object()

// 向对象中添加成员
obj.name = 'Rose'
obj.age = 20

//删除对象中的成员
delete obj.name
```

  `Object` 是 `js` 内置给我们的构造函数，用于创建一个对象使用的

 (3) 构造函数特性：

```javascript
    构造函数是一种特殊的函数，主要用来初始化对象
    	通过构造函数可以快速创建多个类似的对象
	(1) 所有实例化对象都指向 构造函数constructor
    (2) 原型链__proto__ ：实现继承的,并且 可以 对象.__proto__查找 属性和方法
        (放在：prototype原型中的属性和方法)

    (3) prototype原型中的属性和方法
```

## 四. 字符串（String ）

### 4.1定义字符串

```javascript

const str = 'hello'
const str1 = "hello"
const str2 = `hello`     //template literals  模板字符串
在模板字符串中使用变量/表达式    ${}
const str3 = `I say ${str} world`
```

### 4.2 String对象的方法和属性 （methods && properties）

```javascript
(1) str.length  ：获得字符串长度
(2) str.concat() : 字符串的连接
(3) str.trim(): 清除两边的空格
(4) str.slice(start,end):返回字符串中的从start编号到end编号(不包含end)子字符串
(5) str.substring(start,end):同上
(6) str.substr(start,length):返回字符串中从start编号到指定长度length的子字符串
(7) str.indexOf():返回指定字符串的首次出现的编号位置, 失败返回-1
    str.lastIndexOf():返回指定字符串的最后出现的编号位置, 失败返回-1

(8) str.search():返回指定字符串的首次出现的编号位置, 一般结合正则使用效率高, 失败返回-1

(9) str.split(): 将字符串分隔成数组

(10) str.replace(原串,目标串): 字符串替换 ,一般结合正则丰富

(11) str.charAt():返回编号对应的字符串中的字符

(12) str.toLowerCase():转小写字符串
(13) str.toUpperCase():转大写字符串

(14)  str.match():查找指定字符串的返回的数组的字符串,失败返回null
```

  注意： 编号都是从0开始的 

  预习：

```javascript
 Math 数学对象 

 this 对象
 
 call() apply() bind()
```
