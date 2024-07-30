---
title: JS 迴圈與效能
date: 2023-11-21T00:00:00.000
tags: ["JavaScript"]
categories: ["Note"]
draft: false
---

### JS 常見的 for 迴圈

以下由執行速度的快到慢排序

- for-loop-cached

```JS {hl_lines=[1]}
const listSize = yourList.length; // 精華
for (let index = 0; index < listSize; index++) {
  // ...
}
```

- for-loop

```JS
for (let index = 0; index < yourList.length; index++) {
  // ...
}
```

- forEach

```JS
yourList.forEach((element) => {
  // ...
});
```

- for-of

```JS
for (const element of yourList) {
  // ...
}
```

### 參考資料

[https://dev.to/siddiqus/which-for-loop-is-the-fastest-in-javascript-4hdf](https://dev.to/siddiqus/which-for-loop-is-the-fastest-in-javascript-4hdf)
