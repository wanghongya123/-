# node.js

 [node.js](www.npmjs.com)
包管理工具

 **********

## 终端

 node        进入node编辑

 node a.js     就能运行a.js

 npm init   初始化node

 npm install jquery --save ---------//安装jquery

 npm uminstall [包名例jquery] -g---------卸载

 ****
 ## npm用法

npm init   初始化node----------生成一个package.json(数据传递，数据信息，属性名值加双引号，数组中不能加逗号)

 *****

 AMD / CMD 封装
*****
# node.js模块开发

 ## 模块分类三类

### 1.核心模块

 ```js

 ```
 ### 2.第三方模块（插件）
 1.npm install jquery --save ---------//安装jquery方法一--记录到dependencies字段下在 （哪运行就安装到那）

 安装到node_moduless node_moduless 不需要传入

 2.npm install jquery@3.0.0 --save-dev---------//安装jquery方法二--记录到devDependencies字段下 （在哪运行就安装到那）

 3.npm i -g jquery//--global:缩写为-g install 的缩写i；全局安装按到系统中方法三

 ####  卸载模块

 npm uminstall [包名] -g


```js
var $ = require('jquery')//jquery引用方法
```

 ### 3.文件模块（自己写的js）
 ```js
 #### a.js

 var name = "www";
 module.exports = name;//把name导出js 可以在其他js应用

 var aa = require("./index.js");//函数部分/先找.ｊs再找文件夹下的index.js
 console.log(aa);
 aa.sayname("cc")
 aa.sayname1("111")
 ```
```js
####index.js

var ccc = require(./a.js)//路径必须加相对路径不加就会被当成包
console.log(ccc)//输出www

function sayname(name){//函数部分
  console.log(name)
}
function sayname1(name1){
  console.log(name1)
}
module.exports = {
  sayname:sayname,
  sayname1:sayname1,
}

```
******************
## 脚本ｓｃｒｉｐｔ

package.json　中加

"ttt":"代码（例　node -v）" －－－－－－－　加到package.json中

在终端运行
```js
npm run ttt　

```
就相当于运行　node -v

****************************************
# let 与 var

var 有变量提升
ｌｅｔ　只能在域中｛｝同一域不能声明相同变量（重复声明）；

```js
{
  let a = 5;
  console.log(a)//a = 5
}
let a = 6;
console.log(a)//a=6

```

# const

用const 声明的常量只能读不能改
```js
const a = 5;
a=9;//错误
```
如果ｃｏｎｓｔ为对象时能改对象里的值,不能给ａ赋值。
```js
const  a = {
  name:"why"
}
a.name= "wh";
console.log(a.name)//wh
a = 6;
console.log(a)//能输出６但浏览器中会报错

```
# 数组赋值
```js
let [a,b,c]= [1,2,3];
console.log(a,b,c)
```
数组中有空格空格也会占一为空格不能输出
```js
let [a,,b,c]=[1,2,3,4]
console.log(a,b,c)//1,3,4
```
不止能输出数还有函数
```js
let [q,w,r] = [4,{name:"aaa"},function(){}]
console.log(q,w,r)//4 Object {name: "aaa"} function r() {}

```
声明变量赋值　　变量foo,boo,coo  按属性名赋值
```js
let obj = {foo:333,boo:666}
let {foo,boo,coo}=obj;
console.log(foo,boo,coo)//333,666,undefind
```
字符串赋值
```js
const[a,b,c,d,e]="why258"
console.log(a)//w
console.log(b)//h
console.log(a,b,c)//why
```
声明对象的简单写法
```js
let name = "why";
let age ="18";
let say = function(){};
let run =function(){};
let obj ={name,age,say,run}
console.log(obj.name)
```
********************************************

# 箭头函数
```js
let a = (num) =>num*8;//(num)相当于function

// (num){num*8},=>num*8相当于函数内的

console.log(a(5))//40
```
多条js语句
```js
let b = (num,num2) =>{
  num = num++;
  console.log(num)
  num2++;
  return num + num2

}
console.log(b(5,5))
```
返回对象用小括号阔起来
```js
let c = (num,nm1) =>({name:"why"})
console.log(c())
```
setTimeout　函数
```js
setTimeout(()=>console.log(6),500)
```
### 字符串模板输出到ｂｏｄｙ
```js
let name ="why";
let age = "18";
let a =`<p>我的名字是${name}我的年龄是${age}`
document.body.innerHTML = a
//我的名字是ｗｈｙ我的年龄是１８

```
剩余参数放到...rest中
```js
function restFun(a,...rest){
  console.log(a)//1
  console.log(rest)//2,23,8,9
}
restFun(1,2,23,8,9)
```
## reduce有返回值

参数求和  
```js
[1,2,3,4,5].reduce(function(acc,cur){
  console.log(acc,cur);
  return acc + cur
})
///////方法二
function add(...x){
  return x.reduce((m,n)=>m+n)
}
console.log(add(1,2,3,4,5))
```
取最大值
```js
let c = [10,2,3,4,5].reduce(function (a,b){
  return a > b ? a : b
})
console.log(c);

//简写箭头函数
let a =[10,8,9,2,3]
let max = a.reduce((cur,acc)=>cur>acc?cur:acc)
console.log(max)
```
spread 扩展调用　（可用数组拼接）
```js
let arr = [1,2,3,4];
let arr1 = [...arr,5,6,7,8,9];
console.log(arr1)//[1,2,3,4,5,6,7,8,9]
```
# modules模块
## 导入导出
在ｔｅｓｔ中定义ｓｔｒ，ｏｂｊ
```js
let str ="why"
let obj = {age:"18"}
export{str,obj}
export default obj //默认导出
```
在index.js中导出test中的str obj
```js
import {str,obj} from"./text";//可以写成import {str as ccc} from "./test"   console.log(ccc)//why
console.log(str)//why
console.log(obj)//Object {age: "15"}
console.log(obj.age)//15
import aaaaa from "./test"
console.log(aaa.age)
```
## map 用法
```js
let num = [1,2,3,4,5];
let text = num.map(function(a,b,c){
  return `<p>${a}</p>`
})
console.log(text)//<p>1</p><p>2</p><p>3</p>
```
## filter过滤
```js
let filtered = [1,2,5,20,8,99,63,1,0].filter(function(value,index,array){
  return value >10
})
console.log(filtered)
//let cc = filtered.filter((a)=> a > 10)
//sconsole.log(ccs)
```
## forEach加强版的ｆｏｒ循环
```js
let arr =[6,8,9,4]
arr.forEach(function(a){
  console.log(a)
})
//arr.forEach((a)=>console.log(a))//箭头函数
```
## findIndex
```js
let arr = [
  {name:"w",age:15,id:23},
  {name:"wh",age:151,id:123},
  {name:"why",age:152,id:234}
]
let ttt = arr.findIndex(item=>item.age ===151)
console.log(ttt)
```
箭头函数的ｔｈｉｓ指向
```js
function foo(){
  console.log(this);//12
  setTimeout(()=>{
    console.log(this);//12
    console.log("id:",this.id),100//id:12
  })
}
var id = 25;
foo.call({id:12})

```
## 继承
class [name]()//定义类
class [name1] extends [name]{}//继承类
class [name1] extends [name]{
  constructor(){
    super()
  }
}
class只能写一个个方法，方法与方法之间什么都不加
class 首字母大写
```js
_render(){
    throw new Error("子集错误")
  }
  render(){
    return(`<ul>
      ${this._render()}
    <ul>`)

  }
}
class Son extends Father{
  _render(){
    return (`<li>哈哈哈</li>`)
  }
}
var son = new Son()
console.log(son.render());
document.body.innerHTML=son.render()

```
*****************************************************
******************************************************
*****************************************************
# React
react-Dom .render方法 把hello渲染到浏览器中的root中
react-Dom .render（hello,document.getElementById("root")）
## jsx语法
jsx 语法需要ｂａｂｅｌ进行编译　　转化这个方法　React.createElememt();

  特点一：相邻的jsx元素必须在一个闭合的标签内；
  特点二：每一个标签必须闭合
  特点三：没有闭合的标签携程＝写成在关闭
  class = className;for=htmlFor
  区分大小写

```js

//例
import React from "react";
import ReactDom from "react-dom";
let age = 18;
let h = "HELLO";
function　sum(x,y){
  return x+y
}
let hello =<div>
  <p>hello word</p>;
  <lable htmlfor="name">姓名</lable>
  <input value="sss" id="name" />
  <h1>dff {h.toLowerCase()} dvvd </h1>
  <p className="afs">{sum(5,9)}   {age}</p>
  <p>{Date.note}</p>

</div>
ReactDom.render(hello,document.querySelector("#root"))
```

## React 组件有三种－－－当自定义标签用首字母必须大写
  第一种组件React.createClass(
  ```js

  let Hello = React.createClass({
    render:function(){
      return(
        <div>
          <h1>第一种组件的创建方式</h1>
        </div>
      )
    }
  })
  ReactDom.render(<Hello></Hello>,document.querySelector("#root"))
  ```
  第二种
```js
  function Hello(){
    return (
      <h1>我是第二种组件创建方式有返回值，必须是jsx elements</h1>
      )
  }
ReactDom.render(<Hello></Hello>,document.querySelector("#root"))
```
第三种
```js
class My extends React.Component{
  render(){
    return(
      <div>
        <h3>我是第三种组件创建方式</h3>
      </div>
    )
  }
}
ReactDom.render(<My/>,document.querySelector("#root"))
```
