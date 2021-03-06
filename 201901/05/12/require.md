# require


### module 分析

```
Module {
  id: '.',
  exports: {},
  parent: null, // 父模块, 此模块是哪个模块来加载的
  filename: 'G:\\workspace\\20190423\\1.node\\module\\uschool.js',  // 当前模块的绝对路径
  loaded: false,
  children: // 此模块加载的模块
   [ Module {
       id: 'G:\\workspace\\20190423\\1.node\\module\\school.js',
       exports: [Object],
       parent: [Circular],
       filename: 'G:\\workspace\\20190423\\1.node\\module\\school.js',
       loaded: true,
       children: [],
       paths: [Array] } ],
  paths:
   [ 'G:\\workspace\\20190423\\1.node\\module\\node_modules',
     'G:\\workspace\\20190423\\1.node\\node_modules',
     'G:\\workspace\\20190423\\node_modules',
     'G:\\workspace\\node_modules',
     'G:\\node_modules' ] }
```

### 为什么 require 同步执行？

- 1. 因为模块实现了缓存
- 2. 当第一次加载这个模块时，会缓存这个模块的 exports 对象
- 3. 以后需要再次加载的这个模块的时候，会直接从缓存取，不需要再次加载了

### 缓存位置 require.cache

```
console.log(Object.keys(require.cache));
var school = require('./school');
console.log(Object.keys(require.cache));
var school = require('./school');
console.log(Object.keys(require.cache));
```

### 缓存的 key 是什么？
文件的绝对路径


### require 对象分析
```
/*
 * resolve // 得道一个模块的绝对路径的时候，但又不想真正加载它的时候，可以用resolve
 * main // 入口模块, 当前模块
 * extensions // 扩展,
 * cache
*/

// console.log(require('./school'))
// console.log(require.resolve('./school'))
// console.log(require.main)


// console.log(require.extensions)
/**
 * 在node里模块的类型有三种
 * 1. JS模块
 * require
 * 2. json模块
 * 先找文件，读取文件内容，JSON.parse转成对象返回
 * 3. node C++扩展二进制模块
 * 这属于二进制模块
 * 当 require 加载一个模块的时候，
 * 会先找 user
 * 如果找不到，会再找 user.js, 
 * 如果还找不到找 user.json, 
 * 如果还找不到， 最后找user.node
 */
```
