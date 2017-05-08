# Singleton
## C++
* Can be lazy and thread-safe.
* Example of lazy evaluated and correctly destroyed singleton.
~~~~
class S
{
    public:
        static S& getInstance()
        {
            static S    instance; // Guaranteed to be destroyed.
                                  // Instantiated on first use.
            return instance;
        }
    private:
        S() {}                    // Constructor? (the {} brackets) are needed here.

        // C++ 03
        // ========
        // Dont forget to declare these two. You want to make sure they
        // are unacceptable otherwise you may accidentally get copies of
        // your singleton appearing.
        S(S const&);              // Don't Implement
        void operator=(S const&); // Don't implement

        // C++ 11
        // =======
        // We can use the better technique of deleting the methods
        // we don't want.
    public:
        S(S const&)               = delete;
        void operator=(S const&)  = delete;

        // Note: Scott Meyers mentions in his Effective Modern
        //       C++ book, that deleted functions should generally
        //       be public as it results in better error messages
        //       due to the compilers behavior to check accessibility
        //       before deleted status
};
~~~~
## Java
* We can make constructor as private. So that We can not create an object outside of the class.
* Singleton pattern helps us to keep only one instance of a class at any time.
* Can be made lazy and thread-safe.
* Example of a singleton in Java:
~~~~
package com.myjava.constructors;
 
public class MySingleTon {
     
    private static MySingleTon myObj;
    /**
     * Create private constructor
     */
    private MySingleTon(){
         
    }
    /**
     * Create a static method to get instance.
     */
    public static MySingleTon getInstance(){
        if(myObj == null){
            myObj = new MySingleTon();
        }
        return myObj;
    }
     
    public void getSomeThing(){
        // do something here
        System.out.println("I am here....");
    }
     
    public static void main(String a[]){
        MySingleTon st = MySingleTon.getInstance();
        st.getSomeThing();
    }
}
~~~~
