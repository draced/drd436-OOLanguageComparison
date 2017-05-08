# Errors and exception handling
## C++
* All types (including primitive and pointer) can be thrown as exception.
* Example of an exception:
~~~~
#include <iostream>
using namespace std;
int main() 
{
   int x = -1; 
 
   // some other stuff   
   try {
      // some other stuff 
      if( x < 0 )
      {
         throw x;
      }   
   }
   catch (int x ) {
      cout << "Exception occurred: thrown value is " << x << endl;
   }
   getchar();
   return 0;
}
~~~~
* Output:
~~~~
Exception occurred: thrown value is -1
~~~~
* There is a special catch called “catch all” that can catch all kind of exceptions.
* All exceptions are unchecked.
## Java
* Only throwable objects (Throwable objects are instances of any subclass of the Throwable class) can be thrown as exception.
* Can catch Exception object to catch all kind of exceptions. Because, normally we do not catch Throwable(s) other than Exception(s) (which are Errors). Example:
~~~~
catch(Exception e){
  …….
}
~~~~
* There is a block called finally that is always executed after the try-catch block. Example:
~~~~
// creating an exception type
class Test extends Exception { }
 
class Main {
   public static void main(String args[]) {
 
      try {
         throw new Test();
      }
      catch(Test t) {
         System.out.println("Got the Test Exception");
      }
      finally {
         System.out.println("Inside finally block ");
      }
  }
}
~~~~
* There are two types of exceptions – checked and unchecked.
* A new keyword throws is used to list exceptions that can be thrown by a function.
