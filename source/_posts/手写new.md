---
title: 手写new
date: 2022-01-08 11:41:30
categories: 面试题
tags: JavaScript
cover: './img/background.webp'
---

先用文字描述一下 new 的实现过程

- 新定义一个 json 对象
- 对象 继承 构造函数的原型链
- 将构造函数的 this 指向这个对象
- 根据构造函数的返回值类型返回结果

```javascript
function myNew(fn,...args) {

    let obj = {} //创建一个新的对象
    obj.__proto__ = fn.prototype //对象继承构造函数的原型链
    fn.apply(obj,args) //将构造函数的this指向这个对象
    return obj;

}
 function Person() {
    
    this.name = arguments[0]
    this.age = arguments[1]
    this.gender = arguments[2]

 } 
 Person.prototype.sayHello = function() {

    console.log("你好呀,我是",this.name);
 }

//数据测试
 let test = myNew(Person,'张三','18','男')
 test.sayHello()
 console.log(test.name);
 console.log(test.age);

```

