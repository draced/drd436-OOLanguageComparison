# Multithreading
## C++
* Built in support for multithreading was introduced in C++11. Header file thread.h provides functionality for creating multithreaded C++ programs.
* Example that creates and runs a thread:
~~~~
#include <iostream>
#include <thread> 
using namespace std;
void threadFunc()
{
	cout << "Welcome to Multithreading" << endl;

}
int main()
{
	//pass a function to thread
	thread funcTest1(threadFunc);
}
~~~~
## Java
* Classes can be executed as a thread by implementing a `Runnable` interface.
* Example that creates a new thread and starts running it:
~~~~
class RunnableDemo implements Runnable {
   private Thread t;
   private String threadName;
   
   RunnableDemo( String name) {
      threadName = name;
      System.out.println("Creating " +  threadName );
   }
   
   public void run() {
      System.out.println("Running " +  threadName );
      try {
         for(int i = 4; i > 0; i--) {
            System.out.println("Thread: " + threadName + ", " + i);
            // Let the thread sleep for a while.
            Thread.sleep(50);
         }
      }catch (InterruptedException e) {
         System.out.println("Thread " +  threadName + " interrupted.");
      }
      System.out.println("Thread " +  threadName + " exiting.");
   }
   
   public void start () {
      System.out.println("Starting " +  threadName );
      if (t == null) {
         t = new Thread (this, threadName);
         t.start ();
      }
   }
}

public class TestThread {

   public static void main(String args[]) {
      RunnableDemo R1 = new RunnableDemo( "Thread-1");
      R1.start();
      
      RunnableDemo R2 = new RunnableDemo( "Thread-2");
      R2.start();
   }   
}
~~~~
