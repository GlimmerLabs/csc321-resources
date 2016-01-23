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

**If - modifier**
```
...something... if condition

```
Example:
```
2.2.1 :004 > class_in_session  = true
 => true 
2.2.1 :005 > puts "CSC 321 is the best class ever" if class_in_session
CSC 321 is the best class ever
 => nil 
 
 2.2.1 :006 > class_in_session  = false
 => false 
2.2.1 :007 > puts "CSC 321 is the best class ever" if class_in_session
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
More on methods & classes
-------------------
**Default method arguments**

Methods can take in default argument for cases where the value of some argument was not specified:
Example
```
def greet(name="CSC 151 student")
    puts "Hello " + name
end

2.2.1 :011 > greet
Hello CSC 151 student
 => nil 
2.2.1 :012 > greet("Sam")
Hello Sam
 => nil 
```
**Attribute Accessors**

Ruby has a special functionality that helps in the creation of getters and setters for instance or class variables.

|Accessor Type| Description|
|----------| --------------|
|attr_reader | End users of this class have "read only" access to the variable |
|attr_writer            | End users of this class have "write only" access to the variable |
|attr_accessor | End users are able to both read and write to the variable|

Example (attr_reader):
```
class Student
    attr_reader :name
     def initialize
         @name = "Albert"
     end
end

2.2.1 :041 > student_321 = Student.new
 => #<Student:0x00000001c106a0 @name="Some Default Student"> 
2.2.1 :042 > student_321.name
 => "Some Default Student" 
 
 2.2.1 :043 > student_321.name = "Sam"
NoMethodError: undefined method `name=' for #<Student:0x00000001c106a0 @name="Some Default Student">
        from (irb):43
        from /usr/local/rvm/rubies/ruby-2.2.1/bin/irb:11:in `<main>'
        
```
Example (attr_writer):
```
class Student
    attr_writer :name
     def initialize
         @name = "Some Default Student"
     end
end

2.2.1 :051 > student_321 = Student.new
 => #<Student:0x00000001b5b1b0 @name="Some Default Student"> 
2.2.1 :052 > student_321.name = "Sam"
 => "Sam" 
 
 2.2.1 :009 >   student_321 = Student.new
 => #<Student:0x000000020bb380 @name="Some Default Student"> 
2.2.1 :010 > student_321.name
NoMethodError: undefined method `name' for #<Student:0x000000020bb380 @name="Some Default Student">
        from (irb):10
        from /usr/local/rvm/rubies/ruby-2.2.1/bin/irb:11:in `<main>'
```
Example (attr_accessor):
```
class Student
   
    attr_accessor :name
     def initialize
         @name = "Some Default Student"
     end
end

2.2.1 :021 >   student_321 = Student.new
 => #<Student:0x00000001ffe708 @name="Some Default Student"> 
2.2.1 :022 > student_321.name
 => "Some Default Student" 
2.2.1 :023 > student_321.name ="Sam"
 => "Sam" 
```
**Inheritance**

Example
```
class Parent
    def display
        puts "Parent display"
    end
end

class Child < Parent
end

2.2.1 :035 >   parent = Parent.new
 => #<Parent:0x00000001f0be90> 
2.2.1 :036 > parent.display
Parent display
 => nil 
2.2.1 :037 > 
2.2.1 :038 >   child = Child.new
 => #<Child:0x00000001ef76e8> 
2.2.1 :039 > child.display
Parent display
 => nil 
```

Ruby Conventions
-----------------
For conventions accepted by the ruby community visit any of the links below:
+ [https://github.com/styleguide/ruby](https://github.com/styleguide/ruby)
+ [https://github.com/airbnb/ruby] (https://github.com/airbnb/ruby)

Again a quick google search for ruby conventions should yield various useful results

