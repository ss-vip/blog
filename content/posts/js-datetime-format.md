---
title: JS 簡單的日期格式化
date: 2023-11-14T00:00:00.000
tags: ['JavaScript']
categories: ['Note']
draft: false
---

### 日期時間的處理

簡單的日期時間取得以及格式化

```JS
// 取當前日期時間(timestamp 時間戳)
const timestamp = Date.now();
console.log(timestamp); // 1713251128711

// 取當前日期時間(ISO 8601 的格式)
const nowDateTimeISO = new Date().toISOString().split(".")[0] + "Z";
console.log(nowDateTimeISO); // 2024-04-16T07:17:31Z

// 取當前日期時間(補零)
const nowDateTime = new Date(Date.now()).toLocaleString("sv");
console.log(nowDateTime); // 2024-04-16 13:51:58

// 取當前日期時間(補零，指定時區)
const nowDateTimeNY = new Date(Date.now()).toLocaleString("sv", {
  timeZone: "America/New_York"
});
console.log(nowDateTimeNY); // 2024-04-16 03:05:02

// 取當前日期(補零)
const nowDate = new Date(Date.now()).toLocaleString("sv").split(" ")[0];
console.log(nowDate); // 2024-04-16

// 取當前時間(補零)
const nowTime = new Date(Date.now()).toLocaleString("sv").split(" ")[1];
console.log(nowTime); // 13:55:08
```

### 數字與金額的處理

也是常用到的格式

```JS
// 數字補零(補滿6位數)
const sixNum = String(1234).padStart(6, "0");
console.log(sixNum); // 001234

// 金額千分位
const money = Intl.NumberFormat().format(1234567890);
console.log(money); // 1,234,567,890
```
