## Example:
1.
 - `SQL:`
    SELECT count(\*) from items

 - `ANSWER:`
   100

---

1.How many users are there?

 - `SQL:` select count (*) from users;

 - `ANSWER:`+---------+
            |   count |
            |---------|
            |      50 |
            +---------+



2.What are the titles of the 5 most expensive items?

 - `SQL:`select * from items order by price desc limit 5

 - `ANSWER:`
+------+-----------------------+----------------------------+------------------------------------------+---------+
|   id | title                 | category                   | description                              |   price |
|------+-----------------------+----------------------------+------------------------------------------+---------|
|   25 | Small Cotton Gloves   | Automotive, Shoes & Beauty | Multi-layered modular service-desk       |    9984 |
|   83 | Small Wooden Computer | Health                     | Re-engineered fault-tolerant adapter     |    9859 |
|  100 | Awesome Granite Pants | Toys                       | Upgradable 24/7 access                   |    9790 |
|   40 | Sleek Wooden Hat      | Music & Baby               | Quality-focused heuristic info-mediaries |    9390 |
|   60 | Ergonomic Steel Car   | Outdoors                   | Enterprise-wide secondary firmware       |    9341 |
+------+-----------------------+----------------------------+------------------------------------------+---------+

3. What's the most expensive item in the Books category?

- 'SLQ'
select * from items WHERE category = 'Books' order by price asc limit 1

- 'ANSWER'
+------+-------------------------+------------+-------------------------------------+---------+
|   id | title                   | category   | description                         |   price |
|------+-------------------------+------------+-------------------------------------+---------|
|   76 | Ergonomic Granite Chair | Books      | De-engineered bi-directional portal |    1496 |
+------+-------------------------+------------+-------------------------------------+---------+

4. Who lives at 6439 Zettz Hills, Willmouth, WY?

- 'SLQ'
select * from users, addresses WHERE addresses.state = 'WY' AND addresses.city = 'Willmouth' and addresses.street = '6439 Zetta Hills' and addresses.user_id = users.id

-'ANSWER'
+------+--------------+-------------+--------------------------+------+-----------+------------------+-----------+---------+-------+
|   id | first_name   | last_name   | email                    |   id |   user_id | street           | city      | state   |   zip |
|------+--------------+-------------+--------------------------+------+-----------+------------------+-----------+---------+-------|
|   40 | Corrine      | Little      | rubie_kovacek@grimes.net |   43 |        40 | 6439 Zetta Hills | Willmouth | WY      | 15029 |
+------+--------------+-------------+--------------------------+------+-----------+------------------+-----------+---------+-------+


5. Correct Virginie Mitchells address to "New york,NY, 10108".

-'SLQ'
UPDATE addresses SET city = 'New york', state = 'NY', zip = '10108' WHERE user_id = 39


- 'ANSWER'
|   41 |        39 | 12263 Jake Crossing     | New york            | NY      | 10108 |
+------+-----------+-------------------------+---------------------+---------+-------+


6. How much would it cost to buy one of each item in the tools category?

- 'SLQ'
select sum(price) from items where category = 'Tools'

- 'ANSWER'
+-------+
|   sum |
|-------|
|  7383 |
+-------+



7. How many total items did we sell?

-'SQL'
select sum(quantity) from orders

- 'ANSWER'
+-------+
|   sum |
|-------|
|  2125 |
+-------+

8. How much was spent on books?

-'SQL'
select sum(orders.quantity * items.price) FROM orders, items where orders.item_id =items.id and items.category = 'Books'

-'ANSWER'
+--------+
|    sum |
|--------|
| 420566 |
+--------+



9. Simulate buying an item by inserting a user for yourself an an order for yourself

-'SQL'
INSERT INTO users VALUES (51, 'Angela', 'Coates', 'angela@angelamarii')
INSERT INTO orders VALUES (378, 51, 67, 4, '2017-02-06 00:40:30.540431')


-'ANSWER'
|  378 |        51 |        67 |          4 | 2017-02-06 00:40:30.540431 |
+------+-----------+-----------+------------+----------------------------+
