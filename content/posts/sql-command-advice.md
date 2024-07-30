---
title: SQL 優化建議
date: 2023-11-23T00:00:00.000
tags: ["SQL"]
categories: ["Note"]
draft: true
---

### 1. 盡量不用 select \*

```SQL
select id, name from employee;
```

### 2. 只查一筆資料時用 limit 1

```SQL
select id, name from employee where name='jay' limit 1;
```

### 3. 避免在 where 使用 or 連接條件

```SQL
-- 使用 union all
select * from user where userid = 1 union all select * from user where age = 18
```

### 4. 優化 limit 分頁

```SQL
order by + 索引 select id, name from employee order by id limit 10000, 10
```

### 5. 優化 like 語法

```SQL
select userId, name from user where userId like '123%';
```

### 6. 用 where 限制只取需要的資料

```SQL
Long userId = sqlMap.queryObject("select userId from user where userId = 'userId' and isVip='1'")boolean isVip = userId != null;
```

### 7. 避免在 where 使用表達式操作

```SQL
select * from user where age = 11;
```

### 8. 優先使用 inner join

如果是 left join, 盡量小表 join 大表

```SQL
select * from (select * from tab1 where id >2) t1 left join tab2 t2 on t1.size = t2.size;
```

### 9. 盡量避免在 where 中使用 != 或 <> 操作

```SQL
-- 可以考慮分開寫
select age,name from user where age < 18;
select age,name from user where age > 18;
```

### 10. 聯合索引時，最左匹配原則

若表的欄位順序為 userid, age

```SQL
-- 符合最左匹配原則
select * from user where userid = 10 and age = 10;
-- 符合最左匹配原則
select * from user where userid = 10;
```

### 11. 對查詢進行優化

應考慮在 where 及 order by 會使用到的列上建立索引，盡量避免全表掃描

```SQL
alter table user add index idx_address_age (address, age)
```

### 12. insert 大量資料應批次新增

```SQL
insert into user(name, age) values
  <foreach collection = "list" item = "item" index = "index" separator = ",">
    (#{item.name}, #{item.age})
  </foreach>
```

### 13.

### 14.

### 15.

### 16.

### 17.

### 18.

### 19.

### 20.

### 21.

### 22.

### 23.

### 24.

### 25.

### 26.

### 27.

### 28.

### 29.

### 30.

### 參考資料

[https://ithelp.ithome.com.tw/articles/10213001](https://ithelp.ithome.com.tw/articles/10213001)
[https://cloud.tencent.com/developer/article/1606322](https://cloud.tencent.com/developer/article/1606322)
