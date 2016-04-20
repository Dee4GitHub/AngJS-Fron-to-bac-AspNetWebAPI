#Chapter 03 Retrieving Data

#Lesson 13 Building the Repository

- Open the Visual studio solution ACME Product Managment(APM) 
- Select API Web Project in the solution
- Set APM.WebAPI Project as the startup project
- In the Models Folder Create a Class called ProductRepository.cs file
- Add the following internal methods to the class:
	- internal Product Create() --> Creates a new product with default values
	- internal List<Product> Retrieve() -->Retrieves the list of products
	- internal Product Save(Product product) --> Saves a new product
	- internal Product Save (int id, Product product) --> Updates an existing product
-In the App_Data folder add product.json file enlisting data of sample products
	




