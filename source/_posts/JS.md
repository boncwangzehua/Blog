title: js常用方法整理
categories:
  - 默认分类
tags: []
date: 2017-08-11 18:56:00
---
1、数组常用方法

splice方法

```
let arr = [1,2,3];
arr.splice(1,1);
console.log(arr);  //[1,3]

```
splice的参数有两个，第一个是从哪个下标开始删除，第二个是要删除的元素个数。

2、数组去重（es6）
```
let arr = [1,2,1,3,3,2,2];
arr = Array.from(new Set(arr));
console.log(arr) //[1,2,3]
```

```
let arr = [1,2,1,3,3,2,2];
arr = [...new Set(arr)];
console.log(arr) // [1,2,3]
```