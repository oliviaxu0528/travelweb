# JavaScript - Day 08
## 一、DOM（Document Object Model）

 1. 什么是DOM: Document Object Model 文档对象模型

 2. 作用： HTML DOM :访问和操作节点的标准

###  1. 节点（node）： 

​	HTML DOM所有的对象都是节点,DOM 是节点树的HTML

   (1) 文档节点 (document)

   (2) 元素节点( element)
   (3) 属性节点( attribute)

   (4) 文本节点 (text)

   (5) 注释节点 

####   1.1 节点属性(node attributes) 

| -        | nodeType | nodeName   | nodeValue |
| -------- | -------- | ---------- | --------- |
| 元素节点 | 1        | 大写标签名 | null      |
| 属性节点 | 2        | 属性名     | 属性值    |
| 文本节点 | 3        | \#text     | 文本内容  |



    注意：   nodeType 类型    nodeName 名称   nodeValue值

####   1.2 节点关系(node relationship)

    (1) 子节点 childNodes
    
      注意： 非IE下会将换行解析为文本节点,使用 children 解决问题
    
    (2) 第一个和最后一个子节点
    
      node.firstChild
      node.lastChild
    
    (3) 兄弟节点
    
       node.nextSibling  下一个兄弟
       node.previousSibling  上一兄弟节点
    
    (4) 父节点parentNode 


    新增
    
       node.firstElementChild 第一个子节点
       node.lastElementChild  最后一个子节点
       node.nextElementSibling  下一个兄弟
       node.previousElementSibling  上一兄弟节点

####   1.3 访问节点(Access node)

    (1) 通过id名称获得元素节点 ：document.getElementById(id名称)  一个
    
    (2) 通过标签名称获得集合的元素节点： document或节点.getElementsByTagName(标签名) 集合
    
    (3) 通过class名称获得集合的元素节点  doucment.getElementsByClassName(class名称)   集合
    
    新
       通过选择器名称获得元素节点 ：document.querySelector(css选择器名称)  一个
       通过选择器名称获得集合的元素节点 ：document.querySelectorAll(css选择器名称)  集合

#### 1.4 操作节点(Operation node)

我们所说的操作无非就是 **增删改查CRUD（create, read, update, delete)**



    (1) 创建节点
    
       创建元素：   document.createElement(元素)
       创建属性：   document.createAttribute(属性) 了解
       创建文本：   document.createTextNode(文本) 
    (2)
         追加子元素: parentNode.appendChild(子元素) 
         前加子元素: parentNode.insertBefore(子元素,位置)
         删除子元素：parentNode.removeChild(子元素)
         复制元素  ： node.cloneNode(true)
         注意：  node.cloneNode(true) 才能将元素的内容一起复制 


### 2. 属性节点方法和属性:

```
### 元素节点方法和属性(重点)
(1) oBox.attributes  获得属性集合
(2) oBox.tagName  元素名称 
(3) oBox.setAttribute('属性名称','值') 设置
(4) oBox.getAttribute('属性名称')
(5) oBox.removeAttribute('属性名称')

h5自定义属性名   dataset
使用   data-属性名：属性值
<div id="dataset" data-food="noodle">$18.3</div>
 var box=document.getElementById('dataset');
 //获取自定义属性
 console.log(box.dataset.food);//noodle  
```

### 3. 文本节点方法和属性:
      oBox.innerHTML 
      oBox.innerText 

### 4. 文档节点方法和属性 (重点):

    (1) document方法
    
       document.write() : 浏览器输出
       document.writeln():浏览器输出，不同在表达式后面有换行符
        
       document.getElementById(id名称) 一个对象
       document|元素对象.getElementsByTagName(标记名)  集合
       document.getElementsByClassName(class名称)  集合

   (2) document属性对象: document.html标记名称

       document.body
       document.title
       document.head
       document.URL
       document.charset    //只读属性返回当前文档的字符编码
       document.documentElement   //html标记

  (3) document 集合

       document.anchors[]  获得有name属性 的a标签集合
       document.links[]    获得有href属性 的a标签集合
       document.images[]  获得多个图像集合
       document.forms[]   获得多个表单集合

  注意：
       document 在 window对象下面
       window对象是最大对象，所有全局的变量和函数都在window对象下

 ### 5. css 在 Dom 中的使用

     (1) 设置或获得 class名称
     oBox.className = 'on';
    
     (2) 设置或获得行内样式
    
     oBox.style.color='#f00';
     oBox.style.background="#00f"
     oBox.style.fontSize ='30px';....
    
     (3) 获得css选择器中的样式
    
        *非IE : window.getComputedStyle(obj,null)['css属性名称']
    
        * IE  : obj.currentStyle('css属性名称')
     注意：
    
        css 转为Dom的成员属性操作
    
        行内样式问题： 不能获得css选择器中的样式

## 二、 js事件（javascript event）

```
1.点击事件：

onclick：单击事件

ondblclick：双击事件

2.焦点事件

onblur：失去焦点

onfocus:元素获得焦点。

3.加载事件：

onload：一张页面或一幅图像完成加载。

4.鼠标事件：

onmousedown：鼠标按钮被按下。

onmouseup： 鼠标按键被松开。

onmousemove： 鼠标被移动。

onmouseover： 鼠标移到某元素之上。

onmouseout ：鼠标从某元素移开。

鼠标按下时，通过事件对象 event中的属性 button 或 which 可以获取鼠标按键的编号e.button 事件对象中的 button属性可以获取鼠标按键的编号e.which 也可以获取鼠标的按键编号 0左键 1滚轮 2右键

6.选择和改变
oninput： 表单中value值发生改变时触发

onchange ：域的内容被改变。

7.表单事件：

onsubmit ：确认按钮被点击。

onreset： 重置按钮被点击

 取消默认事件： e.preventDefault()
```

5.键盘事件：

onkeydown ：某个键盘按键被按下。

onkeyup： 某个键盘按键被松开。  

onkeypress ：某个键盘按键被按下并松开。和keydown 的区别在于不会去识别键盘上的ctrl，shift，箭头



![abc](F:\课件\JavaScript\Day08\notes\img\abc.png)

键码：

![cd](F:\课件\JavaScript\Day08\notes\img\cd.png)



## 三、获取元素的偏移量（offset of the element）

- 就是元素在页面上的什么位置
- 我们有几个属性来获取，**`offsetLeft`** 和 **`offsetTop`** 和 **`offsetWidth`** 和 **`offsetHeight`**



### 3.1 offsetLeft 和 offsetTop

- 获取的是元左边的偏移量和上边的偏移量
- 分成两个情况来看
- 没有定位的情况下
  - 获取元素边框外侧到页面内侧的距离
- 有定位的情况下
  - 获取元素边框外侧到定位父级边框内侧的距离（其实就是我们写的 `left` 和 `top` 值）



### 3.2 offsetWidth 和 offsetHeight

- 获取元素 `内容宽高 + padding宽高 + border宽高` 的和