## Problem Set 3 

1. Define the terms: relation, tuple, attribute, record, and field.
Relation: relates to a table where the instead of columns and rows it is a set of lists related to one another (a given amount of tuples).
Tuple: an ordered list of elements
Attribute: a data type that specifies a particular type of data of any object
Record: relates to a row in a table, holds different data items that consists in different fields
Field: relates to a column but is not limited to that definition because it can be use in reference to the intersection of a row and a column.


    __Correct__



2. What are keys in a relation?
In relational databases, keys are links to different relations, especially the foreign key which is the link from from one non-primary key of one relation to the primary key of another relation.



    __Correct__



3. What is a surrogate key and how is it used?
A surrogate key is any key that can be a potential (and most often the best choice for) primary key. It can also be used as a candidate key and it is used to identify items with independent attributes.


    __Correct__



4. In the following equation, Area = Length x Width, identify the determinant(s).
The determinants are Length and Width.



    __Correct__



5. If a relation has no duplicate data, how can you be sure there is always at least one primary key?
If a relation has no duplicate you can determine it has at least one primary key because the attributes in a relation represents a unique row.


    __Correct__



6. Give an example of a relation.  Determine a natural key for this relation.
A relation could be online shopping at amazon, where the different fields are item name, item id, vendor, cost, customer id, customer address, customer email. The customer email would be the natural key. 

    __Correct__



  For question 7 - 8, Consider product *orders*.  In particular, associated with an order is: customer name (first and last), address (street, city, state, zip), phone, email, the products orders (including item, quantity, and price).  

7. Create a relational data model for *orders*.  Consider applying normalization rules (discuss Monday)
NF1: cus_first, cus_last, add_street, add_city, add_state, add_zip, cus_phone, cus_email, item_name, item_id, item_quantity, item_price
NF2: The primary keys are the first elements that appear in each table.

    __X.  Issues__


Customer Info
------------
| cus_id |
|--------|
| cus_first |
| cus_last |
| add_street |
| add_city |
| add_state |
| add_zip |
| cus_phone |
| cus_email |

Item
------
| item_id |
|--------|
| item_name |
| item_quantity |
| item_price |
--------------
NF3: The primary keys are the first elements to appear in each table with the exception of the table Customer which represents the foreign keys that connect to one of the three other relations.

Cutomer
-------------
| cus_id |
|--------|
| item_id |
| add_zip |

Customer Info
------------
| cus_id |
|--------|
| cus_first |
| cus_last |
| cus_phone |
| cus_email |

Item
-----
| item_id |
|--------|
| item_name |
| item_quantity |
| item_price |

Address
----------
| add_zip |
|---------|
| add_street |
| add_city |
| add_state |

8. For customer, could email be used as a primary key?  If so, state why.  Also, if possible to use as a primary key, discuss any disadvantages of using email as a primary key.
The email would be a bad primary key (but it could be used as a primary key) because people don't always keep the same email which would mean that attribute could be useless as a unique identifier.

    __Correct__


9. Given two relations S and R below find the Cartsian Product S x R. 
The Cartsian Product is the product of two tables S and R and is a set of ordered pairs.
SELECT A, B, C, D, E FROM S, R;

    __X__


10. Find the natural join between the Faculty and Department relations below.
It will will combine the columns and rows of the two tables that are related. So name, dept, and job id would be combined to make its own relation.
SELECT * FROM  Faculty NATURAL JOIN Department;

    __Correct__




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
