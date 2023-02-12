# A Server, Bugs 🪲, and New Things

# Part 1
These screenshots show outputs from the StringServer's method with the path `/add-message?s=<string>`. 

The code for StringServer:

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    String print = "";
    
    public String handleRequest(URI url) {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    print += parameters[1] + "\n";
                    return print;
                }
            }
            return "404 Not Found!";
        }
    }


class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```

Below is the "first" input `http://localhost:4000/add-message?s=-------------`   
![lab - string server first input](https://user-images.githubusercontent.com/120623425/215392668-b22e25c0-fcc1-47d6-b20f-2bc11d7fdaeb.png)
> * The method handleRequest(URI url) is called and it returns a String
> * The relevant argument in the above method is the URI url.  The value in the field of the class is the string that is returned/printed out like the -------------.
> * The string in the field of the class is changed in that it gets longer with more inputs.
  
This screenshot is the "second" input
  
![lab - string server second input](https://user-images.githubusercontent.com/120623425/215395259-10d6adc5-b3cc-472b-ad7b-a645b1b7cd48.png)
> * The same method handleRequest(URI url) is called.  It is the only method for this server.
> * Though the argument for the method is a bunch of numbers and the return is a String, the numbers were "turned" into Strings.
> * For the same reason as in the first screenshot, the String in the field of the class is changed. Another string was concatenated along with a new line. 

# Part 2
(Unrelated to the string server in Part 1)
One of the bugs from Lab 3: the reverseInPlace() in ArrayExamples.java
* ❌ Failure-inducing input of array length 3
```
  #JUnit
  int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);

    input1 = new int[]{ 3, 2, 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1, 2, 3 }, input1);  //here the last element was expected to be [3] but was actually [1]
```

* ✅ Input w/o failure of array length 1
```
  #JUnit
  int[] input1 = { 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);

    input1 = new int[]{ 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1); //passed test
```
* Symptom is the last element is not reversed because there is a mirroring effect and the old value of the first element was not saved. It was overridden.
![both failure and nonfailure inputs - part 2 -lab](https://user-images.githubusercontent.com/120623425/215398360-041f9b72-a296-4321-8838-0d53254051f1.png)

* 🐛 The bug
  **BEFORE**
```
  # 
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1]; //the bug 🐛
    }
  }
```
🐛 The bug
**AFTER**
```
 # static void reverseInPlace(int[] arr) {
    int oldElement = 0;
    for(int i = 0; i < arr.length; i += 1) {
      if(i == 0){
        oldElement = arr[i];
      }
      if(i == arr.length-1){
        arr[i] = oldElement;
      }
      else{
      arr[i] = arr[arr.length - i - 1];
      }
    }
  }
```
This fix addresses the issue of having a temporary variable which saves the old value of the first element so that it will be used as the last element in the reversed array.                                 

# Part 3
From week 2, I learned that I can create my own url with Java.  I always thought that I needed access to a special domain or needed to purchase an actual server, but to learn that I could host my own website on my computer and eventually make it more accessable via a remote server was very cool and eye-opening to learn and do on my own. 
The process is similar to creating a regular Java class with methods and all, of course while implementing a special interface.  
