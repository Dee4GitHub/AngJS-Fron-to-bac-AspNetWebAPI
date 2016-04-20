#Chapter 03 Retrieving Data

#Lesson 14 Building the Products Controller in Web API 

- Open the Visual studio solution ACME Product Managment(APM) 
- Select API Web Project in the solution
- Set APM.WebAPI Project as the startup project
- In the Controllers Folder, Add a new "Web API 2 controller with read/write actions".
- Controller name is Products
- Change / rewrite the Get method as follows:
   public IEnumerable<Product> Get()
   {
		var productRepository = new ProductRepository();
		return productRepository.Retrieve();
   }
	




