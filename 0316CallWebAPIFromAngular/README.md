#Chapter 03 Retrieving Data

#Lesson 16 Calling Web API from Angular 

- Open the Visual studio solution ACME Product Managment(APM) 
- Open the APM.Client Project
- Right click on APM.Client Project and select Manage NuGet Packages from the menu
- Search for Angular, in the search results choose package "AngularJS Resource" and install
- Close the NuGet Package Manager
- Open Index.Html and add a reference to angular-resource.js under angularJS reference line
- Right click on APM.Client Project and Add a new folder "common"
- Inside the common folder add a javascript file by name "common.services.js"
- Open Index.html and add a reference to common.Services.js under Services comment
- In the common.services.js file add the following code to creat common.services with dependency ng-Resource
	(function () {
		"use strict";
		angular.module("common.services", ["ngResource"])
			.constant("appSettings", {
            serverPath: "http://localhost:62373/"
        });
	}());
	#note: the port number is the same portnumber shown in properties of webAPI project under application URL

- Inside the common folder add a javascript file by name "productsResource.js"
- Open Index.html and add a reference to productsResource.js just under common.services.js reference statement
- In the productsResource.js file add the following code to intialise the productsResource with APM Web API
	(function() {
    "use strict";
    function productResource($resource, appSettings) {
        return $resource(appSettings.serverPath + "/api/products/:id");
    }
    angular.module("common.services")
        .factory("productResource", [
            "$resource", "appSettings", productResource
        ]);

	}())
- In the App.js add dependency for "common.services"
- In productCtrl.js, remove the vm.products = .... and add the following code
	       productResource.query(function(data) {
            vm.products = data;
        });
- Also in productCtrl.js add the dependency for productResource as variable.
- In the properties of APM.WebAPI project set the statup of the project to "Do not show the startup page setting"
- Right click the solution and chose startup projects. 
- Choose multiple startup projects
- set both projects to start and close the window.
- Run the application and see the Products page is displayed
- Note that no products are displayed on page due to Cross Origin Reguest (CORS) issue. This will get resolved in the next Chapter 4
	

