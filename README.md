# Advanced SQL - Subqueries

## Description

In this exercise, we will practice the use of subqueries in simple SQL statements.

##

## Tasks

###

### Task 1

Create a new database and execute the file [src/data/task1.sql](src/data/task1.sql) to load the following tables:

- **item**

    - **id**: Identifier. `serial`, `PRIMARY KEY`
    - **name**: Name of the item. `varchar(100)`

- **stock**

    - **location**: Name of the location or warehouse where the item is stored. `varchar(100)`
    - **item_id**: Item identifier. `integer`, `FOREIGN KEY`
    - **quantity**: Quantity available at this location. `integer`

Your first task is to produce a list of items out of stock (they are not present in the table stock or they are present and their quantity is 0).

- Your result should be sorted by name of the item and should look like this:

| id  | name                   |
|-----|------------------------|
| 33  | Cheap T-shirt          |
| 103 | Cheap T-shirt          |
| 105 | Refurbished Smartphone |
| 93  | Refurbished T-shirt    |


##

## Task 2

Now produce a list of all items in stock. In this list you we should see the following fields:

- **location**. The name of the location where the stock is.
- **item_id**. The id of the item in stock.
- **name**. The name of this item.
- **quantity**. The amount available.

> You are not allowed to use a `JOIN` clause.

- Your result should look like this:

| location | item_id | name                   | quantity |
|----------|---------|------------------------|----------|
| Overseas | 66      | Brand new Bike         | 6        |
| Overseas | 85      | Brand new Bike         | 6        |
| Overseas | 63      | Brand new Chair        | 4        |
| Overseas | 24      | Brand new Chair        | 6        |
| Overseas | 37      | Brand new garden table | 1        |
| Overseas | 12      | Brand new Monitor      | 9        |
| Overseas | 53      | Brand new Mouse        | 1        |
| Overseas | 27      | Brand new Notebook     | 2        |
| Overseas | 49      | Brand new Smartphone   | 2        |
| Overseas | 16      | Brand new Smartphone   | 1        |
| Overseas | 14      | Brand new Tablet       | 8        |
| Overseas | 60      | Brand new T-shirt      | 2        |
| Overseas | 17      | Cheap Bike             | 9        |
| Overseas | 39      | Cheap garden table     | 7        |
| Overseas | 86      | Cheap Keyboard         | 7        |
| ...      | ...     | ...                    | ...      |


###

### Task 3

Your next task is to find out what is the maximum quantity of any items in a warehouse and list all items with that quantity.

> You are not allowed to use a `JOIN` clause.
>
> Your result should include the name of the item, the name of the location and the quantity.

- Your result should be sorted by name of the item and should look like this:

| item                 | location          | quantity |
|----------------------|-------------------|----------|
| Brand new Monitor    | Overseas          | 9        |
| Brand new Notebook   | Offskirts 1       | 9        |
| Cheap Bike           | Overseas          | 9        |
| Cheap garden table   | Offskirts 2       | 9        |
| Cheap Keyboard       | Central Warehouse | 9        |
| Cheap Laptop         | Offskirts 1       | 9        |
| Cheap Mouse          | Offskirts 2       | 9        |
| Cheap Notebook       | Offskirts 2       | 9        |
| Cheap Smartphone     | Overseas          | 9        |
| Exceptional Jeans    | Offskirts 2       | 9        |
| Exceptional Jeans    | Offskirts 1       | 9        |
| Exceptional Mouse    | Offskirts 1       | 9        |
| Exceptional T-shirt  | Offskirts 2       | 9        |
| Exceptional T-shirt  | Central Warehouse | 9        |
| Refurbished Bike     | Offskirts 2       | 9        |
| Refurbished Jeans    | Overseas          | 9        |
| Refurbished Jeans    | Central Warehouse | 9        |
| Refurbished Keyboard | Overseas          | 9        |
| Refurbished Notebook | Overseas          | 9        |
| Standard Monitor     | Central Warehouse | 9        |
| Used Laptop          | Overseas          | 9        |
| Used Laptop          | Offskirts 2       | 9        |
| Used Mouse           | Central Warehouse | 9        |

###

### Task 4

Execute the file [src/data/task4.sql](src/data/task4.sql) to load the following tables into the current database:

- **order**

    - **id**: Identifier. `serial`, `PRIMARY KEY`
    - **user_id**: User identifier. `integer`, `FOREIGN KEY`

- **ordered_items**

    - **order_id**: Order identifier. `serial`, `FOREIGN KEY`
    - **item_id**: Item identifier. `integer`, `FOREIGN KEY`
    - **quantity**: Amount of items ordered. `integer`


Find out which orders and items cannot be shipped due to lack of stock.

For the shipping of an order we need to have all the required items in sufficient quantity from a single location.

The result should be sorted by order_id first and then by item's name, and should include the following fields:

- **order_id**: id of the order
- **item**: the name of the item missing
- **required**: the quantity ordered
- **available**: the maximum quantity available at any single location
- **location**: the name of any location having the maximum availability

- Your result should look like this:

| order_id | item              | required | available | location          |
|----------|-------------------|----------|-----------|-------------------|
| 1        | Cheap T-shirt     | 5        |           |                   |
| 16       | Used garden table | 4        | 2         | Overseas          |
| 26       | Used Notebook     | 3        | 2         | Central Warehouse |
| 29       | Cheap Smartphone  | 5        | 4         | Offskirts 2       |
| 32       | Brand new Mouse   | 5        | 1         | Overseas          |
| 40       | Cheap T-shirt     | 5        | 0         | Central Warehouse |
| 43       | Standard Keyboard | 4        | 1         | Overseas          |
| 44       | Cheap Smartphone  | 5        | 4         | Offskirts 2       |
| 57       | Cheap T-shirt     | 4        | 2         | Offskirts 2       |
| 65       | Standard Keyboard | 4        | 1         | Overseas          |
| 65       | Used Notebook     | 5        | 2         | Central Warehouse |
| 66       | Cheap Smartphone  | 5        | 4         | Offskirts 2       |
| 74       | Cheap T-shirt     | 1        |           |                   |
| 82       | Cheap T-shirt     | 4        | 0         | Central Warehouse |
| 83       | Used Chair        | 4        | 2         | Offskirts 1       |
| ...      | ...               | ...      | ...       | ...               |
