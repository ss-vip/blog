---
title: JS 找出陣列中不重複的值
date: 2023-11-14T00:00:00.000
tags: ['JavaScript']
categories: ['Note']
draft: false
---

### 用位元運算子 XOR (^) 特性

```JS
function uniqueNumber(nums) {
  return nums.reduce((a, b) => a ^ b, 0)
}

console.log(uniqueNumber([1, 2, 3, 1, 2])) // 3
```

### 去除重複的值

```JS
const origin = [1, 2, 'a', 3, 1, 'b', 'a']
const result = [...(new Set(origin))]
console.log(result) // [1, 2, 'a', 3, 'b']
```

### 參考資料

- [https://pjchender.dev/javascript/js-operator/](https://pjchender.dev/javascript/js-operator/)
- [https://guahsu.io/2017/06/JavaScript-Duplicates-Array/](https://guahsu.io/2017/06/JavaScript-Duplicates-Array/)
