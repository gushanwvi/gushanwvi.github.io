---
layout:     post
title:      Relational Model
subtitle:   Class Notes of Database
date:       2020-03-12
author:     Eric
header-img: bg-202003142141.jpg
catalog: true
tags:
    - Class Notes
    - Database
---





### 0x01

* `DML`(data-manipulation language) `DDL`(data-definition language)
* An `assertion` is any condition that the database must always satisfy. 
* This all-or-none requirement is called ***atomicity***.
* A ***transaction*** is a collection of operations that performs a single logical function in a database application.
* Each ***transaction*** is a unit of both ***atomicity*** and ***consistency***.



### 0x02

* relation schema is a vector  / a set of attributes
* relation is a two-dimensional table  / a set of n-tuples

![image-20200305101417041](http://q7266277k.bkt.clouddn.com/image-20200305101417041.jpg)

* Superkey K is a candidate key if K is minimal.(can't find a subset of K that is a superkey.)
* One of the candicate keys is selected to be the primary key.(as you wish, any one will be ok)



### 0x03 Relational Model

* **Relation** is used to refer to a **table**, while **tuple** refers to a **row**. And, **attribute** refers to a **column**.
* A domain is **atomic** if elements of the domain are considered to be indivisible units.
* **Database schema** is the logical design of the database. **Database instance** is a snapshot of the data in the database at a given instant in time.
* **Relation schema** is just like the notion of type definition, while **relation** is the variable and ***relation instance is the value of the variable***.
* A **superkey** is a **set** of one or more attributes that identify uniquely a tuple in a relation.
* **Candidate keys** are minimal superkeys. (superkeys for which no proper subset is a superkey)
* **One** of the candidate keys is selected to be the **primary key**.(as you wish, any one will be ok)
* The primary key should be chosen such that its attribute values are never, or very rarely, changed.
* **Foreign key** is one of the relation's attributes, referencing another relation. Simultaneously, **foreign key** is the other relation's **primary key**. The relation is called the **referencing relation** of the foreign key dependency, and the other relation is called the **referenced relation** of the foreign key.
* A **referential integrity constraint** requires that the values appearing in specified attributes of any tuple in the referencing relation also appear in specified attributes of at least one tuple in the referenced relation.
* Operation
  * join, natural join
  * union
  * Cartesian product
  * intersection
  * set difference
  * ![](http://q7266277k.bkt.clouddn.com/20200316220658.png)

