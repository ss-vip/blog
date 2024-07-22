---
title: JS ~~ 取整數
date: 2023-11-15T00:00:00.000
tags: ['JavaScript']
categories: ['Note']
draft: false
---

### 用 ~~ 取得整數值

無條件捨去，取得整數值，效能優於 parseInt

```JS
console.log(~~ -2.34); // -2
```

### 用 ~ 判斷陣列的值是否存在

```JS
const arr = [1, 2, 3];
if (~arr.indexOf(3)) {
  console.log("find!"); // find!
}
```

### 參考資料
- <https://segmentfault.com/a/1190000003731938>
- <https://shunnien.github.io/2017/06/26/JavaScript-Double-bitwise-not/>
