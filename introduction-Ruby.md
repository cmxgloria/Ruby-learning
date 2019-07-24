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
puts "I am learning ruby with my laptop"
print " at home!"
// I am learning rubu with my laptop at home! (noted leave space before the first word in print)
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

##new chapter PUTTING THE FORM IN FORMATTER
##What You'll Be Building
read a user’s input and correct his or her capitalization.
```
print "What's your first name? "
first_name = gets.chomp
first_name.capitalize!
 
print "What's your last name? "
last_name = gets.chomp
last_name.capitalize!
 
print "What city are you from? "
city = gets.chomp
city.capitalize!
 
print "What state or province are you from? "
state = gets.chomp
state.upcase!
 
puts "Your name is #{first_name} #{last_name} and you're from #{city}, #{state}!"
//(after you answer all questions, it prints out like this 'Your name is Gloria Chen and you're from Melbourne,VICTORIA!')
```

##Prompting the User
```
print "What's your first name?"
first_name=gets.chomp
first_name.capitalize!
puts first_name
print "What's your last name?"
last_name=gets.chomp
last_name.capitalize!
puts last_name
print "Which city are you from?"
city= gets.chomp
city.capitalize!
puts city
print "Which state are you from?"
state = gets.chomp
state.upcase!
puts state

puts "My name is #{first_name} #{last_name} and I am from #{city},  #{state}."
//it prints automatically each answer with the right format as you see 'put' straight away after each question
```
##Getting Input
```
variable_name= gets.chomp
```
gets is the Ruby method that gets input from the user. When getting input, Ruby automatically adds a blank line (or newline) after each bit of input; chompremoves that extra line. (Your program will work fine without chomp, but you’ll get extra blank lines everywhere.)
```
print "What's your first name?"
first_name=gets.chomp
```
##Repeat for More Input
```
print "What's your first name?"
first_name=gets.chomp
print "What's your last name?"
last_name=gets.chomp
print "Which city are you from?"
city= gets.chomp
print "Which state are you from?"
state = gets.chomp
```
##Printing the Output
```
print "What's your first name?"
first_name=gets.chomp
puts first_name
print "What's your last name?"
last_name=gets.chomp
puts last_name
print "Which city are you from?"
city= gets.chomp
puts city
print "Which state are you from?"
state = gets.chomp
puts state
 
puts "My name is #{first_name} #{last_name} and I am from #{city},  #{state}."
```
=begin
What's your first name?
gloria
What's your last name?
chen
Which city are you from?
melbourne
Which state are you from?
Victoria
My name is gloria chen and I am from melbourne,victoria.
=end
##Formatting with String Methods
```
print "This is my question?"
answer = gets.chomp
answer2 = answer.capitalize 
answer.capitalize!
```
1.It capitalizes the first letter of a string and makes the rest of the letters lower case.We assign the result to answer2
2.the next line might look a little strange, we don’t assign the result of capitalize to a variable. Instead you might notice the ! at the end of capitalize. This modifies the value contained within the variable answer itself. The next time you use the variable answer you will get the results of answer.capitalize
```
print "What's your first name? "
first_name = gets.chomp
first_name.capitalize!
 
print "What's your last name? "
last_name = gets.chomp
last_name.capitalize!
 
print "What city are you from? "
city = gets.chomp
city.capitalize!
 
print "What state or province are you from? "
state = gets.chomp
state.upcase!
 
puts "Your name is #{first_name} #{last_name} and you're from #{city}, #{state}!"
```
=begin
What's your first name?
Gloria
What's your last name?
Chen
Which city are you from?
Melbourne
Which state are you from?
VICTORIA
My name is Gloria Chen and I am from Melbourne,VICTORIA.
=end
 
# NEW CHAPTER CONTROL FLOW IN RUBY
##How It Works
they always produce the same result based on that input; they don’t change their behavior in reaction to the environment (the collection of all variables and their values that exist in the program at a given time).
they always produce the same result based on that input; they don’t change their behavior in reaction to the environment (the collection of all variables and their values that exist in the program at a given time).
Control flow gives us the flexibility we’re looking for. We can select different outcomes depending on information the user types, the result of a computation, or the value returned by another part of the program.
```
print "Integer please: "
user_num = Integer(gets.chomp)

if user_num < 0
  puts "You picked a negative integer!"
elsif user_num > 0
  puts "You picked a positive integer!"
else
  puts "You picked zero!"
end
## Integer please: -6
You picked a negative integer!
```
##Else
```
if 1 > 2
  print "I won't get printed because one is less than two."
else
  print "That means I'll get printed!"
end
##That means I'll get printed
 
 ##Elsif
 ```
 if 10 < 5
  puts "I'm not being printed because 10 is not less than 5!"
elsif 10 == 5
  puts "I won't be printed because 10 does not equal 5!"
else
  puts "10 is greater than 5, so I'm being printed!"
end
## 10 is greater than 5, so I'm being printed!
```

##Unless
```
hungry = false
unless hungry
puts "I'm writing Ruby programs!"
else
puts "Time to eat!"
end
##I'm writing Ruby programs!
```

##Equal or Not?
```
is_true = 2 != 3

is_false = 2 == 3
```

##Less Than or Greater Than
Less than: <
Less than or equal to: <=
Greater than: >
Greater than or equal to: >=
```
test_1 = 17 > 16

test_2 = 21 < 30

test_3 = 9 >= 9

test_4 = -11 < 4
```
##
Practice Makes Perfect
```
# test_1 = 77 != 77
test_1 = false
# test_2 = -4 <= -4
test_2 = true
# test_3 = -44 < -33
test_3 = true
# test_4 = 100 == 1000
test_4 = false
```
##And
Comparators aren’t the only operators available to you in Ruby. You can also use logical or boolean operators. Ruby has three: and (&&), or (||), and not (!). Boolean operators result in boolean values: true or false.

The boolean operator and, &&, only results in true when both expression on either side of && are true. Here’s how && works:

true && true # => true
true && false # => false
false && true # => false
false && false # => false
For example, 1 < 2 && 2 < 3 is true because it’s true that one is less than two and that two is less than three.
```
# boolean_1 = 77 < 78 && 77 < 77
boolean_1 = false

# boolean_2 = true && 100 >= 100
boolean_2 = true

# boolean_3 = 2**3 == 8 && 3**2 == 9
boolean_3 = true
```

##Or
Ruby also has the or operator (||). Ruby’s || is called an inclusive or because it evaluates to true when one or the other or both expressions are true. Check it out:

true || true # => true
true || false # => true
false || true # => true
false || false # => false

##Not
!true # => false
!false # => true
```
# boolean_1 = !true
boolean_1 = false

# boolean_2 = !true && !true
boolean_2 = false

# boolean_3 = !(700 / 10 == 70)
boolean_3 = false
```
Combining Boolean Operators
```
# boolean_1 = (3 < 4 || false) && (false || true)
boolean_1 = true

# boolean_2 = !true && (!true || 100 != 5**2)
boolean_2 =false

# boolean_3 = true || !(true || false)
boolean_3 = true
```

##If, Else, and Elsif
```
a = 10
b = 11
if a < b
  print "a is less than b!"
elsif b < a
  print "b is less than a!"
else
  print "b is equal to a!"
end
##a is less than b!
```

##Unless
```
hungry = false
print "Let us play out." unless hungry
##Let us play out.
```

##Dare to Compare
Now let’s review comparators / relational operators. We’ve turned the tables a bit!

Remember, comparators need to compare two values to each other to result in true or false

10 > 8 # true
8 > 10 # false
8 == 10 # false
8 != 10 # true

##Billions of Booleans
Home stretch! Let’s go over boolean operators.

( 1 == 1 ) && ( 2 == 2 )  # true
( 1 == 2 ) || ( 2 == 2 ) # true
!( false ) # true
With && both comparisons on the left and right must evaluate to true for the entire statement to return true. If the left side does not return true it will not bother trying the right side
With || either the right or left side must evaluate to true. If the left side evaluates to true, the right side will not be tried because it has met the condition of one side being true.
With ! you reverse the result. If you’re false you’re now true. if you’re true you’re now false! Just think of it as opposite day!
```
# test_1 should be true
test_1 = (8==8)&&(-1==-1)

# test_2 = should be true
test_2 = (7>5)||(6>5)

# test_3 = should be false
test_3 = !(true)
```

## THITH MEANTH WAR!
What You'll Be Building

In this project, we’ll combine control flow with a few new Ruby string methods to Daffy Duckify a user’s string, replacing each "s" with "th".

```
print "Thtring, pleathe!: "
user_input = gets.chomp
user_input.downcase!

if user_input.include? "s"
  user_input.gsub!(/s/, "th")
else
  puts "Nothing to do here!"
end
  
puts "Your string is: #{user_input}"
//Thtring, pleathe!: school
Your string is: thchool

```

Getting User Input
```
print "Pleathe enter a thtring: " 
user_input = gets.chomp
```
 
Downcase!
We want to make sure we capture both "S" and "s"

Setting Up the 'If' Branch, Part 1
```
print "Pleathe enter a thtring: " 
user_input = gets.chomp
user_input.downcase!

if user_input.include? "s"
  print "This string has an s."
end
```
#Pleathe enter a thtring: singing
This string has an s.
 
 Setting Up the 'If' Branch, Part 2
 When we find "s", we want Ruby to replace every instance of "s" it finds with "th". We can do this with the .gsub! method, which stands for global substitution.

The syntax looks like this: rb string_to_change.gsub!(/s/, "th")

When we get to later lessons, we’ll explain why the /s/ has to be between slashes instead of between quotes. Note: you cannot put a space between gsub! and the bit in parentheses.


Setting Up the 'Else' Branch

Returning the Final String—Er, "Thtring"
Home stretch—now we want to display the Daffy Duckified string to the user. You can do that using the string interpolation we learned earlier:
```
my_string = "muchachos"
print "Adios, #{my_string}!"
# ==> "Adios, muchachos!"
```

```
print "Pleathe enter a thtring: " 
user_input = gets.chomp
user_input.downcase!

if user_input.include? "s"
  user_input.gsub!(/s/, "th")
else
  puts "There are no 's's in your string."
end

puts "Your new thtring is #{user_input}."
```
#print: Pleathe enter a thtring: sting
Your new thtring is thting.


Congratulationth!
Great work!

How might you improve this project? You could:

Add an additional if statement to re-prompt the user for input if they don’t enter anything
Think about how you might account for words in which the letter “c” sounds like an “s”
Think about how you might preserve the user’s original capitalization
 





