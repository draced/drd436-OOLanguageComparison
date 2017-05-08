# Namespaces
## Namespaces in C++:
* In C++ a namespace is defined with a namespace block. 
~~~~ 
namespace abc {
 int bar;
}
~~~~
* Within this block, identifiers can be used exactly as they are declared. Outside of this block, the namespace specifier must be prefixed.
* Code that is not explicitly declared within a namespace is considered to be in the global namespace.
* Namespace resolution in C++ is hierarchical. This means that within the hypothetical namespace `food::soup`, the identifier chicken refers to `food::soup::chicken`. If `food::soup::chicken` doesn't exist, it then refers to `food::chicken`. If neither `food::soup::chicken` nor `food::chicken` exist, chicken refers to `::chicken`, an identifier in the global namespace.
* Namespaces in C++ are most often used to avoid naming collisions.

## Namespaces in Java:
*  The idea of a namespace is embodied in Java packages.
*  All code belongs to a package, although that package need not be explicitly named.
* Code from other packages is accessed by prefixing the package name before the appropriate identifier, for example `class String` in package `java.lang` can be referred to as `java.lang.String`.
* Unlike C++, namespaces in Java are not hierarchical as far as the syntax of the language is concerned. However, packages are named in a hierarchical manner.
* Packages express semantic categories of code.
* Function and class scopes can be viewed as implicit namespaces that are inextricably linked with visibility, accessibility, and object lifetime.
