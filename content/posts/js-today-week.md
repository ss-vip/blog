---
title: JS 今天星期幾
date: 2023-11-15T00:00:00.000
tags: ['JavaScript']
categories: ['Note']
draft: false
---

### 顯示今天是星期幾的兩種寫法

使用 switch

```JS
const dayNumber = new Date().getDay()
let day = '星期日'
switch(dayNumber){
  case 1:
    day = '星期一'
    break
  case 2:
    day = '星期二'
    break
  case 3:
    day = '星期三'
    break
  case 4:
    day = '星期四'
    break
  case 5:
    day = '星期五'
    break
  case 6:
    day = '星期六'
    break
}
console.log('今天' + day)
```

使用 object

```JS
const dayNumber = new Date().getDay()
const days = {
  0: '星期日',
  1: '星期一',
  2: '星期二',
  3: '星期三',
  4: '星期四',
  5: '星期五',
  6: '星期六'
}
const day = days[dayNumber]
console.log('今天' + day)
```
