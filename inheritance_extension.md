# Inheritance
## C++
* There is forest of classes; when we create a class that doesn’t inherit from anything, we create a new tree in forest.
* Access specifier can be public, protected and private. The default access specifier is private. Access specifiers affect accessibility of data members of base class from the derived class. In addition, it determines the accessibility of data members of base class outside the derived class.
* Multiple inheritance is supported. Example:
~~~~
class A
{
	int m_iA;
	A(int iA) :m_iA(iA)
	{
	}
};

class B
{
	int m_iB;
	B(int iB) :m_iB(iB)
	{
	}
};

class C
{
	int m_iC;
	C(int iC) :m_iC(iC)
	{
	}
};
~~~~
* You can create a new class that will inherit all the properties of all these classes:
~~~~
class ABC :public A, public B, public C
{
	int m_iABC;
	//here you can access m_iA, m_iB, m_iC 
};
~~~~
* Multilevel inheritance is possible. Multilevel inheritance represents a type of inheritance when a Derived class is a base class for another class. In other words, deriving a class from a derived class is known as multi-level inheritance. 
* Hierarchical inheritance is possible which allows you to to create multiple Derived classes that inherit properties of the same Base class.
## Java
* All classes inherit from the Object class directly or indirectly. Therefore, there is always a single inheritance tree of classes in Java, and Object class is root of the tree. If we create a class that doesn’t inherit from any class then it automatically inherits from Object class.
* Members of the grandparent class are not directly accessible.
* Protected members of a class “A” are accessible in other class “B” of same package, even if B doesn’t inherit from A (they both have to be in the same package). For example, in the following program, protected members of A are accessible in B.
~~~~
class A {
    protected int x = 10, y = 20;
}
  
class B {
    public static void main(String args[]) {
        A a = new A();
        System.out.println(a.x + " " + a.y);
    }
}
~~~~
* Java uses extends keyword for inheritence.
* Cannot change the protection level of members of base class in Java, if some data member is public or protected in base class then it remains public or protected in derived class.
* Does not support multiple inheritance. A class cannot inherit from more than one class. A class can implement multiple interfaces though.
