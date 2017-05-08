# Types
* Both C++ and Java are strongly-typed languages with similar typing. There are a few notable differences.
## C++
* Standardized minimum limits for all numerical types, but the actual sizes are implementation-defined. Standardized types are available via the standard library <cstdint>.
* Provides object types and type names. Allows reflection via run-time type information (RTTI).
* Pointers, references, and pass-by-value are supported for all types (primitive or user-defined).
* Allows explicitly overriding types, and some implicit narrowing conversions (for compatibility with C).
## Java
* 	Standardized limits and sizes of all primitive types on all platforms.
* 	All types (primitive types and reference types) are always passed by value.'
* Generics are used to achieve basic type-parametrization, but they do not translate from source code to byte code due to the use of type erasure by the compiler.
* `final` provides a version of `const`, equivalent to `type* const` pointers for objects and const for primitive types. Immutability of object members achieved via read-only interfaces and object encapsulation.
