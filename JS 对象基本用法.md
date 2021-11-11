# js对象基本用法

## 声明对象的两种语法

对象是无序的数据集合、键值对的集合

```JavaScript
let obj1 = {'name':'lmy','age':24}

let obj2 = new Object({'name':'pxh','age':'24'})

//当然 我们一般使用第一种
/*
一些需要注意的地方
键名是字符串，不是标识符，可以包含任意字符
键名的引号可以省略，但省略之后类似于 2abc 这种键名会报错，但是单独用2做键名可以
即使省略了引号，键名也还是字符串
*/
```

## 删除对象的属性

```JavaScript
let obj = {'name':'lmy','age':24,'gf':'pxh','career':'farmer'}

delete obj.name
delete obj['name']

//或者可以这样
let name = 'name'
delete obj[name] //此时name是一个变量，先取值，其值为'name'，所以实际效果是delete ['name']
```

## 查看对象的属性

```JavaScript
let obj = {'name':'lmy','age':24,'gf':'pxh','career':'farmer'}

Object.keys() //查看所有键
Object.values() //查看所有值
Object.entries() //查看所有键值

obj.name
obj['name']

//不戴绿帽子
let age = 'name'
console.log(obj[age])
//选项1 输出24  选项2 输出lmy
//222222222222222222222222222222222222222222222
```

```JavaScript
let obj = {'name':'lmy','age':24,'gf':'pxh','career':'farmer'}
//判断对象是否含有某个属性名
'name' in obj //返回true
'name1' in obj //返回false

//判断一个属性是自身属性还是共有属性
obj.hasOwnProperty('name')  //true
obj.hasOwnProperty('toString') //false

//obj.xxx === undefined 不能判断'xxx'是否为obj的属性
```

## 修改或增加属性
```JavaScript
//直接赋值
let obj = {'name':'lmy'}
obj.name = 'pxh'
obj['name'] = 'pxh'
obj['nam'+'e'] = 'pxh'


//批量赋值
let obj = {'name':'pxh'}
Object.assign(obj,{'age':24,'gender':'man'})
```
```JavaScript
//有关共有属性
//无法通过自身修改或增加共有属性
let obj1 = {}
let obj2 = {}
obj1.toString = 'xxx' //只会修改obj1自身的属性，obj2的toString仍在原型上

//如果说非要修改或增加原型的属性
obj1.__proto__.toString = 'xxx'

Object.prototype.toString = 'xxx'

//但是一般不要修改原型的属性

//修改原型
let obj1 = {'name':'lmy'}
let obj2 = {'name':'pxh'}
let common = {'king':'human'}
obj1.__proto__ = common
obj2.__proto__ = common

//这时候 obj1 和 obj2 的原型变为了 common，但是common也是对象，所以common也有原型，common的原型是__proto__，原型链~


//但是以上这种使用__proto__的方法不推荐

//建议使用Object.create()
let common = {'kind':'human'}

let obj = Object.create(common)  //一开始就指定obj的原型为common
//之后再添加属性 
obj.name = 'lmy'
Object.assign(obj,{'age':24})
```

## 'name' in obj和obj.hasOwnProperty('name') 的区别

```JavaScript
//都是查看属性是不是在对象里的方法
//前者自身属性和共有属性都返回true，后者仅仅是自身属性才返回true
```
