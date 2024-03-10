Question 1 -
Answer-  Based on the  table structure, the relationship between the “Product” and “Product Category” entities can be inferred from the columns in the tables.
        In the “product” table, there is  a column named category_id, which likely serves as a foreign key referencing the id column in the “product_category” table. This column establishes a link between each 
       product and its corresponding category.
       
    Each product in the “product” table is associated with a specific category through the category_id column. The category_id column in the “product” table holds the ID of the category to which the product belongs. In the “product_category” table, the id column uniquely identifies each category.
    
By referencing the id column of the “product_category” table through the category_id column in the “product” table, you establish a relationship between products and their respective categories.

 One-to-Many Relationship-This Relatopnship indicates that each product belongs to One and only One product category while each Product_category can have multiple associated products .
  The relationship between the “Product” and “Product Category” entities is established through the category_id column in the “product” table, which references the primary key (id) column in the “product_category” table. This allows you to associate each product with a specific category.


 Question 2-
 Answer- To ensure that each product in the “Product” table has a valid category assigned to it, Set up a foreign key constraint between the “category_id” column in the “Product” table and the “id” column in the “product_category” table. This constraint will enforce referential integrity, ensuring that every value in the “category_id” column of the “Product” table corresponds to an existing “id” in the “product_category” table.
Implementation
ALTER TABLE Product
ADD CONSTRAINT product_category
FOREIGN KEY (category_id)
REFERENCES product_category(id);

With this constraint in place, any attempt to insert or update a product with a category_id that does not exist in the product_category table will result in a foreign key violation error,
preventing invalid data from being added to the database.
