# Bike Sales Database Analysis

This repository contains SQL queries and analysis I've performed on a bike sales database I found. The database schema includes information about customers, staff, stores, orders, order items, product categories, products, stock levels, and brands.

## Database Schema

The database consists of the following tables:

* **CUSTOMERS**: Information about customers.
    * `customer_id` (PK)
    * `first_name`
    * `last_name`
    * `phone`
    * `email`
    * `street`
    * `city`
    * `state`
    * `zip_code`
* **STAFFS**: Information about store staff.
    * `staff_id` (PK)
    * `first_name`
    * `last_name`
    * `email`
    * `phone`
    * `active` (boolean)
    * `store_id` (FK to STORES)
    * `manager_id` (FK to STAFFS - self-referencing)
* **STORES**: Details about the retail stores.
    * `store_id` (PK)
    * `store_name`
    * `phone`
    * `email`
    * `street`
    * `city`
    * `state`
    * `zip_code`
* **ORDERS**: Records of customer orders.
    * `order_id` (PK)
    * `customer_id` (FK to CUSTOMERS)
    * `order_status` (e.g., 1=Pending, 2=Processing, 3=Rejected, 4=Completed)
    * `order_date`
    * `required_date`
    * `shipped_date`
    * `store_id` (FK to STORES)
    * `staff_id` (FK to STAFFS)
* **ORDER\_ITEMS**: Details of individual items within an order.
    * `order_id` (FK to ORDERS, part of PK)
    * `item_id` (part of PK)
    * `product_id` (FK to PRODUCTS)
    * `quantity`
    * `list_price` (at the time of order)
    * `discount`
* **CATEGORIES**: Product categories.
    * `category_id` (PK)
    * `category_name`
* **PRODUCTS**: Information about the products sold.
    * `product_id` (PK)
    * `product_name`
    * `brand_id` (FK to BRANDS)
    * `category_id` (FK to CATEGORIES)
    * `model_year`
    * `list_price`
* **STOCKS**: Inventory levels at each store.
    * `store_id` (FK to STORES, part of PK)
    * `product_id` (FK to PRODUCTS, part of PK)
    * `quantity`
* **BRANDS**: Product brands.
    * `brand_id` (PK)
    * `brand_name`

## Analysis Goals

The goal of this analysis is to explore different aspects of the bike sales data, such as:

* Understanding who our customers are and where they are located.
* Looking at how sales are performing.
* Figuring out which products and brands are popular.
* Getting a sense of the inventory we have.

## Contents

This repository contains:

* `queries/`: A folder with SQL files containing the queries I've used.

## Getting Started

1.  **Database**: You'll need the SQLite database file (`.db` file) to run the queries.
2.  **SQL Client**: You can use any SQLite client (like DB Browser for SQLite or the `sqlite3` command line tool) to execute the SQL files in the `queries/` directory.

## What I've Explored

So far, I've looked into questions like:

* How much data is in each table?
* What kinds of product categories and brands are there?
* Where are the stores located?
* How have orders changed over time?
* Which products and brands sell the most?
* Who are our best customers?
* What's the stock situation for different products in each store?

## Contributions
If you have any ideas or want to contribute, feel free to reach out!
