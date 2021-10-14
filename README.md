# InterfaceCode
/*
Challenge for all of you
Try to solve the following question
TOPIC IS — INTERFACE
  A library needs to develop an online application for two types of users/roles, Adults and children.
  Both of these users should be able to register an account.
Any user who is less than 12 years of age will be registered as a child and they can borrow a “Kids” category book for 10 days,
 whereas an adult can borrow “Fiction” category books which need to be returned within 7 days.
Note: In future, more users/roles might be added to the library where similar rules will be enforced.
Develop Interfaces and classes for the categories mentioned above.
1. Create an interface LibraryUser with the following methods declared,
Method Name
registerAccount
requestBook
2. Create 2 classes “KidUsers” and “AdultUser” which implements the LibraryUser interface.
3.  Both the classes should have two instance variables as specified below.
Instance variables  Data type
age int
bookType String
4. The methods in the KidUser class should perform the following logic.
registerAccount function:
if age < 12, a message displaying “You have successfully registered under a Kids Account” should be displayed in the console.
If(age>12), a message displaying, “Sorry, Age must be less than 12 to register as a kid” should be displayed in the console.
requestBook function:
if bookType is “Kids”, a message displaying “Book Issued successfully, please return the book within 10 days” should be displayed in the console.
Else, a message displaying, “Oops, you are allowed to take only kids books” should be displayed in the console.
5. The methods in the AdultUser class should perform the following logic.
registerAccount  function:
if age > 12, a message displaying “You have successfully registered under an Adult Account” should be displayed in the console.
If age<12, a message displaying, “Sorry, Age must be greater than 12 to register as an adult” should be displayed in the console.
requestBook function:
if bookType is “Fiction”, a message displaying “Book Issued successfully, please return the book within 7 days” should be displayed in the console.
Else, a message displaying, “Oops, you are allowed to take only adult Fiction books” should be displayed in the console.
6. Create a class “LibraryInterfaceDemo.java” with a main method which performs the below functions,
Test case #1:
Create an instance of KidUser class.
Set the age as specified in the below table and invoke the registerAccount method  of the  KidUser object
Age
10
18
Set the book Type as specified in the below table and invoke the requestBook method of the KidUser object,
BookType
“Kids”
“Fiction”
Test case #2:
Create an instance of AdultUser class.
Set the age as specified in the below table and invoke the registerAccount method of the AdultUser object
Age
5
23
Set the book Type as specified in the below table and invoke the requestBook method of the  AdultUser  object
BookType
“Kids”
“Fiction”
 */

import java.util.Scanner;

 interface Library {

    public void Account();
    public void Book();
}
 class KidUsers implements Library
{
    int Age;
    String BookType;
    //constructor
    public KidUsers()
    {   Scanner sc = new Scanner(System.in);
        Age =sc.nextInt();
        BookType = sc.next();
    }
public void Account()
   {
       if (Age<12)
       {
           System.out.println("successful register under the kids account");
       }
       else
       {
           System.out.println("age is more than 12");
       }
   }
   public void Book()
   {
       if (BookType.equals("Kids"))
       {
           System.out.println("Book request successfuly completed ");
       }
       else
       {
           System.out.println("not register to Book");
       }
   }
}
class AdultUser implements Library
{
     int Age;
     String BookType;
    //constructor
    public AdultUser()
    {
        Scanner sc = new Scanner(System.in);
        Age = sc.nextInt();
        BookType = sc.next();
    }
    public void Account()
    {
        if(Age>12)
        {
            System.out.println("Successfully register for adults");
        }
        else
        {
            System.out.println("not register");
        }
    }
    public void Book()
    {
        if(BookType.equals("Fiction"))
        {
            System.out.println("Successfully done for book request");
        }
        else
        {
            System.out.println("not done for book request");
        }
    }
}
public class LibraryUser{
    public static void main(String[] args)
    {
       KidUsers obj = new KidUsers();
       obj.Account();
       obj.Book();
       AdultUser obj1 = new AdultUser();
       obj1.Account();;
       obj1.Book();
    }
}
