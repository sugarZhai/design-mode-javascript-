# 设计模式整理

1、数据耦合的解释如下：
数据耦合指两个模块之间有调用关系,传递的是简单的数据值,相当于高级语言的值传递”。
这是网上找的数据耦合的定义，我想问问这个定义中的两个模块指的是什么啊？
如果我想做一个创建和插入节点的功能，写一个创建节点的函数，再写一个插入节点的函数，这两个函数能算两个模块
function create(id){
   var box=document.createElement("div")
   box.setAttribute("id",id)
   return box
}
function append(id){ 
   var box=create(id)
   document.body.appendchild(obj)
}
这个能说append函数中append和create数据耦合了吗？     
a访问b  那么 a和b 是耦合的


你那个就是 耦合的 因为 append中访问了 create

怎么解耦？

function create(id){
   var box=document.createElement("div")
   box.setAttribute("id",id)
   return box
}
function append(obj){ 
   document.body.appendchild(obj)
}

//调用
var box=create(id)
append(box);

那么现在 append 和 create 解耦了 互相不知道对方的存在
因为 调用代码（也叫 业务逻辑） 组织了他们的关系




2、Iterator我们至少要有2个方法，hasNext()和Next()，这样才做做到遍历所有对象,为什么？
 关于Iterator主要有三个方法：hasNext()、next()、remove()

  hasNext:没有指针下移操作，只是判断是否存在下一个元素

  next：指针下移，返回该指针所指向的元素

 remove：删除当前指针所指向的元素，一般和next方法一起用，这时候的作用就是删除next方法返回的元素

迭代器的原理：
1、当创建完成指向某个集合或者容器的Iterator对象是，这是的指针其实指向的是第一个元素的上方，即指向一个空

 2、当调用hasNext方法的时候，只是判断下一个元素的有无，并不移动指针

 3、当调用next方法的时候，向下移动指针，并且返回指针指向的元素，如果指针指向的内存中没有元素，会报异常。

 4、remove方法删除的元素是指针指向的元素。如果当前指针指向的内存中没有元素，那么会抛出异常。
![输入图片说明](https://gitee.com/uploads/images/2017/1213/152823_9e08e3de_1642965.png "屏幕截图.png")
http://blog.csdn.net/zhujiangtaotaise/article/details/50515939






3、参考链接为http://www.cnblogs.com/TomXu/archive/2012/04/16/2436460.html