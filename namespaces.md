## Namespaces
* Namespaces in C++:
  * In C++ a namespace is defined with a namespace block. 
~~~~ 
namespace abc {
 int bar;
}
~~~~
  * Within this block, identifiers can be used exactly as they are declared. Outside of this block, the namespace specifier must be prefixed.
  * Code that is not explicitly declared within a namespace is considered to be in the global namespace.
  * Namespace resolution in C++ is hierarchical. This means that within the hypothetical namespace 'food::soup', the identifier chicken refers to 'food::soup::chicken'. If 'food::soup::chicken' doesn't exist, it then refers to 'food::chicken'. If neither 'food::soup::chicken' nor 'food::chicken' exist, chicken refers to '::chicken', an identifier in the global namespace.
  * Namespaces in C++ are most often used to avoid naming collisions.
