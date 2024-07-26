---
title: JS 常見的陣列操作
date: 2023-11-20T00:00:00.000
tags: ["JavaScript"]
categories: ["Note"]
draft: false
---
### JS 做一個 Todolist 吧

以 todolist 為例，做個有 [CRUD](https://zh.wikipedia.org/zh-tw/%E5%A2%9E%E5%88%AA%E6%9F%A5%E6%94%B9) 功能的待辦清單

```JS
// todolist 資料容器
let todoListData = []

// 編號用隨機亂數
function newId () {
  return ~ (Date.now() + (Math.random()*50))
}
```

- 新增一筆資料

```JS
let newTodoData = {
  "id": newId(),
  "title": "買早餐",
  "info": "要漢堡跟可樂"
}
todoListData.push(newTodoData)
```

- 刪除所有資料

```JS
todoListData.length = 0
```

- 刪除指定資料

```JS
// 要被刪除的 id
const id = 385746993

// 找 id 存在的 index 位置
const listIndex = todoListData.findIndex(element => element.id == id)

// 若 id 存在就刪除
if (listIndex > -1) {
  todoListData.splice(listIndex, 1)
}
```

- 查詢指定資料

```JS
// 要尋找的 id
const id = 385746993

// 找 id 的 index 位置
const listIndex = todoListData.findIndex(element => element.id == id)

// 顯示資料及找不到 id 的處理
if (listIndex < 0) {
  console.log("找不到:" + id)
} else {
  return todoListData[listIndex]
}
```

- 修改指定資料

```JS
// 要修改的 id 與內容
const id = 385746993
const newTitle = "買下午茶"
const newInfo = "檸檬蛋糕起司塔"

// 找 id 的 index 位置
const listIndex = todoListData.findIndex(element => element.id == id)

// 修改資料及找不到 id 的處理
if (listIndex < 0) {
  console.log("找不到:" + id)
} else {
  todoListData[listIndex].title = newTitle
  todoListData[listIndex].info = newInfo
}
```

### Codepen 範例

<iframe height="350" style="width: 100%;" scrolling="no" title="JS - Todolist" src="https://codepen.io/tw1720/embed/OJeRQMx?default-tab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/tw1720/pen/OJeRQMx">
  JS - Todolist</a> by Hank (<a href="https://codepen.io/tw1720">@tw1720</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>
