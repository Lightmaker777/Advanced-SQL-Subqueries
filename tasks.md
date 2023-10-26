## Task 1
<pre>subqueries_db=# \i /home/dci-student/24-10-2023-python-database-advanced-sql-subqueries-Lightmaker777/src/data/task1.sql 
CREATE TABLE
CREATE TYPE
CREATE TABLE
INSERT 0 105
INSERT 0 303</pre>
<pre>
subqueries_db=# \x
Expanded display is on.
subqueries_db=# SELECT id, name
FROM item
WHERE item.id NOT IN (
  SELECT item_id
  FROM stock
  WHERE quantity > 0
)
ORDER BY name;
-[ RECORD 1 ]----------------
id   | 33
name | Cheap T-shirt
-[ RECORD 2 ]----------------
id   | 103
name | Cheap T-shirt
-[ RECORD 3 ]----------------
id   | 105
name | Refurbished Smartphone
-[ RECORD 4 ]----------------
id   | 93
name | Refurbished T-shirt
</pre>
## Task 2
<pre>
-[ RECORD 1 ]--------------------
location | Outskirts 2
item_id  | 66
name     | Brand new Bike
quantity | 4
-[ RECORD 2 ]--------------------
location | Outskirts 2
item_id  | 85
name     | Brand new Bike
quantity | 4
-[ RECORD 3 ]--------------------
location | Overseas
item_id  | 85
name     | Brand new Bike
quantity | 6
-[ RECORD 4 ]--------------------
location | Central Warehouse
item_id  | 85
name     | Brand new Bike
quantity | 7
-[ RECORD 5 ]--------------------
location | Overseas
item_id  | 66
name     | Brand new Bike
quantity | 6
-[ RECORD 6 ]--------------------
location | Outskirts 2
item_id  | 24
name     | Brand new Chair
quantity | 8
-[ RECORD 7 ]--------------------
location | Outskirts 1
item_id  | 24
name     | Brand new Chair
quantity | 7
-[ RECORD 8 ]--------------------
location | Central Warehouse
item_id  | 24
</pre>
## Task 3
<pre>
-[ RECORD 1 ]------------------
name     | Brand new Monitor
location | Overseas
quantity | 9
-[ RECORD 2 ]------------------
name     | Brand new Notebook
location | Outskirts 1
quantity | 9
-[ RECORD 3 ]------------------
name     | Cheap Bike
location | Overseas
quantity | 9
-[ RECORD 4 ]------------------
name     | Cheap garden table
location | Outskirts 2
quantity | 9
-[ RECORD 5 ]------------------
name     | Cheap Keyboard
location | Central Warehouse
quantity | 9
-[ RECORD 6 ]------------------
name     | Cheap Laptop
location | Outskirts 1
quantity | 9
-[ RECORD 7 ]------------------
name     | Cheap Mouse
location | Outskirts 2
quantity | 9
-[ RECORD 8 ]------------------
name     | Cheap Notebook
location | Outskirts 2
quantity | 9
-[ RECORD 9 ]------------------
name     | Cheap Smartphone
location | Overseas
quantity | 9
-[ RECORD 10 ]-----------------
name     | Exceptional Jeans
</pre>
## Task 4
<pre>-[ RECORD 1 ]---------------------
order_id  | 1
item      | Exceptional Monitor
required  | 2
available | 0
location  | Outskirts 2
-[ RECORD 2 ]---------------------
order_id  | 2
item      | Exceptional Monitor
required  | 5
available | 0
location  | Outskirts 2
-[ RECORD 3 ]---------------------
order_id  | 2
item      | Refurbished Chair
required  | 4
available | 1
location  | Outskirts 2
-[ RECORD 4 ]---------------------
order_id  | 2
item      | Standard Monitor
required  | 4
available | 3
location  | Outskirts 2
-[ RECORD 5 ]---------------------
order_id  | 2
item      | Standard Monitor
required  | 4
available | 0
location  | Outskirts 1
-[ RECORD 6 ]---------------------
order_id  | 3
item      | Brand new Monitor
required  | 4
available | 3
location  | Outskirts 2
-[ RECORD 7 ]---------------------
order_id  | 4
</pre>


