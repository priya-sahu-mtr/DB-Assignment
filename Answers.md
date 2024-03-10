# DB-Assignment
ANSWER 1:
Here,we simplify the tables in term's of keys and breakdown of the attributes in each table:

Product table:

id (Primary Key)
name
category_id (FOREIGN KEY referencing category_id in Product_Category)
inventory
discount_id
created_at
modified_at
deleted_at

Product_Category table:

category_id (PRIMARY KEY)
name
created_at
modified_at
deleted_at

In the given schema in the figure, we can conclude that:

This relationship is often implemented in a database schema using a foreign key constraint. In the "Product" table, there would typically be a column that references the primary key of the "Product_Category" table. This column establishes the relationship between the two entities, ensuring that each product is linked to a specific product category.
Each product has a single category_id, indicating that it belongs to one category.
However, multiple products can have the same category_id, which means multiple products can belong to the same category.
This establishes a many-to-one relationship between "Product" and "Product_Category". Many products can belong to one category, but each product belongs to only one category. Therefore, the category_id attribute in the "Product" table shows a many-to-one mapping with the "Product_Category" table.

ANSWER 2:

To ensure that each product in the "Product" table has a valid category assigned to it, we can use a foreign key constraint in our database schema. Specifically, the "category_id" column or field in the "Product" table would be defined as a foreign key that references the "category_id" column in the "Product_Category" table.

Here's how we can set up the foreign key constraint:

ALTER TABLE Product
ADD CONSTRAINT FK_Product_Category
FOREIGN KEY (category_id) 
REFERENCES Product_Category(category_id);

With the help this constraint in place, whenever a new row is inserted into the "Product" table, the database will check that the value of the "category_id" column exists in the "category_id" column of the "Product_Category" table. If the value does not exist, the database will reject the insertion or update operation, ensuring that each product always has a valid category assigned to it.

This foreign key constraint helps maintain referential integrity between the two tables (Product & Product_category), preventing the possibility of inconsistency in the data of our database.






