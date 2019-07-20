# Ruby is a Delight
```
ruby_is_eloquent = true
ruby_is_ugly = false

puts "Ruby is eloquent!" if ruby_is_eloquent
puts "Ruby's not ugly!" unless ruby_is_ugly
```
#Ruby is eloquent!
Ruby's not ugly!

A Simpler 'If'

The One-Line Unless

One Good Turn Deserves a Ternary
An even more concise version of if/else is the ternary conditional expression. It’s called “ternary” because it takes three arguments: a boolean, an expression to evaluate if the boolean is true, and an expression to evaluate if the boolean is false.

The syntax looks like this:
```
boolean ? Do this if true: Do this if false
```
An example might be

```
puts 3 < 4 ? "3 is less than 4!" : "3 is not less than 4."
```
Remember: the order of arguments is important, and you don’t need an end for this version of if/else.


When and Then: The Case Statement
```
case language
  when "JS"
    puts "Websites!"
  when "Python"
    puts "Science!"
  when "Ruby"
    puts "Web apps!"
  else
    puts "I don't know!"
end
```
But you can fold it up like so:
```
rb case language when "JS" then puts "Websites!" when "Python" then puts "Science!" when "Ruby" then puts "Web apps!" else puts "I don't know!" end
```

```
puts "Hello there!"
greeting = gets.chomp

case greeting
  when "English" then puts "Hello!"
  when "French" then puts "Bonjour!"
  when "German" then puts "Guten Tag!"
  when "Finnish" then puts "Haloo!"
  else puts "I don't know that language!"
end
```
#Hello there!
Finnish
Haloo!

Conditional Assignment
```
favorite_book = nil
puts favorite_book

favorite_book ||= "Cat's Cradle"
puts favorite_book

favorite_book ||= "Why's (Poignant) Guide to Ruby"
puts favorite_book

favorite_book = "Why's (Poignant) Guide to Ruby"
puts favorite_book
```
#Cat's Cradle
Cat's Cradle
Why's (Poignant) Guide to Ruby

We try conditional assignment again, this time with “Why’s (Poignant) Guide to Ruby.” But wait! Our variable already has a value, “Cat’s Cradle,” so it stays set to that value and that’s what we see printed out.

```
# Write your code on line 2!
favorite_language = nil
puts favorite_language

favorite_language = 'Ruby'
puts favorite_language
favorite_language ||= 'Python'
puts favorite_language
favorite_language = 'I love both of them.'
puts favorite_language

```
#Ruby
Ruby
I love both of them.

Implicit Return
For instance, if you don’t tell a JavaScript function exactly what to return, it’ll return undefined. For Python, the default return value is None. But for Ruby, it’s something different: Ruby’s methods will return the result of the last evaluated expression.

This means that if you have a Ruby method like this one:

def add(a,b)
  return a + b
end
You can simply write:

def add(a,b)
  a + b
end
And either way, when you call add(1,1), you’ll get 2.

```
def multiple_of_three(n)
   n % 3 == 0 ? "True" : "False"
end
```

Short-Circuit Evaluation
```
def a
  puts "A was evaluated!"
  return true
end

def b
  puts "B was also evaluated!"
  return true
end

puts a || b
puts "------"
puts a && b
```
#A was evaluated!
true
------
A was evaluated!
B was also evaluated!
true

```

def a 
  puts 'A was evaluated.'
  return false
end
def b
  puts 'B was evaluated.'
  return true
end
puts a || b
puts '------'
puts a & b
```
#A was evaluated.
B was evaluated.
true
------
A was evaluated.
B was evaluated.
false

The Right Tool for the Job
If we want to do something a specific number of times, we can use the .times method, like so:

5.times { puts "Odelay!" }
# Prints 5 "Odelay!"s on separate lines
If we want to repeat an action for every element in a collection, we can use .each:

[1, 2, 3].each { |x| puts x * 10 }
# Prints 10, 20, 30 on separate lines

```
my_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

my_array.each { |num| puts num unless num % 2 !=0 }
```
#2
4
6
8
10

Up the Down Staircase
95.upto(100) { |num| print num, " " }
# Prints 95 96 97 98 99 100
Use .upto to puts the capital letters "L" through "P".

(Make sure to use puts and not print, so each letter is on its own line!)
```
"L".upto('P'){
  |letter| puts letter}
  ```
  #L
M
N
O
P

Call and Response
.respond_to? takes a symbol and returns true if an object can receive that method and false otherwise. For example,

[1, 2, 3].respond_to?(:push)
would return true, since you can call .push on an array object. However,

[1, 2, 3].respond_to?(:to_sym)
would return false, since you can’t turn an array into a symbol.

Being Pushy
Instead of typing out the .push method name, you can simply use <<, the concatenation operator (also known as “the shovel”) to add an element to the end of an array:

[1, 2, 3] << 4
# ==> [1, 2, 3, 4]


Good news: it also works on strings! You can do:

```rb “Yukihiro “ << “Matsumoto”

==> “Yukihiro Matsumoto”
```

sample
```
alphabet = ["a", "b", "c"]
alphabet<<'d'# Update me!

caption = "A giraffe surrounded by "
caption <<"weezards!" # Me, too!
puts caption
```


String Interpolation
You can always use plain old + or << to add a variable value into a string:
```
drink = "espresso"
"I love " + drink
# ==> I love espresso
"I love " << drink
# ==> I love espresso
```
But if you want to do it for non-string values, you have to use .to_s to make it a string:
```
age = 26
"I am " + age.to_s + " years old."
# ==> "I am 26 years old."
"I am " << age.to_s << " years old."
# ==> "I am 26 years old."
```
This is complicated, and complicated is not the Ruby way. A better way to do this is with string interpolation. The syntax looks like this:
```
"I love #{drink}."
# ==> I love espresso.
"I am #{age} years old."
# ==> I am 26 years old.
```
All you need to do is place the variable name inside #{} within a string!

```
favorite_things = ["Ruby", "espresso", "candy"]

puts "A few of my favorite things:"

favorite_things.each do |thing|
  puts "I love #{thing}!"
end
```
#A few of my favorite things:
I love Ruby!
I love espresso!
I love candy!

One-Liners
```
puts "One is less than two!" if 1 < 2
```

The Ternary Operator
```
three = 3
puts three == 3 ? "Of course." : "What?"
# ==> puts "Of course."
```

In Case of Many Options
```
puts "What's your favorite language?"
language = gets.chomp

case language
when "Ruby"
  puts "Ruby is great for web apps!"
when "Python"
  puts "Python is great for science."
when "JavaScript"
  puts "JavaScript makes websites awesome."
when "HTML"
  puts "HTML is what websites are made of!"
when  "CSS"
  puts "CSS makes websites pretty."
else
  puts "I don't know that language!"
end
```
#What's your favorite language?
Ruby
Ruby is great for web apps!

