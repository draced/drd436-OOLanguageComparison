# Implementation of listeners and event handlers
## C++
* In native C++ event handling, you set up an event source and event receiver using the `event_source` and `event_receiver` attributes, respectively, specifying `type=native`. These attributes allow the classes to which they are applied to fire events and handle events in a native, non-COM context.
* In an event source class, use the `__event` keyword on a method declaration to declare the method as an event.
* In an event receiver class, you define event handlers, which are methods with signatures (return types, calling conventions, and arguments) that match the event that they will handle.
* Also in an event receiver class, you use the intrinsic function `__hook` to associate events with event handlers and `__unhook` to dissociate events from event handlers. You can hook several events to an event handler, or several event handlers to an event.
* To fire an event, simply call the method declared as an event in the event source class. If handlers have been hooked to the event, the handlers will be called.
* Example of an event handler:
~~~~
#include <stdio.h>  
  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
  
[event_receiver(native)]  
class CReceiver {  
public:  
   void MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
   }  
  
   void MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
   }  
  
   void hookEvent(CSource* pSource) {  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void unhookEvent(CSource* pSource) {  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   CSource source;  
   CReceiver receiver;  
  
   receiver.hookEvent(&source);  
   __raise source.MyEvent(123);  
   receiver.unhookEvent(&source);  
}
~~~~
* Will generate this output:
~~~~
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123. 
~~~~
## Java
* The `java.awt.event` package provides many event classes and Listener interfaces for event handling.
* Must first register the component with the Listener. Example:
~~~~
public void addActionListener(ActionListener a){}
~~~~
* Example of event handling with ActionListener:
~~~~
import java.awt.*;  
import java.awt.event.*;  
class AEvent extends Frame implements ActionListener{  
TextField tf;  
AEvent(){  
  
//create components  
tf=new TextField();  
tf.setBounds(60,50,170,20);  
Button b=new Button("click me");  
b.setBounds(100,120,80,30);  
  
//register listener  
b.addActionListener(this);//passing current instance  
  
//add components and set size, layout and visibility  
add(b);add(tf);  
setSize(300,300);  
setLayout(null);  
setVisible(true);  
}  
public void actionPerformed(ActionEvent e){  
tf.setText("Welcome");  
}  
public static void main(String args[]){  
new AEvent();  
}  
}  
~~~~
