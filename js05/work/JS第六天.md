# JavaScript - 第六天


## 一. this 对象 (*重点)

### 1.1 this 指向

  (1) 全局作用域下 this 指 window对象 
   (2) 构造函数中 this 指实例化对象
   (3) 普通函数中 this 指window对象
   (4) 对象下面的方法 this 指该对象

   总结： this 只有在对象下 指向该对象,其他指向全局作用域下window对象

### 1.2 call(), apply()，bind() 使用

  (1) 函数调用
      fn()  fn.call()  fn.apply()    fn.bind()

 （2）参数不同

```javascript
 fn.call(对象,参数1,参数2,参数3,...)
 fn.apply(对象,[参数1,参数2,参数3,...]) 参数是数组
 
 let newFn = fn.bind(对象)
 newFn()
```

  (3) 参数对象可以改变this指代 

## 二. Math 对象

 (1) Math.max() 最大值
 (2) Math.min() 最小值

 (3) Math.pow(base,exp) 求n次幂 3^n 4^n
 (4) Math.sqrt(x)  开平方  例如： 4开平方 2
 (5) Math.abs(x)   绝对值

 (6) Math.round(x) 四舍五入
 (7) Math.ceil(x)  向上取整
 (8) Math.floor(x) 向下取整

 (9) Math.random() 求随机小数

 ## 三. 时间日期对象(date)

```javascript
  var d = new Date();    //获取当前时间

  (1) d.getFullYear() 获得4位年
  (2) d.getMonth() 获得月 0-11 数字
  (3) d.getDate() 获得日 1-31

  (4) d.getHours()  获得小时
  (5) d.getMinutes()  获得分钟
  (6) d.getSeconds()  获得秒
  (7) d.getDay() 一周中的星期几 0-6 
```




### 时间日期对象方法： 

```javascript
 (1) d.getTime() 获得时间戳: 从 1970-01-01 到现在的毫秒数
```

   Object 对象中的两个方法：

```javascript
   (2) d.valueOf(): 对象的值, 返回时间戳
   (3) d.toString()：将对象转为字符串
```




 ## 四. 数组（array）

  (1) 什么是数组：存数据的集合
  (2) 一维数组定义：

```javascript
 1） var arr = [值,值,值....];

 2)  var arr = new Array(值,值,值....);

 3)  var arr = new Array([长度]);  //只传入一个数字表示数组长度

     arr[0] ="tom";               //定义数组某一项的值
     arr[1] ="alice";
     arr[2] ="jerry";
```

   注意：

```javascript
  * 数组的值可以是任意数据类型
  * 输出某一个值 arr[下标]
```

   (3) 分类

```javascript
 1）索引数组：键名称是整数
 2）关联数组：键名称是字符串
```

  （4）一维数组的循环遍历

```javascript
 1）for 循环 ： 只能索引数组
 2）for...in 遍历索引和关联数组或对象
 3) arr.forEach(function(v,k){
        ...
 	})
```

   (5) 二维数组的循环遍历(重点)


   (6) 数组的方法：

```javascript
   1） arr.length 获得数组的长度
   2） arr.concat() 数组的连接

   3） arr.slice(start,end); 数组的截取，不包含end(包前不包后)

   4) arr.join('') 将数组转为字符串  str.split('') 将字符串转为数值

   5) arr.reverse(): 数组的反转
   6). arr.sort(fn): 数组的排序, 默认只能对字符串按位比较
```


```javascript
   7) arr.indexOf(): 返回数组值的首次编号位置

      arr.lastIndexOf():返回数组值的最后编号位置
```


```javascript
   8） arr.splice(start,length,[添加替换的内容]): 返回删除的数组
   9)
      arr.push(): 尾部添加一个或多个数组的成员值,并且返回新数组长度
      arr.unshift():头部添加一个或多个数组的成员值,并且返回新数组长度

      arr.pop():  尾部删除一个成员值,并返回改值
      arr.shift():  头部删除一个成员值,并返回改值
```


```javascript
   10). arr.forEach(fn)  :遍历数组
   11). arr.map(fn) : 映射
   
   12). arr.filter(fn)：过滤器，过滤出符合条件的数组
```


```javascript
预习：

    正则
```
