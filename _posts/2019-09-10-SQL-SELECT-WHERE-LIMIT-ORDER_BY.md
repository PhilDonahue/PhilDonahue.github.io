---
layout:     post
title:      "SQL注入必知必会"
subtitle:   "SQL-SELECT-WHERE-LIMIT-ORDER_BY"
date:       2019-09-07 00:30:00
author:     "LR"
header-img: "img/sql_background.jpeg"
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
> **警告：不能部分使用DISINTCT**<br>
> DISINTCT关键字作用于所有列，不仅仅是跟在其后的那一列。例如，你指定SELECT DISINTCT vend_id,prod_id,除非指定的两列完全相同，否则所有行都会被检索出来

###### ORDER BY ######
1. 按单列排序
ORDER BY子句取一个或多个列的名字，据此对输出进行排序
```
SELECT DISTINCT vend_id
FROM Products
ORDER BY prod_name;
```
- **分析**：输出结果相同，指示DBMS软件对prod_name列以字母顺序排序数据
> **ORDER BY子句位置**
> 保证它是SELECT语句中最后一条子句，否则会出现错误信息
<br>
> **'通常非选择列进行排序'**
> '通常，ORDER BY子句中使用的列将是为显示而选择的列。但是，实际上不一定要这样，用非检索的列排序数据是完全合法的。'
<br><br>
2. 按多个列排序
下面代码检索3个列，并按其中两个列对结果进行排序---首先按价格，然后按名称排序
```
SELECT DISTINCT vend_id,prod_price,prod_name
FROM Products
ORDER BY prod_price,prod_name;
```
仅对于多个行具有相同的prod_price值时才对产品按prod_name进行排序，如果prod_price中所有值都是唯一的，则不会按prod_name排序。
3. 按列位置排序（相对列位置排序）
```
SELECT DISTINCT vend_id,prod_price,prod_name
FROM Products
ORDER BY 2,3;
```
- **分析**：SELECT清单中指定的是选择列的相对位置而不是列名。ORDER BY 2表示按SELECT清单中的第二个列prod_name进行排序。ORDER BY 2,3表示先按prod_price,再按prod_name进行排序
'当修改SELECT清单时，忘掉相对修改位置，而造成数据错误'
> **按非选择列排序**
> 当根据不出现在SELECT清单中的列进行排序时，不能采用这项技术。但是，'如果有必要，可以混合匹配使用实际列名和相对列位置。'
