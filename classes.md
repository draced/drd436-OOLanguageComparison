# Classes
## C++
* Supports classes, structs (passive data structure (PDS) types), and unions, and can allocate them on the heap or the stack.
* Classes are an added feature to C, so you can still write programs that work entirely without using a class. 
* Whenever an object of a class is created its constructor is called, and its parent class constructor is called, as are the constructors for all objects that belong to the class.
* Example:
~~~~
#include <iostream>
class Foo
{
        public:
        Foo() { std::cout << "Foo's constructor" << std::endl; }
};
class Bar : public Foo
{
        public:
        Bar() { std::cout << "Bar's constructor" << std::endl; }
};

int main()
{
        Bar bar;
}
~~~~
* The object bar is constructed in two stages: first, the Foo constructor is invoked and then the Bar constructor is invoked. The output of the above program will be to indicate that Foo's constructor is called first, followed by Bar's constructor. 
* The initialization list also lets you specify which constructor gets called for the objects that are fields of the class.
## Java
* Classes are allocated on the heap. Java SE 6 optimizes with escape analysis to allocate some objects on the stack.
* All objects are descendants of a common class (Object).
* All code in Java must reside within classes and interfaces. Each class is compiled into a separate .class file, which can be executed by a JVM on any machine which can support a JVM, achieving platform independence.
* Java makes you declare every member's accessibility separately.
* Java allows you to perform initialization in a variety of ways:
~~~~
public class Test {
  static String staticName = getStaticName();
 
  /* This is a static initialization block */
  static {
    System.out.println("In static initializer block");
  }
 
  static String getStaticName() {
    System.out.println("In getStaticName");
    return "<Hero>";
  }
 
  String name = getName();
 
  /* This is an initialization block */
  {
    System.out.println("In initializer block");
  }
 
  String getName() {
    System.out.println("In getName");
    return "Batman";
  }
 
  public static void main(String[] args) {
    System.out.println(new Test().name);
    System.out.println(new Test().name);
  }
}
~~~~
* Static initialization happens when a class is loaded by the JVM for the first time. Everything else is executed before the constructor of the object is called. So the code prints out the following:
~~~~
In getStaticName
In static initializer block
In getName
In initializer block
In Test()
In getName
In initializer block
In Test()
~~~~
