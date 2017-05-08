# Properties
* Getters and setters are created manually in both C++ and Java.
* No specific tools for backing variables in both C++ and Java.
* Here is a few notable properties of the languages:
## C++
* Optional automated bounds checking (e.g., the at() method in vector and string containers).
* Native unsigned arithmetic support.
* The C++ Standard Library was designed to have a limited scope and functions, but includes language support, diagnostics, general utilities, strings, locales, containers, algorithms, iterators, numerics, input/output, random number generators, regular expression parsing, threading facilities, type traits (for static type introspection) and Standard C Library. The Boost library offers more functions including network I/O.
## Java
* All operations are required to be bound-checked by all compliant distributions of Java. HotSpot can remove bounds checking.
* Native unsigned arithmetic unsupported. Java 8 changes some of this, but aspects are unclear.
* The standard library has grown with each release. By version 1.6, the library included support for locales, logging, containers and iterators, algorithms, GUI programming (but not using the system GUI), graphics, multi-threading, networking, platform security, introspection, dynamic class loading, blocking and non-blocking I/O. It provided interfaces or support classes for XML, XSLT, MIDI, database connectivity, naming services (e.g. LDAP), cryptography, security services (e.g. Kerberos), print services, and web services. SWT offered an abstraction for platform-specific GUIs, but was superseded by JavaFX in the latest releases ; allowing for graphics acceleration and CSS-themable UIs. It although doesn't support any kind of "native platform look" support.
* Extensive Javadoc documentation standard on all system classes and methods.
