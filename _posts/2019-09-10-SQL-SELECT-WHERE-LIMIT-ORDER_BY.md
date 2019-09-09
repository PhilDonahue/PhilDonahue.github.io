---
layout:     post
title:      "SQL注入必知必会"
subtitle:   "SQL-SELECT-WHERE-LIMIT-ORDER_BY"
date:       2019-09-07 00:30:00
author:     "LR"
header-img: "img/sql_background.jpg"
tags:
    - SQL
---

#### SQL-SELECT-WHERE-LIMIT-ORDER_BY ####
###### SELECT ######
```
SELECT DISTINCT vend_id
FROM Products;
```
- **分析**：SELECT DISTINCT vend_id告诉DBMS只返回不同（具有唯一性）的vend_id行，DIATINCT必须放到列命前面
> **警告：不能部分使用DISINTCT**
> DISINTCT关键字作用于所有列，不仅仅是跟在其后的那一列。例如，你指定SELECT DISINTCT vend_id,prod_id,除非指定的两列完全相同，否则所有行都会被检索出来
