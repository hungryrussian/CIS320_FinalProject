# CIS320_FinalProject
CIS320 Python Programming Final Project

Final Project Proposal
Overview Statement
The problem addressed by this project will be to digitize the daily operations of a restaurant or foodservice small business.  In the hospitality industry, computers are still scarcely adopted.  This is largely due to budget constraints where there is a fine line between breaking even and losing money.  However, the benefits gained by implementing a digital line-of-business (LOB) application such as the one proposed in this project will increase productivity of both management and employees and ultimately decrease operating costs.
The application proposed by this project will be a simple LOB program to computerize the three main areas of foodservice:
➢	Inventory management
➢	Personnel scheduling and HR
➢	Point of Sale (POS)
This proposed application will computerize the basic functions in each of the above three departments.  This will streamline the daily administrative operations and lower operating costs.
The application is designed to be lightweight and operate smoothly on older PCs.  It will be text-based and menu driven.  By limiting the system requirements for the application, it will enable businesses to reuse existing hardware or purchase inexpensive computers to run the software.
Scope / Specifications
The proposed application will be menu driven and accessible through the keyboard.  Mouse integration and GUI programming is beyond the scope of this project.  A GUI frontend may be attempted if the project is completed and time permitting.
The program will consist of three individual modules:
➢	The “Inventory” module,
➢	The “Personnel” module, and
➢	The “Point of Sale” module.
When first launching the application, the user will be prompted to enter their employee number.  This will act as a rudimentary permissions control that will grant or deny access to each module depending on the employee.  There will be two levels of users: Manager and Employee.  Managers will have access to all modules of the program.  Employees will only be able to access the Inventory and POS modules.
The Inventory module will manage daily operations pertaining to inventory, stock, and management thereof.  It will allow all users to list all or some items in the inventory, check if they are in stock, receive items and update the stock count, decrement the stock count, and add/remove items from the inventory list.  Every input from the user while in this module (for stock updates, item additions) will be validated to ensure the correct data type is entered.  An error and retry will be thrown if the user attempts to input the wrong data type (i.e., a word into an inventory count).  An Inventory class will be created and each inventory item will be stored as an Inventory object.
The Personnel module will handle scheduling for employees.  Only users with the “Manager” delegation will be able to access this module.  In this menu, there will be options to add or deactivate employees from the system, list some or all employees, and view or update the schedule.  Each input from the user will be validated to ensure they have entered the correct data type.  Incorrect entries will have an error thrown and the input attempt retried.  There will be a generic Employee class created that will provide the basic functionality for this module.  A child class of Manager will add additional attributes to the Employee class.
The POS module will record sales at the front-of-house (FOH).  All users will have access to this module.  In this menu, there will be options to create a new sale or recall a previous sale.  The sale itself will be defined as a class object and passed to a modifySale() function to perform the following options:
1)	Add line item
2)	Delete line item
3)	Discount line item
4)	Finalize sale
5)	Void sale
Each sale will be indexed and saved to allow for future reference and export to reporting or finance software.
Data persistence for the application will be handled by writing the data entered in the program to file.  Depending on the capabilities of Python 3 and the information covered in class, the program will either store the data written to a file or use a SQLite database, or both.  There are many tutorials online for using Python 3 with a SQLite database and the syntax is not too difficult to learn in addition to the class.  The data storage method with the most efficient and effective implementation will be used in the program.
Approach
This program will be created through a top-down approach.  We have defined the big picture of the project and will break down each step into sub-components until there are no further subprocesses.  By designing a module and menu-based application, the top-down approach makes logical sense.  Each module is already defined and can be dissected down to individual functions that need to be written.  The application flowchart is easy to create because it closely mirrors the flow of each menu.  Each team member will be assigned predefined functions to code to spec and the program will be assembled from these functions.
Libraries of Interest
The following libraries might be used in the program.  The pros and cons of each library are discussed as well as the usage within the application.
1.	Datetime
https://docs.python.org/3/library/datetime.html
The datetime library will be used in the POS module to take the date and time of a sale.  It is conceivable that the program will use a condensed date and timestamp as the unique key for each sale (2017.04.19.11.49.32.128).  Because the target market is the small business with only a handful of terminals, it is essentially statistically impossible to create a duplicate record using this method of indexing.
2.	Sqlite3
https://docs.python.org/3/library/sqlite3.html
This library allows access to a SQLite database file from the Python 3 application.  From the program, SQL queries can be called and executed against the database.  This is a viable alternative to dumping data to dumb files from Python.  A relational database is predisposed to organizing data in a logical manner.  It will be the most efficient method to store the application data.  However, we will not be learning this library in class and it will require additional extracurricular work on a tight schedule to learn and implement.

