## Problem Set 4 

1. Create three tables: Customers, Orders, and OrderItems.
SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='TRADITIONAL,ALLOW_INVALID_DATES';
-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `mydb` DEFAULT CHARACTER SET utf8 ;
USE `mydb` ;
-- -----------------------------------------------------
-- Table `mydb`.`Customers`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`Customers` (
  `customer_id` INT NOT NULL,
  `customer_last` VARCHAR(45) NULL,
  `customer_name` VARCHAR(45) NULL,
  `customer_zip` VARCHAR(5) NOT NULL,
  `customer_add1` VARCHAR(45) NOT NULL,
  `customer_add2` VARCHAR(45) NULL,
  PRIMARY KEY (`customer_id`))
ENGINE = InnoDB;
-- -----------------------------------------------------
-- Table `mydb`.`Items`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`Items` (
  `item_id` INT NOT NULL,
  `item_title` VARCHAR(45) NOT NULL,
  `item_description` VARCHAR(45) NULL,
  `item_cost` DECIMAL(2) NOT NULL,
  PRIMARY KEY (`item_id`))
ENGINE = InnoDB;
-- -----------------------------------------------------
-- Table `mydb`.`oders`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`oders` (
  `item_id` INT NOT NULL,
  `customer_id` INT NOT NULL,
  `order_id` INT NOT NULL,
  PRIMARY KEY (`order_id`),
  INDEX `customer_id_idx` (`customer_id` ASC),
  INDEX `item_id_idx` (`item_id` ASC),
  CONSTRAINT `customer_id`
    FOREIGN KEY (`customer_id`)
    REFERENCES `mydb`.`Customers` (`customer_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `item_id`
    FOREIGN KEY (`item_id`)
    REFERENCES `mydb`.`Items` (`item_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB;
SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;

2. Why do we need an OrderItems table?
An OrderItems table is needed because it keeps overlap out from the data. The table represents an individual order item, which is not limited to one customer and also does not limit the customer to one item. This would mean that the customer is not determined by the item.

3. Create linked tables in MS Access.

4. Create forms to enter customer data.

5. Create a form with a subform to enter orders and order item.

6. Use forms created in 4 and 5 to insert Customers and Orders.  Add customers that have not made any orders. Make the number of entries relatively small.  Why?  

7. Use SQL DML to INSERT records into Customers and Orders (and OrderItems).
INSERT INTO Customers
  (customer_id, customer_last, customer_name, customer_zip, customer_add1, customer_add2)
  VALUES
  ("0100", "Waters", "Angel", "04048", "14 Parsonsfield Road", "Null");
INSERT INTO items
  (item_id, item_title, item_description, item_cost)
  VALUES
  ("17557", "Notebook: blue", "This college ruled notebook is 200 sheets, with three hole punch and space to put your class schedule.",   "1.99");
INSERT INTO Orders
  (order_id, customer_id, item_id)
  VALUES
  ("8055", "0100", "17557");

8. Find all customer orders.

9. Select all customers that orders a certain product (This will depend on what data you entered into the table).  Find all customers that ordered product 3452.  

10. List 5 questions that you can answer from this data.
