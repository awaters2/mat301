## Problem Set 3 

1. Define the terms: relation, tuple, attribute, record, and field.
Relation: relates to a table where the instead of columns and rows it is a set of lists related to one another (a given amount of tuples).
Tuple: an ordered list of elements
Attribute: a data type that specifies a particular type of data of any object
Record: relates to a row in a table, holds different data items that consists in different fields
Field: relates to a column but is not limited to that definition because it can be use in reference to the intersection of a row and a column.

2. What are keys in a relation?
In relational databases, keys are links to different relations, especially the foreign key which is the link from from one non-primary key of one relation to the primary key of another relation.

3. What is a surrogate key and how is it used?
A surrogate key is any key that can be a potential (and most often the best choice for) primary key. It can also be used as a candidate key and it is used by

4. In the following equation, Area = Length x Width, identify the determinant(s).
The determinants are Length and Width.

5. If a relation has no duplicate data, how can you be sure there is always at least one primary key?

6. Give an example of a relation.  Determine a natural key for this relation.

  For question 7 - 8, Consider product *orders*.  In particular, associated with an order is: customer name (first and last), address (street, city, state, zip), phone, email, the products orders (including item, quantity, and price).  

7. Create a relational data model for *orders*.  Consider applying normalization rules (discuss Monday)

8. For customer, could email be used as a primary key?  If so, state why.  Also, if possible to use as a primary key, discuss any disadvantages of using email as a primary key.

9. Given two relations S and R below find the Cartsian Product S x R. 
SELECT A, B, C, D, E FROM S, R;

10. Find the natural join between the Faculty and Department relations below.
SELECT * FROM  Faculty NATURAL JOIN Department;

S
--------------
| A | B |
|---|---|
| 1 | 2 |
| 2 | 3 |
---------

R
------------
| C | D | E |
|---|---|---|
| 3 | 1 | 1 |
| 2 | 2 | 3 |
| 2 | 1 | 5 |



Faculty
--------------
| Name | ID | Dept |
|-------|----|----------------|
| Joe | 1 | Chemistry |
| Susan | 2 | Math |
| Tom | 3 | Marine Science |
| Mike | 4 | Math |


Department
------------
| Dept | Chair  |
|---|---|
| Chemistry | John |
| Math | Mike |
| Marine Science | Barry |
