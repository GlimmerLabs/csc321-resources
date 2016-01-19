#Ruby Resources

Interactive Ruby
----------------
In a terminal you can open an interactive prompt(IRB) that uses the  ruby interpreter.This could be useful for quick testing/experimenting.
Open a terminal window and type `irb`.

```
albertowusuasare:~/workspace $ irb
2.2.1 :001 > 
```
After the interpreter opens you can begin to interact with it. 
```
2.2.1 :001 > "Hello world"
 => "Hello world" 

2.2.1 :002 > ["Sam","Sum","Some"]
 => ["Sam", "Sum", "Some"] 
 
 2.2.1 :003 > family = {'dog' => 'canine', 'cat' => 'feline', 'donkey' => 'asinine'}                                                    
 => {"dog"=>"canine", "cat"=>"feline", "donkey"=>"asinine"} 
```
You can  exit out of IRB, with any of the following commands `exit`, `quit`, `irb_exit`
```
2.2.1 :004 > irb_exit
albertowusuasare:~/workspace $ 
```
There are alternatives to IRB that you can use. A simple google querry will yield various results. A popular online interpreter is [repl.it] (https://repl.it/languages/ruby)

Ruby Types
----------
Below are some of the basic types supported by Ruby:

|Example |Type |
|--------|:---:|
|123     | Integer  |
|9.88    |Float     |
|?c      | Character|
|'string'|String    |
|"string"| Double quoted String|
|:symbol | symbol|
| ["Sum","Some","Sam"] | Array |
|{"dog"=>"canine", "cat"=>"feline", "donkey"=>"asinine"} |Associative array (Hash)|

Basics
--------

**Print statements**
```
2.2.1 :003 > puts "Hello World"
Hello World
 => nil 
 ```
 **Variables**
 ```
local_var = 'This variable lives in a code block'
@instance_var = "I am a variable bound to an instance of a class"
@@class_var = " I am a variable that is in a class"
$global_var = "I am a global  variable and can be accessed everywhere"
CONSTANT = "I am some constant"
 ```
 **Methods**
 ```
 def method_name(parameter)
   ......
 end
 
 def no_param_method
   ...
 end
 ```
 ***Classes***
 ```
 class Greeter
   def greet
     puts "Hello CSC 321 Student"
   end
 end
 ```
 Class instantiation :
 ```
 2.2.1 :017 > gt = Greeter.new
 => #<Greeter:0x000000015a45c8> 
2.2.1 :018 > gt.greet
Hello CSC 321 Student
 => nil 
 ```
Conditionals && Control Structures
-------------------
**If-else**
```
if (condition)
 ... do something...
else
 ... do another thing ...
end
```
Example:
```
def is_class_day?(day)
    if(day == "Monday" || day == "Wednesday" || day == "Friday")
        puts true
    else
        puts false
    end
end

2.2.1 :026 > is_class_day?("Friday")
true
 => nil 
```
**Unless**
```
unless condition 
   ... do something ...
else
   .. do another thing...
end
```
Example:
```
def enough_water?(cups)
    unless (cups >= 8)
        puts false
    else
        puts true
    end
end

2.2.1 :034 > enough_water?(7)
false
 => nil 
```
Ruby Conventions
-----------------
For conventions accepted by the ruby community visit any of the links below:
+ [https://github.com/styleguide/ruby](https://github.com/styleguide/ruby)
+ [https://github.com/airbnb/ruby] (https://github.com/airbnb/ruby)

Again a quick google search for ruby conventions should yield various useful results

