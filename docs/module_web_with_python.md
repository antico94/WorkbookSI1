git # Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
R:
Avoid the name of a table/column in the plural. It is better to use employee instead of employees
If the name of the table or column must consist of more than one word, use an underscore to connect them, for example employee_city. Some professionals prefer to use what is called CamelCase style instead, for example EmployeeCity. The preferred style is different for different relational database systems
Check that the name is not already used as a keyword in SQL
If the name is the same as an SQL keyword, enclose the name within quotation marks
The name of an object in a database for a table or a column should be unique and not too long. Avoid special characters in the name like $, &, * , etc. (use only letters, numbers, and underscores)
Use an underscore in a name only if necessary

#### What layers can you name in a simple web application?
R: Presentation layer (PL)
Data service layer (DSL)
Business logic layer (BLL)
Data access layer (DAL)


### Error handling
#### What error can occur, when an array does not have an element on the requested index?
R: `IndexOutOfRangeException`

#### What is the “finally” block, and how would you use it?
R: The finally block in java is used to put important codes such as clean up code e.g. closing the file or closing the connection. The finally block executes whether exception rise or not and whether exception handled or not. A finally contains all the crucial statements regardless of the exception occurs or not.
#### Why should we catch special exception types?

### Security
#### What is SQL injection? How to protect an application against it?
R: The only sure way to prevent SQL Injection attacks is input validation and parametrized queries including prepared statements. The application code should never use the input directly.

#### What is XSS? How to protect an application against it?
R: Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or encoding it.
Filter input on arrival. At the point where user input is received, filter as strictly as possible based on what is expected or valid input.
Encode data on output. At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
Use appropriate response headers. To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way you intend.
Content Security Policy. As a last line of defense, you can use Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.

#### How to properly store passwords?
R: Never Store Plaintext Passwords, always encrypt them using the available methods existing already, the more complex, the safest.

#### What is HTTPS?
R: HTTPS stands for Hypertext Transfer Protocol Secure. It is the protocol where encrypted HTTP data is transferred over a secure connection. ... By virtue, HTTPS encryption is done bi-directionally, which means that the data is encrypted at both the client and server sides.

#### What is encryption and decryption?
R: Encryption is the process of translating plain text data (plaintext) into something that appears to be random and meaningless (ciphertext). Decryption is the process of converting ciphertext back to plaintext. ... To decrypt a particular piece of ciphertext, the key that was used to encrypt the data must be used.

#### What is hashing?
R: Hashing is the process of converting a given key into another value. A hash function is used to generate the new value according to a mathematical algorithm. The result of a hash function is known as a hash value or simply, a hash.

#### What is the difference between encryption and hashing? When would you use which?
R: Encryption is a two-way function; what is encrypted can be decrypted with the proper key. Hashing, however, is a one-way function that scrambles plain text to produce a unique message digest. With a properly designed algorithm, there is no way to reverse the hashing process to reveal the original password.
Encryption is used usually for messages, headers and hashing for passwords.

#### What encryption methods do you know?
R: AES, RSA, Triple DES, Twofish.

#### What hashing methods do you know?
R: MD5, SHA-1, SHA-2, NTLM, and LANMAN.

#### How/where would you store sensitive data (like db password, API key, ...) of your application?
R: In a unit that does not have access to Internet, is protected by a password and i only know about it.

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
R: Stack and Queue both are the non-primitive data structures. The main differences between stack and queue are that stack uses LIFO (last in first out) method to access and add data elements whereas Queue uses FIFO (First in first out) method to access and add data elements.

#### What is BubbleSort? Describe the main logic of this sorting algorithm.
R: Bubble Sort is a simple algorithm which is used to sort a given set of n elements provided in form of an array with n number of elements. ... Sorting takes place by stepping through all the elements one-by-one and comparing it with the adjacent element and swapping them if required.

#### Explain the process of finding the maximum and minimum value in a list of numbers!
R: We declare and initialize variables max and min to store maximum and minimum. Traverse the array from i = 1 to n-1 and compare each element with min and max. If (X[i] < min), it means we have found a value smaller than minimum value till ith index. We update min with X[i] i.e min = X[i].

#### Explain the process of calculating the average value in an array of numbers!
R: We declare and initialize variables count and sum, for each number in the array we raise count with 1 and add the value of the number to the sum, at the last number of the array we divide the sum by the count and that's our average

#### What is Big O complexity? Explain time and space complexity!
R: Big O notation is a formal expression of an algorithm's complexity in relation to the growth of the input size. Hence, it is used to rank algorithms based on their performance with large inputs.
Time complexity is a function describing the amount of time an algorithm takes in terms of the amount of input to the algorithm. ... Space complexity is a function describing the amount of memory (space) an algorithm takes in terms of the amount of input to the algorithm.

#### Explain the process of calculating the average value in a list of numbers!
We declare and initialize variables count and sum, for each number in the array we raise count with 1 and add the value of the number to the sum, at the last number of the array we divide the sum by the count and that's our average.


### Procedural
#### How the CASE condition works in SQL?
R: The CASE statement goes through conditions and returns a value when the first condition is met (like an if-then-else statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

#### How the switch-case condition works in JavaScript?
R: How does switch case work in JavaScript?
The switch statement evaluates an expression. The value of the expression is then compared with the values of each case in the structure. If there is a match, the associated block of code is executed. The switch statement is often used together with a break or a default keyword (or both).

#### How to achieve a switch-case-like structure in Python?
R: `def switch_demo(argument):
switcher = {
1: "January",
2: "February",
3: "March",
4: "April",
5: "May",
6: "June",
7: "July",
8: "August",
9: "September",
10: "October",
11: "November",
12: "December"
}
print switcher.get(argument, "Invalid month")`

#### Explain variable scoping in Python!
R: The scope of a variable refers to the context in which that variable is visible/accessible to the Python interpreter.

#### What’s the difference between const and var in JavaScript?
R: var declarations are globally scoped or function scoped while let and const are block scoped. var variables can be updated and re-declared within its scope; let variables can be updated but not re-declared; const variables can neither be updated nor re-declared. They are all hoisted to the top of their scope.

#### How the list comprehension looks like in Python?
R: `number_list = [ x for x in range(20) if x % 2 == 0]
print(number_list)`

#### How the “ternary expression” looks like in Python?
R: `1 if A else 2 if B else 3`

#### How the ternary expression looks like in JavaScript?
R: `function getFee(isMember) {
return (isMember ? '$2.00' : '$10.00');
}

console.log(getFee(true));
// expected output: "$2.00"

console.log(getFee(false));
// expected output: "$10.00"

console.log(getFee(null));
// expected output: "$10.00"`

#### How to import a function from another module in Python?
R: Create a Python file containing the required functions. Create another Python file and import the previous Python file into it. Call the functions defined in the imported file.

#### How to import a function from another module in JavaScript?
R: For importing any module, use a function called 'Require' which takes in the module name and if its user defined module then its relative path as argument and returns its reference. The script. js contains the above JavaScript module (library. js)

### Functional
#### What is recursion?
R: In computer science, recursion is a programming technique using function or algorithm that calls itself one or more times until a specified condition is met at which time the rest of each repetition is processed from the last one called to the first.

#### Write a recursive function which calculates the Fibonacci numbers!
R: `def recur_fibo(n):
if n <= 1:
return n
else:
return(recur_fibo(n-1) + recur_fibo(n-2))

nterms = 10

# check if the number of terms is valid
if nterms <= 0:
print("Plese enter a positive integer")
else:
print("Fibonacci sequence:")
for i in range(nterms):
print(recur_fibo(i))`

#### How to store a function in a variable in Python?
R: 

def value():
resp = requests.get('http://www.google.com').elapsed.total_seconds()
return resp

test = value()

while True:
print test

#### List the ways of defining a callable logical unit in JavaScript!
R: 

#### What is an event listener? How to attach one?
R: An event listener is a procedure in JavaScript that waits for an event to occur. The simple example of an event is a user clicking the mouse or pressing a key on the keyboard
To add an event handler to an event of an element, you use the addEventListener() method of the element object.

#### How to trigger an event in JavaScript?
R: 
We create an event using the Event constructor.
We listen to this event using the addEventListener() method.
We trigger or dispatch the event using element. dispatchEvent(eventName) method.
A custom Event named start has now been created.

#### What is a callback function? Tell some examples of its usage.
R: A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.
We usually use callbacks when we fetch data and want to do something afterwards with data gathered.

#### What is a Python decorator? How does it work? Tell some examples of its usage.
R: A decorator in Python is a function that takes another function as its argument, and returns yet another function . Decorators can be extremely useful as they allow the extension of an existing function, without any modification to the original function source code.
`def decorator_list(fnc):
def inner(list_of_tuples):
return [fnc(val[0], val[1]) for val in list_of_tuples]
return inner


@decorator_list
def add_together(a, b):
return a + b


print(add_together([(1, 3), (3, 17), (5, 5), (6, 7)]))`

#### What is the difference between synchronous and asynchronous execution?
R: Synchronous execution means the first task in a program must finish processing before moving on to executing the next task whereas asynchronous execution means a second task can begin executing in parallel, without waiting for an earlier task to finish.


## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
R: 'connS' contains the connection string. This is what allows an application to open a connection and execute a SQL query with a database. Within it, you can see that the server and database names are provided, as well as what credentials are needed (same ones used to access the database via SSMS).
You could simply advertise your database connection address and port number on an open connection. This would allow anyone with the right authentication to get into the database using a direct connection, a client browser tool like Toad, or a command-line tool like “mysql” for MySQL or “sqlplus” for Oracle. This wouldn’t be a very “pretty” interface, but would function for both humans and programs. But I certainly don’t advise this as it’s totally insecure and brutally hard to manage.
You could have a simple HTTP interface that accepts a login/password, lets the user enter SQL text, and displays the results. This would be a bit more “controlled” than the above, but not much…
If you want to allow stuff like mobile apps to have access to a database, a pretty standard way to do it is to design an API to the database, and have a server-side app that accepts the inbound API call, keeps connections to the DB, executes the queries appropriate to the API call, and returns results to the caller using a formatted outbound API. Nowadays, these are usually done using JSON as the transport language, although you still have to define what’s actually in the API.
The last option is typically the preferred approach as you can change the underlying DB schema without needing to change the API and the apps using it to dialog with the database. It’s also quite a bit more secure.

#### When do you use the DISTINCT keyword in SQL?
R: The SQL DISTINCT keyword is used in conjunction with the SELECT statement to eliminate all the duplicate records and fetching only unique records. There may be a situation when you have multiple duplicate records in a table.

#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?
R: The SQL WHERE clause is used to specify a condition while fetching the data from a single table or by joining with multiple tables. If the given condition is satisfied, then only it returns a specific value from the table. You should use the WHERE clause to filter the records and fetching only the necessary records.
The GROUP BY Statement in SQL is used to arrange identical data into groups with the help of some functions. i.e if a particular column has same values in different rows then it will arrange these rows in a group. ... GROUP BY clause is used with the SELECT statement.
A HAVING clause in SQL specifies that an SQL SELECT statement must only return rows where aggregate values meet the specified conditions.
What does ORDER BY do in SQL?
The ORDER BY keyword is used to sort the result-set in ascending or descending order. The ORDER BY keyword sorts the records in ascending order by default.

#### What are aggregate functions in SQL? Give 3 examples.
R: In database management an aggregate function is a function where the values of multiple rows are grouped together as input on certain criteria to form a single value of more significant meaning
`1) Count()
2) Sum()
3) Avg()
4) Min()
5) Max()`
6) 
#### What kind of JOIN types do you know in SQL? Could you give examples?
R:
Inner Join / Simple Join.
Left Outer Join / Left Join.
Right Outer Join / Right Join.
Full Outer Join.
Cross Join.
Self Join.

#### What are the constraints in sql?
R: Constraints in SQL Server are predefined rules and restrictions that are enforced in a single column or multiple columns, regarding the values allowed in the columns, to maintain the integrity, accuracy, and reliability of that column's data

#### What is a cursor in SQL? Why would you use one?
R: A SQL cursor is a database object that is used to retrieve data from a result set one row at a time. A SQL cursor is used when the data needs to be updated row by row.

#### What are database indexes? When to use?
R: A database index is a data structure that improves the speed of data retrieval operations on a database table at the cost of additional writes and storage space to maintain the index data structure. ... An index is a copy of selected columns of data, from a table, that is designed to enable very efficient search.

#### What are database transactions? When to use?
R: A database transaction symbolizes a unit of work performed within a database management system (or similar system) against a database, and treated in a coherent and reliable way independent of other transactions. A transaction generally represents any change in a database.

#### What kind of database relations do you know? How to define them?
R: There are three types of relationships between the data you are likely to encounter at this stage in the design: one-to-one, one-to-many, and many-to-many. To be able to identify these relationships, you need to examine the data and have an understanding of what business rules apply to the data and tables.

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?
`SELECT * FROM address`

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
R: n general, if your application is structured into layers, have the data access tier call a stored procedure on your database server to write a log of the database changes.

In languages that support such a thing aspect-oriented programming can be a good technique to use for this kind of application. Auditing database table changes is the kind of operation that you'll typically want to log for all operations, so AOP can work very nicely.

Bear in mind that logging database changes will create lots of data and will slow the system down. It may be sensible to use a message-queue solution and a separate database to perform the audit log, depending on the size of the application.

It's also perfectly feasible to use stored procedures to handle this, although there may be a bit of work involved passing user credentials through to the database itself.

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
R: HTML is the HyperText Markup Language, which is designed to create structured documents and provide for semantic meaning behind the documents. HTML5 is the next version of the HTML specification.

XML is the Extensible Markup Language, which provides rules for creating, structuring, and encoding documents. You often see XML being used to store data and to allow for communication between applications. It's programming language-agnostic - all of the major programming languages provide mechanisms for reading and writing XML documents, either as part of the core or in external libraries.

XHTML is an XML-based HTML. It serves the same function as HTML, but with the same rules as XML documents. These rules deal with the structure of the markup.

#### How to include a JavaScript file in a webpage?
R: To include an external JavaScript file, we can use the script tag with the attribute src . You've already used the src attribute when using images. The value for the src attribute should be the path to your JavaScript file. This script tag should be included between the <head> tags in your HTML document

#### How to include a CSS file in a webpage?
R: By adding a <link> element, inside the head section targeted at the CSS file path.

#### How to select an element using its id in CSS?
R: Using the # followed by the id value.

#### How to select elements using their class in CSS?
R: Using the . followed by the class name.

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?

#### How to select all list items in all ordered lists on the page in CSS?
#### How to select elements using their attributes in CSS?
R: [attribute^=”value”] Selector: This selector is used to select all the elements whose attribute value begins with the specified value. The value doesn't need to be a whole word. [attribute$=”value”] Selector: This selector is used to select all the elements whose attribute value ends with the specified value.

#### What are UX and UI?
R: UX (user experience) and UI (user interface) are two interdependent terms. While UI generally deals with the interaction between users and computer systems, software and applications, UX deals more generally with a user's overall experience with a brand, product or service.

#### Please list some points that an application should fulfill to have good UX.
R: Useful – Content should be original and fulfill a need.
Usable – Site must be easy to find.
Desirable – Design elements bring about emotion and appreciation.
Findable – Content needs to be locatable and navigable offsite and onsite.

#### What is XML, XSLT, DTD?
R: The Extensible Markup Language (XML) is a simple text-based format for representing structured information: documents, data, configuration, books, transactions, invoices, and much more. It was derived from an older standard format called SGML (ISO 8879), in order to be more suitable for Web use.
XSLT (Extensible Stylesheet Language Transformations) is a language for transforming XML documents into other XML documents, or other formats such as HTML for web pages, plain text or XSL Formatting Objects, which may subsequently be converted to other formats, such as PDF, PostScript and PNG.
A  document type definition (DTD) is a set of markup declarations that define a document type for an SGML-family markup language (GML, SGML, XML, HTML). ... It defines the document structure with a list of validated elements and attributes. A DTD can be declared inline inside an XML document, or as an external reference

#### What is the difference between HTML and XML?
R: HTML and XML are related to each other, where HTML displays data and describes the structure of a webpage, whereas XML stores and transfers data. HTML is a simple predefined language, while XML is a standard language that defines other languages.


### Javascript

#### What is javascript?
R:JavaScript is a text-based programming language used both on the client-side and server-side that allows you to make web pages interactive. ... Incorporating JavaScript improves the user experience of the web page by converting it from a static page into an interactive one. To recap, JavaScript adds behavior to web pages.

#### When to use AJAX? Bring examples of its usage.
R: Ajax should be used anywhere in a web application where small amounts of information could be saved or retrieved from the server without posting back the entire pages. A good example of this is data validation on save actions.

#### What is DOM and how to manipulate it from Javascript?
R: The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.
To manipulate an element inside the DOM, you first need to select it and store a reference to it inside a variable. Inside your script element, add the following line:
const link = document.querySelector('a');
Now you can manipulate the document.

#### What are events and how/why to use them in Javascript?
R: JavaScript's interaction with HTML is handled through events that occur when the user or the browser manipulates a page. When the page loads, it is called an event. When the user clicks a button, that click too is an event. Other examples include events like pressing any key, closing a window, resizing a window, etc.
Event handlers can be used to handle and verify user input, user actions, and browser actions: Things that should be done every time a page loads. Things that should be done when the page is closed. Action that should be performed when a user clicks a button.

#### What is event bubbling/capturing? How would you use it?
R: With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements. With capturing, the event is first captured by the outermost element and propagated to the inner elements.
Event capturing is the event starts from top element to the target element. It is the opposite of Event bubbling, which starts from target element to the top element.

#### What is JSON and how do we use it?
JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax. It is commonly used for transmitting data in web applications (e.g., sending some data from the server to the client, so it can be displayed on a web page, or vice versa).
SON format is used for serializing and transmitting structured data over network connection. It is primarily used to transmit data between a server and web applications. Web services and APIs use JSON format to provide public data. It can be used with modern programming languages.


## Software engineering

### Version control

#### What type of branching strategy would you use?
R: Release Branching {A release branching strategy involves creating a branch for a potential release that includes all applicable stories. When a team starts working on a new release, the branch is created. For teams that need to support multiple releases and patch versions over time, a release branching strategy is required}

#### What would you do if you find a bug on the production code (master branch)?
R: If you want to fix a bug on production create "Hotfix" branch off master. Resolve the bug in that and then merge it in master.

#### How can you move changes from one branch to another in GIT?
R: By merging them.

#### How does a VCS help with code reviews?
R: It helps because you can see the code before then review and the code afterwards, so you will always know what and how it was improved.

#### What is your favorite git command? Why?
R: Pull, because i can always be updated on what my colleagues/workmates have done.

#### What does remote/local mean in Git? 
R: remote = remote repository. Stuff that's on your hard drive is local. Stuff that's on GitHub's server is remote. origin = the default name of the remote repository on GitHub corresponding to the repo you're currently in on your machine. master = the default name of the initial branch of a repository.


### DevOps

#### Why is it good to use a package manager software?
R: A package manager is a programming language's tool to create project environments and easily import external dependencies. ... You can usually specify dependencies, a package name, author, tags/keywords and version number. All this helps online repositories store your package and allows others to find your project.

#### Why is it good to use a virtual environment for a project?
A virtual environment is a tool that helps to keep dependencies required by different projects separate by creating isolated python virtual environments for them. This is one of the most important tools that most of the Python developers use.


### Networks

#### What kind of HTTP status codes do you know?
R: Informational responses ( 100 – 199 )
Successful responses ( 200 – 299 )
Redirection messages ( 300 – 399 )
Client error responses ( 400 – 499 )
Server error responses ( 500 – 599 )

#### What is a API?
R: API is the acronym for Application Programming Interface, which is a software intermediary that allows two applications to talk to each other.

#### What is REST API?
R: A REST API (also known as RESTful API) is an application programming interface (API or web API) that conforms to the constraints of REST architectural style and allows for interaction with RESTful web services. REST stands for representational state transfer and was created by computer scientist Roy Fielding.

#### What is JSON? When to use?
R: JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax. It is commonly used for transmitting data in web applications (e.g., sending some data from the server to the client, so it can be displayed on a web page, or vice versa).

#### What is TCP/IP? What layers does it define, what are they responsible for?
R: TCP/IP stands for Transmission Control Protocol/Internet Protocol and is a suite of communication protocols used to interconnect network devices on the internet. ... The TCP/IP protocol suite functions as an abstraction layer between internet applications and the routing and switching fabric.

#### What’s the difference between TCP and UDP?
R: TCP is a connection-oriented protocol, whereas UDP is a connectionless protocol. A key difference between TCP and UDP is speed, as TCP is comparatively slower than UDP. Overall, UDP is a much faster, simpler, and efficient protocol, however, retransmission of lost data packets is only possible with TCP.

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
R: `GET /search?q=test HTTP/2
Host: www.bing.com
User-Agent: curl/7.54.0
Accept: */*`
All of them are relevant for their purpose. There is no such thing as a field is more relevant than the other.

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
R: `HTTP/1.1 404 Not Found
Date: Sun, 18 Oct 2012 10:36:20 GMT
Server: Apache/2.2.14 (Win32)
Content-Length: 230
Connection: Closed
Content-Type: text/html; charset=iso-8859-1`


#### What is DNS? How does it work?
R: D. N. S. (Domain Name System) The Internet's system for converting alphabetic names into numeric IP addresses. For example, when a Web address (URL) is typed into a browser, DNS servers return the IP address of the Web server associated with that name.

#### What is a web server?
R:  A web server is a computer that runs websites. It's a computer program that distributes web pages as they are requisitioned. The basic objective of the web server is to store, process and deliver web pages to the users. This intercommunication is done using Hypertext Transfer Protocol (HTTP).

#### Explain the client-server architecture.
R: Client Server Architecture is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client. This type of architecture has one or more client computers connected to a central server over a network or internet connection.

#### What would you use a session for?
R: Basic usage ¶ Sessions are a simple way to store data for individual users against a unique session ID. This can be used to persist state information between page requests. Session IDs are normally sent to the browser via session cookies and the ID is used to retrieve existing session data.

#### What would you use a cookie for?
R: Cookies can be used by web servers to identity and track users as they navigate different pages on a website, and to identify users returning to a website. Cookies may be either "persistent" cookies or "session" cookies.


## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
R:
Agile development methodology. (individuals and interactions over processes and tools; working software over comprehensive documentation; customer collaboration over contract negotiation; and. responding to change over following a plan)

DevOps deployment methodology. (DevOps is a methodology meant to improve work throughout the software development lifecycle. You can visualize a DevOps process as an infinite loop, comprising these steps: plan, code, build, test, release, deploy, operate, monitor and -- through feedback -- plan, which resets the loop.)

Waterfall development method. (The Waterfall methodology—also known as the Waterfall model—is a sequential development process that flows like a waterfall through all phases of a project (analysis, design, development, and testing, for example), with each phase completely wrapping up before the next phase begins.)

Rapid application development. (Rapid application development is an agile software development approach that focuses more on ongoing software projects and user feedback and less on following a strict plan. As such, it emphasizes rapid prototyping over costly planning)


#### What are the SCRUM roles?
R: Scrum has three roles: product owner, scrum master and the development team members. While this is pretty clear, what to do with existing job titles can get confusing. Many teams ask if they need to change their titles when adopting scrum.

#### What are the SCRUM ceremonies?
R: Scrum defines four events (sometimes called ceremonies) that occur inside each sprint: sprint planning, daily scrum, sprint review, and sprint retrospective.

#### What are the SCRUM artifacts?
R: The main agile scrum artifacts are product backlog, sprint backlog, and increments. ... Yet in software development, the term artifact refers to key information needed during the development of a product.

#### What is the main goal of a retrospective meeting?
R: A Retrospective is a ceremony held at the end of each iteration in an agile project. The general purpose is to allow the team, as a group, to evaluate its past working cycle. In addition, it's an important moment to gather feedback on what went well and what did not.

#### Explain, when would you recommend to use the waterfall methodology?
R: There are no ambiguous requirements (no confusion). It is good to use this model when the technology is well understood. The project is short and cast is low. Risk is zero or minimum.

