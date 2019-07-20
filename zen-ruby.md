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
