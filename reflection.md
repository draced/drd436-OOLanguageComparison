# Reflection
## C++
* The most common way to access reflection features is through the GetType method. This method is provided by System::Object, from which all garbage-collected classes derive.
* The GetType method returns a pointer to a Type class object, which describes the type upon when the object is based. (The Type object does not contain any instance-specific information.)
* Example:
~~~~
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
~~~~
* Will generate this output:
~~~~
full type name of 'sample string' is 'System.String'  
~~~~
## Java
* All objects in Java have the method getClass(), which lets you determine the object's class even if you don't know it at compile time.
* Example:
~~~~
Method method = foo.getClass().getMethod("doSomething", null);
method.invoke(foo, null);
~~~~
