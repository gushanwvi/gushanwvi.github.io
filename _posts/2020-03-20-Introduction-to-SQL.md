---
layout:     post
title:      Introduction to SQL
subtitle:   Class Notes of Database
date:       2020-03-20
author:     Eric
header-img: bg-202003142141.jpg
catalog: true
tags:
    - Class Notes
    - Database
---





* **numeric(p,d)** : The number consists of *p* digits(plus a sign), and *d* of the *p* digits are to the right of the decimal point.
* Since SQL does not provide a `for all X, P(X)` construct (where P is a predicate), we are forced to implement the constraint by an equivalent construct, `not exists X such that not P(X)`, that can be expressed in SQL.



### Command

#### create table

* ![](http://q7266277k.bkt.clouddn.com/20200317223008.png)



#### not null

* ![](http://q7266277k.bkt.clouddn.com/20200317223923.png)



#### insert

* ![](http://q7266277k.bkt.clouddn.com/20200317224051.png)

* The order of attributes can be specified.

  ![](http://q7266277k.bkt.clouddn.com/20200320155838.png)

* Insert tuples on the basis of the result of a query:
  ![](http://q7266277k.bkt.clouddn.com/20200320155932.png)



#### Update

* ![](http://q7266277k.bkt.clouddn.com/20200320165820.png)

* > Consider an update where we set the tot_cred attribute of each student tuple to the sum of the credits of courses successfully completed by the student. We assume that a course is successfully completed if the student has a grade that is not ’F’ or null.

  ![](http://q7266277k.bkt.clouddn.com/20200320171911.png)





#### Case

* ![](http://q7266277k.bkt.clouddn.com/20200320170703.png)

#### delete 

* delete all tuples from a relation

  ![](http://q7266277k.bkt.clouddn.com/20200317224204.png)
  
* *P* represents a predicate and *r* represents a relation. Find all tuples in $r$ for which $P(t)$ is true, and then deletes them from $r$.

  * ![](http://q7266277k.bkt.clouddn.com/20200320154732.png)

  * ![](http://q7266277k.bkt.clouddn.com/20200320154954.png)
  * ![](http://q7266277k.bkt.clouddn.com/20200320155100.png)

#### drop table

* delete a relation from a database

  ![](http://q7266277k.bkt.clouddn.com/image-20200317224354511.png)



#### alter table

* new attributes initialized as null value
  ![](http://q7266277k.bkt.clouddn.com/20200318125406.png)
  ![](http://q7266277k.bkt.clouddn.com/20200317230541.png)



#### select

* allow duplicates
  ![](http://q7266277k.bkt.clouddn.com/20200317230934.png)

* eliminate duplicates
  ![](http://q7266277k.bkt.clouddn.com/image-20200317230953472.png)

* arithmetic expressions
  ![](http://q7266277k.bkt.clouddn.com/20200317231339.png)

* where clause
  ![](http://q7266277k.bkt.clouddn.com/20200317231652.png)

* multiple relations
  ![](http://q7266277k.bkt.clouddn.com/20200318124437.png)



#### from

* The **from** clause by itself defines a Cartesian product of the relations listed in the clause.(including duplicates of attributes that appear in the schemas of both relations)
* an iterative process
  ![](http://q7266277k.bkt.clouddn.com/20200318130232.png)



#### natural join

* ![](http://q7266277k.bkt.clouddn.com/20200318135609.png)

* The result of the natural join operation is a relation. The **where** and **select** clauses are then evaluated on this relation.
* Natural join considers only those pairs of tuples with the same value on those attributes that appear in the schemas of both relations.



#### join...using

* ![](http://q7266277k.bkt.clouddn.com/20200318141023.png)

#### as

* ![](http://q7266277k.bkt.clouddn.com/20200318141728.png)
* ![](http://q7266277k.bkt.clouddn.com/20200318141909.png)

>“Find the names of all instructors whose salary is greater than at least one instructor in the Biology department.”

* ![](http://q7266277k.bkt.clouddn.com/20200318142640.png)

* ![](http://q7266277k.bkt.clouddn.com/20200319135913.png)

#### order by

> List in descending order of *salary*. If several instructors have the same salary, order them in ascending order by name.

![](http://q7266277k.bkt.clouddn.com/20200318171328.png)

#### between

![](http://q7266277k.bkt.clouddn.com/20200318171719.png) equals to  ![](http://q7266277k.bkt.clouddn.com/20200318171842.png)

also `not between`





### Integrity Constraints

* **primary key**($A_{j_1},A_{j_2},\dots,A_{j_m}$)

* **foreign key**($A_{k_1},A_{k_2},\dots,A_{k_n}$) **references** relation *s* 
* **not null**



### Additional Basic Operations

* SQL specifies strings by enclosing them in single quotes, e.g. `'Computer'`.

* A single quote character can be specified by using two single quote characters, e.g. `It's right` -> `It''s right`

* The SQL standard specifies that equality operation on strings is ***case sensitive***. But some databases are not.

* `trim(s)` removes spaces at the end of the string.

* **Pattern matching** : `%` (matches any substring) and `_` (matches any character)

  e.g.  `___%` matches any string of at least three characters.

* SQL expresses patterns by using `like` comparison operator.
  ![](http://q7266277k.bkt.clouddn.com/20200318170001.png)

* **escape** 

  * `like 'ab\%cd%' escape '\'` matches all strings beginning with `ab%cd` .
  * `like 'ab\\cd%' escape '\'` matches all strings beginning with `ab\cd` .
  * Search for mismatches by using the `not like` comparison operator.

* The asterisk symbol `*` denote *all attributes* .
  ![](http://q7266277k.bkt.clouddn.com/20200318170821.png)

* $(v_1,v_2,\dots,v_n)$ is a tuple of arity n.
  * $(a_1,a_2)\le(b_1,b_2)$ is true if $a_1\le b_1$ **and** $a_2\le b_2$ 
  * $(a_1,a_2)=(b_1,b_2)$ is true if $a_1= b_1$ **and** $a_2= b_2$ 
* **Set operations** 
  * `union`  $\cup$  (to retain all duplicates `union all`, the number of duplicate tuples in the result is equal to the total number of duplicates that appear in both c1 and c2. )
  * `intersect` $\cap$ (to retain all duplicates `intersect all`, the number of duplicate tuples in the result is equal to the minimum number of duplicates in both c1 and c2.)
  * `except\minus` $-$ (to retain all duplicates `except all`, the number of duplicate tuples in the result is equal to the number of duplicate copies in c1 minus the number of duplicate copies in c2, provided that the difference is positive. If the difference is negative, the number is 0.)
  * ![](http://q7266277k.bkt.clouddn.com/image-20200318173715082.png)



### Null Values

* The result of an arithmetic expression is null if any of the input values is null.

* SQL treats as **unknown** the result of any comparison involving a *null* value.

  * **Unknown** creates a third logical value in addition to *true* and *false*.

  * |           | and *unknown* | or *unknown* |    not    |
    | :-------: | :-----------: | :----------: | :-------: |
    |  *true*   |   *unknown*   |    *true*    |           |
    |  *false*  |    *false*    |  *unknown*   |           |
    | *unknown* |   *unknown*   |   *unknow*   | *unknown* |

* If the **where** clause predicate evaluates to either **false** or **unknown** for a tuple, that tuple is not added to the result.

* `where salary is null`  `is not null`  `is unknown`  `is not unknown`

* `('A', null)`  and  `('A', null)` are treated as being identical in **select**, **union**, **intersection**, **except**, even if some of the attributes have a null value. However, a comparison `null = null` in predicates would return **unknown**.



### Aggregate Functions

* *Aggregate functions* take a collection of values as input and return a single value.

* |                  |                  |
  | :--------------: | :--------------: |
  | Average: **avg** |  Total: **sum**  |
  | Minimum: **min** | Count: **count** |
  | Maximum: **max** |                  |
  
  (The input to **sum** and **avg** must be a collection of numbers)

* ![](http://q7266277k.bkt.clouddn.com/20200319111603.png)

* Because of the keyword **distinct** preceding ID, even if an instructor teaches more than one course, she is counted only once in the result.

  ![](http://q7266277k.bkt.clouddn.com/20200319112109.png)

* To find the number of tuples in a relation

  ![](http://q7266277k.bkt.clouddn.com/20200319112213.png)

* SQL does not allow the use of **distinct** with **count(*)**. It is legal to use **distinct** with **max** and **min**, even though the result does not change.

* `group by` : Any attribute that is not present in the **group by** clause must appear only inside an aggregate function if it appears in the **select** clause.

  ![](http://q7266277k.bkt.clouddn.com/20200319112841.png)

* > Find the number of instructors in each department who teach a course in the Spring 2010 semester

  ![](http://q7266277k.bkt.clouddn.com/20200319113229.png)

* **having** clause

  * ![](http://q7266277k.bkt.clouddn.com/20200319124203.png)

  * ![](http://q7266277k.bkt.clouddn.com/20200320101931.png)

* > For each course section offered in 2009, find the average total credits (tot cred) of all students enrolled in the section, if the section had at least 2 students.

  ![](http://q7266277k.bkt.clouddn.com/20200319125225.png)

* All aggregate functions except **count(*)** ignore null values in their input collection. The **count** of an empty collection is defined to be 0, and all other aggregate operations return a value of null when applied on an empty collection,



### Nested Subqueries

* `in`  `not in`

  > Find all the courses taught in the both the Fall 2009 and Spring 2010 semesters.

  * ![](http://q7266277k.bkt.clouddn.com/20200319131302.png)
  * ![](http://q7266277k.bkt.clouddn.com/20200320083920.png)

  > Find the total number of (distinct) students who have taken course sections taught by the instructor with ID 110011.

  ![](http://q7266277k.bkt.clouddn.com/20200319135558.png)

* `some/any` ('any' has linguistic ambiguity in English)

  * `< some, <= some, >= some, = some, <> some`

  * `= some` equals to `in`
  * `<> some` is ***not*** the same as **not in**.

* `all`

  * `< all, <= all, >= all, = all, <> all`
  * `<> all` equals to **not in**.
  * `= all` is ***not*** the same as **in**.

  > Find the departments that have the highest average salary.

  ![](http://q7266277k.bkt.clouddn.com/20200319141939.png)

* Test for empty relation: `exists`  `not exists` `except`  (return true or false)

  * > Find all studentswho have taken all courses offered in the Biology department.

  * ![](http://q7266277k.bkt.clouddn.com/20200320091615.png)

* Test for the absence of duplicate tupes:  

  * `unique(subquery)`

  * returns **true** if subquery has no duplicates
  * the **unique** predicate would evaluate to true on the empty set.
  * **unique** test on a relation fails *if and only if* the relation contains two identical tuples.
  * **unique** test may turn out to be true even if there are multiple copies of a tuple, as long as at least one of the attributes of the tuple if **null**. (since `null = null` returns **unknown**)
  * `not unique` 

* `with`

  * **With** defines a temporary relation whose definition is available only to the query in which the **with** clause occurs.

  * > Find all departments where the total salary is greater than the average of the total salary at all departments.

  * ![](http://q7266277k.bkt.clouddn.com/20200320141819.png)

* The usage of correlation variables, that is, attributes of relations in the from clause of the outer query.

  ![](http://q7266277k.bkt.clouddn.com/20200320153110.png)

















