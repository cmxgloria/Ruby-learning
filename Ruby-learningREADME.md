#INTRODUCTION TO RUBY
Ruby is a powerful, flexible programming language you can use in web/Internet development, to process text, to create games, and as part of the popular Ruby on Rails web framework. Ruby is:
High-level,
Interpreted,
Object-oriented
Easy to use.
##Data Types: Numbers, Strings, Booleans
```
my_num = 25    # Add your code here!

my_boolean = true    # And here!

my_string = "Ruby"    # Also here.

puts my_num
puts my_boolean
puts my_string
```
##Variables
my_num = 100
# Write code above this line!

puts my_num
#print: 100
##Math
There are six arithmetic operators we’re going to focus on:
Addition (+)
Subtraction (-)
Multiplication (*)
Division (/)
Exponentiation (**)
Modulo (%)
##'puts' and 'print'
The print command just takes whatever you give it and prints it to the screen. puts (for “put string”) is slightly different: it adds a new (blank) line after the thing you want it to print. You use them like this:
puts "What's up?"
print "Oxnard Montalvo"
No parentheses or semicolons needed!
```
puts "I am learning ruby now."
print "Busy day but meaningful!"
```
##Everything in Ruby is an Object
Because everything in Ruby is an object (more on this later), everything in Ruby has certain built-in abilities called methods. You can think of methods as “skills” that certain objects have. For instance, strings (words or phrases) have built-in methods that can tell you the length of the string, reverse the string, and more.
We also promised to tell you more about the interpreter. The interpreter is the program that takes the code you write and runs it. You type code in the editor, the interpreter reads your code, and it shows you the result of running your code in the console.
##The '.length' Method
The '.length' Method
Methods are summoned using a .. If you have a string, "I love espresso", and take the .length of it, Ruby will return the length of the string (that is, the number of characters—letters, numbers, spaces, and symbols). Check it out: ```rb “I love espresso”.length
==> 15```
(That little line starting with the # isn’t part of what you need to write—it just shows you the output Ruby will provide. More on this in the next section!)
Taking the length of input can be useful if, for example, you want to make a website that takes credit card payments. Ruby can check to make sure the credit card number appears to be valid.
```
my_name="Gloria Chen1 ?"
puts my_name.length
```
#output:14
##The '.reverse' Method
The .reverse method is called the same way .length is, but instead of asking Ruby to tell you how long a string is, it spits out a backwards version of the string you gave it. For instance,
"Eric".reverse
will result in
"cirE"
Reversing input can be useful if you want to sort a list of values from highest to lowest instead of lowest to highest. (We’ll get to sorting in later lessons.)
```
my_name="Gloria Chen"
puts my_name.reverse
```
#nehC airolG
##'.upcase' & '.downcase'
Let’s try one more method (er, two methods). As you might have guessed, the .upcase and .downcasemethods convert a string to ALL UPPER CASE or all lower case, respectively.
```
my_name="Gloria Chen"
puts "Gloria Chen".upcase
puts "Gloria Chen".downcase
```
#output: GLORIA CHEN
#output:gloria chen
##Single-Line Comments
The # sign should come before your comment and affects anything you write after it, so long as you’re on a single line. (We’ll show you how to do multi-line comments in a second.) Check out these examples:
# I'm a full line comment!
"Eric".length # I'm a comment, too!
The second example will return 4, since the comment comes after the code that Ruby will execute.
##Multi-Line Comments
You can write a comment that spans multiple lines by starting each line with a #, but there’s an easier way. If you start with =begin and end with =end, everything between those two expressions will be a comment. Take a look at this example:
```
=begin
I'm a comment!
I don't need any # symbols.
=end
```
Don’t put any space between the = sign and the words begin or end. You can do that with math (2 + 5 is the same as 2+5), but in this case, Ruby will get confused. =begin and =end also need to be on lines all by themselves, just as shown above.
##Naming Conventions
these variables should start with a lowercase letter and words should be separated by underscores, like counter and masterful_method
##Variables & Data Types
my_name= "gloria"
my_age= 18
##Math
```
sum = 13 + 379
product = 923 * 15
quotient = 13209 / 17

puts sum
puts product
puts quotient
```
=begin
392
13845
777
=end
##Strings and String Methods
you call a method by using the . operator, like this: "string".method
```
name = "Gloria Chen"
puts name.reverse
puts name.upcase
puts name.downcase
```
=begin
nehC airolG
GLORIA CHEN	
gloria chen
=end
##Comments
```
#introduce myself
name="my name is gloria"
=begin
name="banyuel school"
rate=1
=end
```
 
 
 
nehC airolG



