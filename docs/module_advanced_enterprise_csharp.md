# Enterprise module (C# branch)

## ASP.NET Core

### What Is the difference between .NET Core and .NET Standard? How do them relate to “classic” .NET?
.NET Core is a free, cross-platform, open source implementation of the managed framework.Windows Forms are not part of .NET Core. Technically, .NET Core only supports console applications. 
Unlike the .NET Framework, .NET Core is not considered a Windows component. Therefore, updates come as NuGet packages, not through Windows Update.

Each implementation of the managed framework has its own set of Base Class Libraries..NET Standard is a specification for implementing the BCL.
The relationship between .NET Standard and a .NET implementation is the same as between the HTML specification and a browser. The second is an implementation of the first.
Each .NET version has an associated version of the .NET Standard. .NET Standard is defined as a single NuGet package because all .NET implementations are required to support it.

### What is ASP.NET MVC?
MVC is a design pattern used to decouple user-interface (view), data (model), and application logic (controller). This pattern helps to achieve separation of concerns.

### Can you explain Model, Controller and View in MVC?
The Model-View-Controller (MVC) architectural pattern separates an application into three main groups of components: Models, Views, and Controllers.

The Model in an MVC application represents the state of the application and any business logic or operations that should be performed by it. Business logic should be encapsulated in the model, along with any implementation logic for persisting the state of the application.

Views are responsible for presenting content through the user interface. There should be minimal logic within views, and any logic in them should relate to presenting content.

Controllers are the components that handle user interaction, work with the model, and ultimately select a view to render. In an MVC application, the view only displays information; the controller handles and responds to user input and interaction. In the MVC pattern, the controller is the initial entry point, and is responsible for selecting which model types to work with and which view to render (hence its name - it controls how the app responds to a given request).

### Explain the page lifecycle of MVC.
1)Routing - routes url to its controller and action
2)Url Routing Module intercepts the Request - Whenever you make a request against an ASP.NET MVC application, the request is intercepted by the UrlRoutingModule HTTP Module.
3)MVC Handler Executes -  the MVC Handler executes and when the process request method is called a new controller gets created.
4)Controller Executes - controller is called and its action called requested by user.
5)Render View Method Called - at last when we call reutrn View() Render View method is called and puts reponse on the page to be displayed.


### What is Razor View Engine?
Razor View engine is a markup syntax which helps us to write HTML and server-side code in web pages using C#.It is server-side markup language however it is not at all a programming language.
Razor is a templating engine and ASP.NET MVC has implemented a view engine which allows us to use Razor inside of an MVC application to produce HTML. 
However, Razor does not have any ties with ASP.NET MVC.

### What you mean by Routing in MVC?
Routing enables us to define a URL pattern that maps to the request handler. The request handler in MVC  is the Controller class and Action method.

### What is Layout in MVC?
An application may contain a specific UI portion that remains the same throughout the application, such as header, left navigation bar, right bar, or footer section. 
ASP.NET MVC introduced a Layout view which contains these common UI portions so that we don't have to write the same code in every page.

### What ConfigureServices() method does in Startup.cs?
As the name suggests, it's a method for configuring services that are used by your application. ConfigureServices it's the first method to be called, before Configure method.
Adding services to the services container makes them available within your application via dependency injection.
The ConfigureServices method is also where you should add configuration option classes that you would like to have available in your application

### What Configure() method does in Startup.cs?
The Configure method is used to specify how the ASP.NET application will respond to individual HTTP requests. 
Each Use extension method adds middleware to the request pipeline. 
For instance, the UseMvc extension method adds the routing middleware to the request pipeline and configures MVC as the default handler.

### What is wwwroot folder in ASP.NET Core?
The wwwroot folder is new in ASP.NET 5.0. All of the static files in your project go into this folder. 
These are assets that the app will serve directly to clients, including HTML files, CSS files, image files, and JavaScript files. The wwwroot folder is the root of your web site. 
That is, http://some.hostname/ points to wwwroot, all URLs for static content are relative to the wwwroot folder.

### What’s the usage of [InternalsVisibleTo] attribute? What are pros and cons of it?
The [InternalVisibleTo] attribute specifies that types that are ordinarily visible only within the current assembly are visible to a specified assembly.
PROS: 
-Keeps your public API limited to what you want to publish
-Provides greater flexibility for internal refactoring and backwards compatibility
-Allows your test libraries to access internal classes and methods for additional testing and coverage
CONS:
-Easily abused, so things usually marked “private” are now marked “internal”
-Potential loss of encapsulation
-Decision about what should be public could be wrong
-Essentially two levels of “public” visibility that have to be managed

## Object Relational Mapping, Entity Framework

### What is an ORM? What are benefits, when to use?
ORM is a technique that lets you query and manipulate data from a database using an object-oriented paradigm.
Usually we are reffering to a library that implements the Object-Relational Mapping technique.
PROS:
- DRY: You write your data model in only one place, and it's easier to update, maintain, and reuse the code.
- A lot of procedures are done automatically
- Forces you to write MVC code which make your code cleaner
- You don't have to write poorly-formed SQL
- Sanitizing: using prepared statements that are as easy as calling a method
- It fits in your natural way of coding
- It abstracts the DB system, so you can change it whenever you want.

CONS:
-You have to learn it, and ORM libraries are not lightweight tools;
-You have to set it up. Same problem.
-It can lead to performance issues very easily. It is very likely that the data access code generated by the ORM is more complex than you'd typically write for an application. 
This is because most ORMs are designed to handle a wide variety of data-use scenarios

### What is Entity Framework? What are the advantages, limitations?
Entity Framework is an open-source ORM framework for .NET applications supported by Microsoft. 
It enables developers to work with data using objects of domain specific classes without focusing on the underlying database tables and columns where this data is stored. 
With the Entity Framework, developers can work at a higher level of abstraction when they deal with data, and can create and maintain data-oriented applications with less code compared with traditional applications.

Advantages of Entity Framework

-Cross-platform: EF Core is a cross-platform framework which can run on Windows, Linux and Mac.
-Querying: EF allows us to use LINQ queries (C#/VB.NET) to retrieve data from the underlying database.
-Modelling: EF (Entity Framework) creates an EDM (Entity Data Model) with entities with get/set properties of different data types. 
It uses this model when querying or saving entity data to the underlying database.
-Saving: EF executes INSERT, UPDATE, and DELETE commands to the database based on the changes occurred to your entities when you call the SaveChanges() method.
EF also provides the asynchronous SaveChangesAsync() method.
-It provides auto generated code
-It reduce development time and cost


Disadvantages of Entity Framework

-Lazy loading is the main drawbacks of EF
-Its syntax is complicated
-It is not available for every RDMS
-Need to handle data in nontraditional way


### What is lazy loading?
Lazy loading is an optimization technique for the online content, be it a website or a web app.
Instead of loading the entire web page and rendering it to the user in one go as in bulk loading, the concept of lazy loading assists in loading only the required section and delays the remaining, until it is needed by the user.

In EF core lazy loading means that the related data is transparently loaded from the database when the navigation property is accessed. However, this can very easily create problems, hence it is often preffered to use eager loading.

### What is the difference between code first and DB first approach?
In code first approach we will first create entity classes with properties defined in it. Entity framework will create the database and tables based on the entity classes defined. 
So database is generated from the code.

In this approach Database and tables are created first. Then you create entity Data Model using the created database.

### What is a migration script?
Migration is a way to keep the database schema in sync with the EF Core model by preserving data.
In EF Core migrations will create or update the database schema based on the EF Core model. 
Whenever you change the domain classes, you need to run migration to keep the database schema up to date.
EF Core migrations are a set of commands which you can execute in NuGet Package Manager Console or in dotnet Command Line Interface 

### What is a navigation property?
Navigation properties provide a way to navigate an association between two entity types. Every object can have a navigation property for every relationship in which it participates. 
Navigation properties allow you to navigate and manage relationships in both directions, returning either a reference object (if the multiplicity is either one or zero-or-one) or a collection (if the multiplicity is many). 

### Name 3 different attributes used in EF Core, what can they do for you?
1)Key 
The Key attribute can be applied to a property in an entity class to make it a key property and the corresponding column to a PrimaryKey column in the database.
2)Required 
The Required attribute can be applied to one or more properties in an entity class. EF will create a NOT NULL column in a database table for a property on which the Required attribute is applied.
3)MaxLength 
The MaxLength attribute specifies the maximum length of data value allowed for a property which in turn sets the size of a corresponding column in the database.
4)MinLength
Same logic as before.