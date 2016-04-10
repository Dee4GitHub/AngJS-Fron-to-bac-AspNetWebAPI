#Chapter 02 Getting Started Angular and Web API

#Lesson 09 Anatomy of an ASP.Net Web API Service

- Open the Visual studio solution ACME Product Managment(APM) 
- Select API Web Project in the solution
- Set APM.WebAPI Project as the startup project
- Open the WebApiConfig.cs
- Comment the following lines of code (for now the authentication is disabled, will enable later in the course)
      config.SuppressDefaultHostAuthentication();
	  config.Filters.Add(new HostAuthenticationFilter(OAuthDefaults.AuthenticationType));
- Save the file and close it
- Open the ValuesController.cs file present in the Controllers Folder
- Comment the "[Authorize]" keyword at the top
- Save the file and run the application
- Notice the Asp.net Sample page comes up in the browser
- Click on Api tab in the top menu
- Copy the Url for Get api/Values/{id} 
- Paste in the Address bar to form the URL http://localhost:62373/api/Values/5 and press Enter
- Notice that it returns a string "value" retruned by the Web Api method Get in the Values Controller



