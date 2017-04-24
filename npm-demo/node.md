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
