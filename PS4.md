## Problem Set 4 

1. Create three tables: Customers, Orders, and OrderItems.
CREATE TABLE `Orders` (
  `id` int(11) NOT NULL,
  `customer_id` int(11) NOT NULL,
  `order_date` date NOT NULL,
  PRIMARY KEY (`id`),
  KEY `customer_id_idx` (`customer_id`),
  CONSTRAINT `customer_id` FOREIGN KEY (`customer_id`) REFERENCES `Customers` (`id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;

CREATE TABLE `Order_Details` (
  `order_id` int(11) NOT NULL,
  `item_id` int(11) NOT NULL,
  `qty` int(11) DEFAULT NULL,
  PRIMARY KEY (`order_id`,`item_id`),
  KEY `order_id_idx` (`order_id`),
  KEY `item_id_idx` (`item_id`),
  CONSTRAINT `order_id` FOREIGN KEY (`order_id`) REFERENCES `Orders` (`id`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `item_id` FOREIGN KEY (`item_id`) REFERENCES `Products` (`product_id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;

CREATE TABLE `Customers` (
  `id` int(11) NOT NULL,
  `last` varchar(45) CHARACTER SET utf8 DEFAULT NULL,
  `first` varchar(45) CHARACTER SET utf8 DEFAULT NULL,
  `zip` char(5) CHARACTER SET utf8 NOT NULL,
  `address1` varchar(45) CHARACTER SET utf8 NOT NULL,
  `address2` varchar(45) CHARACTER SET utf8 DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;


2. Why do we need an OrderItems table?
An OrderItems table is needed because it keeps overlap out from the data. The table represents an individual order item, which is not limited to one customer and also does not limit the customer to one item. This would mean that the customer is not determined by the item.

3. Create linked tables in MS Access.

4. Create forms to enter customer data.

5. Create a form with a subform to enter orders and order item.

6. Use forms created in 4 and 5 to insert Customers and Orders.  Add customers that have not made any orders. Make the number of entries relatively small.  Why?  

7. Use SQL DML to INSERT records into Customers and Orders (and OrderItems).
INSERT INTO unemath_Waters.Customers
(id, last, first, zip, address1, address2)
VALUES
('100', 'Waters', 'Angel', '04048', '14 Parsonsfield Rd', ''),
('101', 'Lutes', 'Jennifer', '04005', '11 Hills Beach Rd', 'P.O. Box 1'),
('102', 'Quinlan', 'Professor', '04005', '11 Hills Beach Rd', 'P.O. Box 2'),
('103', 'Waters', 'Deyanira', '04061', '6 Rosemont Ave', ''),
('104', 'Waters', 'Jeff', '04048', '14 Parsonsfield Rd', ''),
('105', 'Lyons', 'Chad', '04106', '69 Smith Ave', 'P.O. Box 13')

INSERT INTO unemath_Waters.Orders
(id, customer_id, order_date)
VALUES
('2', '100', '2016-02-05'),
('3', '105', '2016-03-11'),
('4', '101', '2016-07-15'),
('5', '100', '2016-07-16'),
('6', '102', '2016-09-10')

INSERT INTO unemath_Waters.Order_Details
(order_id, item_id, qty)
VALUES
('2', '2008', '2'),
('2', '4152', '1'),
('3', '2008', '1'),
('4', '503', '3'),
('4', '1002', '1'),
('5', '2007', '1')

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
