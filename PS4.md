## Problem Set 4 

1. Create three tables: Customers, Orders, and OrderItems.

2. Why do we need an OrderItems table?
An OrderItems table is needed because it keeps overlap out from the data. The table represents an individual order item, which is not limited to one customer and also does not limit the customer to one item. This would mean that the customer is not determined by the item.

3. Create linked tables in MS Access.

4. Create forms to enter customer data.

5. Create a form with a subform to enter orders and order item.

6. Use forms created in 4 and 5 to insert Customers and Orders.  Add customers that have not made any orders. Make the number of entries relatively small.  Why?  

7. Use SQL DML to INSERT records into Customers and Orders (and OrderItems).

8. Find all customer orders.
SELECT * FROM unemath_Waters.Orders;

9. Select all customers that orders a certain product (This will depend on what data you entered into the table).  Find all customers that ordered product 3452.
SELECT * FROM unemath_Waters.OrderDetails WHERE product_id=1000;
SELECT * FROM unemath_Waters.OrderDetails WHERE product_id=3452;

10. List 5 questions that you can answer from this data.
(1) What is the most popular item bought through this company?
(2) What are people buying regionally (via zipcodes)?
(3) Seasonally, what is the most bought item (due to the dates given in the order details table)?
(4) How much does a single customer order?
(5) Is there a specific theme of categories for a specific customer?
