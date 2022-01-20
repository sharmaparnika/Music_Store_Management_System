# Music Store Management System

Music Library Management System have to manage various musical items comes with number of models and variety. Maintaining all musical records such as create order, calculate bill, add new music in database, edit the music description, and delete any item from large music library was not an easy task on regular basis.

This is a music store manager program in C++ with mysql database that can create order, calculate bill, add new music in database, edit the music description, and delete any item also it shows the total music in stock, and it can find the specific music. it stores all data in MySQL database.

### Features:
The program can create order, find music, sold items, item in stock, all items, add new Item, remove Item.

1. Create Order

      Here the user can create an order, choose items, delete items and buy the item and finally show the price of total items. The user can also choose same item.

2. Find Music

      User can find their song with four different categories Name, Category, Type, and Artist.

3. Sold Items
  
      It shows how many item and which items were sold.

4. Item in Stock

      It shows the item that is in the stock that means the quantity of the item is more then zero.

5. All Items

      Shows all the items in the database.

6. Add New Item

      Add new item in the database.

7. Edit Item

      Edit any item content.

8. Remove Item

      Can delete any item from database.

9. Exit

      Exit the program.
      
      
### Music Store Manager Program Details:

In the beginning of the program Global variables, Class db_response, Function main.

![image](https://user-images.githubusercontent.com/73773202/150319417-a61c6f09-551d-4b21-beef-f6cd284cf2cc.png)


### Global variables used in this Music Store Manager Program:

* qstate represent the state of the query. If 0 is successful 1 is failed.
* conn is the mysql connection variable.
* row is for getting the current row of the database.
* res is for getting all the values form the database.

### Class db_response

* This class contains connection of the database.
* mysql_init is the initializer of mysql_real_connect
* mysql_real_connect connects to the database. (MySql server should open while connecting)
* the if statement shows the successful or failed connection.

![image](https://user-images.githubusercontent.com/73773202/150319697-6cabc456-2d52-4571-9009-fa0e377a46a8.png)


### Function main:

* Here firstly the clear screen command then the title command and the color command.
* db_response::ConnectionFunction() is create the connection to the database.
* The program features
    *  Create Order.
    *  Find Music.
    *  Sold Items.
    *  Item in Stock.
    *  All Items.
    *  Add New Item.
    *  Edit Item.
    *  Remove Item.

![image](https://user-images.githubusercontent.com/73773202/150319939-3777c40b-8532-4660-8696-95c17c43ad91.png)


* The switch case is used for switching between this functions
    *  AddNewItemInDatabase();
    *  ShowAllItems();
    *  ItemInStock();
    *  FindMusic();
    *  EditItem();
    *  RemoveItem();
    *  CreateOrder();
    *  SoldItems();


* Function AddNewItemInDatabase()
    *  Add new item in the database.
    *  Firstly gets the input of Category, Type, Name, Artist, Price, Quantity from the database
    *  stringstream function can copy the non-string variable to a string variable.
    *  The insert query stored in the insert_query variable
    *  c_str() converts the string to constant character the mysql_query function can only deals with the constant character.
    *  qstate gets the state of the query
Finally the Exit Code terminates the program or go to main function or repeat the same function.

![image](https://user-images.githubusercontent.com/73773202/150320622-adc3dd5d-61aa-45b9-928c-c30ccd5964c5.png)

* Function ShowAllItems()
    *  Shows all the item in the database.
    *  Assign result in qstate
    *  Finally show the result in the console of all rows in the database
    *  Lastly, Exit Code run for go to main function or exit.
   
 * Function ItemInStock()
    *  Show all the item in stock
    *  This is same as ShowAllItems() function but this only show that items quantity is more than zero.
    *  Lastly, Exit Code run for go to main function or exit.
* Function FindMusic()
    *  Find items from database
    *  Four ways to find items Name, Type, Artist, Category
    *  From the choose of one item from the list the user can search that particular item
    *  The program is smart so if the user type one word then it can find the result with that word.
    *  Finally the Exit Code terminates the program or go to main function or repeat the same function.

![image](https://user-images.githubusercontent.com/73773202/150320928-b3bab896-b5c6-4a86-945d-80f8db41ba56.png)


* Function EditItem()
    *  User can edit any item.
    *  Firstly all the items name and ids are displayed in the console.
    *  Than the user can choose only one item and can edit the item.
    *  The user can change the item property or remain the item property same.
    *  Finally the Exit Code terminates the program or go to main function or repeat the same function.

![image](https://user-images.githubusercontent.com/73773202/150321041-06f79e39-5e76-4c5e-ae12-8985e2f0abaa.png)


* Function RemoveItem()
    *  Delete item from database
    *  Firstly shows all the items Name and Id in the database with mysql query
    *  Then it check the number is valid or not if not than show a message
    *  If the number is valid than the program execute the mysql delete query and delete that item from the database and show a message.
    *  Finally the Exit Code terminates the program or go to main function or repeat the same function.

![image](https://user-images.githubusercontent.com/73773202/150321317-5d6d3149-b7a7-43a9-b3a3-bd76b8902a6a.png)


* Function CreateOrder()
    *  User can create an order.
    *  Firstly the mysql query select all the items from the database and display in the console if the item quantity is more than zero.
    *  It also store the items in an array.
    *  Now the user can type the ID of the song.
    *  The user can type same id of the song.
    *  It also checks the id validity.
    *  Now the program shows the list of the items
    *  After that the program can edit the list item by removing items from the list or buy the items.
    *  When the program goes to buy function then two loops are execute.
    *  There is a ‘If’ statement, that check is the given value is matching with the id of songs.
    *  Then a mysql query is get the current quantity of the item in the database.
    *  totalprice add the price of the items which are bought by the user.
    *  Then the quantity calculation, in every purchase the quantity reduce of the respective item.
    *  The update mysql query update the last calculated item quantity in the database.
    *  Finally the result message and the total price pops up in the console.
    *  Then the Exit Code executes.

![image](https://user-images.githubusercontent.com/73773202/150321531-5ce2cf4f-60fa-4955-934c-e0d8efee6f7f.png)
 
* Function SoldItems()
    *  The sold item shows the item all the items that sold and how many of them are sold with its all property.
    *  Then the Exit Code runs.

### Details for MySQL Database used in this Music Store Manager Program
Database and Table Name:

* Table: musicinfo_tb, solditem_tb
* Database: cpp_musicstore_db
* Usage: XAMPP Server, MySql Headers, MySql Libs

![image](https://user-images.githubusercontent.com/73773202/150322528-3d3102b9-fcd1-4772-b080-bbc3217144c5.png)


---
