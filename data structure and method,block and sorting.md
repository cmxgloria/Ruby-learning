# data structure

Creating Arrays
my_array =['apple','banana','grape']

Access by Index
We can access the ith element of an array called array by putting the index in square brackets, like so: array[i]. array[0] gets the first element, array[1] gets the second element, and so on. This is called access by index.
```
demo_array = [100, 200, 300, 400, 500]

print demo_array[2] 
```
Arrays of Non-Numbers
```
string_array = ["These", "are", "some", "strings"]
print string_array[3]
```

Arrays of Arrays
```
multi_d_array = [[0,0,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,0]]

multi_d_array.each { |x| puts "#{x}\n" }
#[0, 0, 0, 0]

[0, 0, 0, 0]

[0, 0, 0, 0]

[0, 0, 0, 0]
```

Create Your Own
See how a two-dimensional array 
```
my_2d_array = [[1,2,3],['apple','grape','banana'],[true,false,true]]
print my_2d_array.each{|x| puts "#{x}\n"}
# [1, 2, 3]

["apple", "grape", "banana"]

[true, false, true]

[[1, 2, 3], ["apple", "grape", "banana"], [true, false, true]]
```
Introduction to Hashes
hash is a collection of key-value pairs. Hash syntax looks like this:

hash = {
  key1 => value1,
  key2 => value2,
  key3 => value3
}
Values are assigned to keys using =>. You can use any Ruby object for a key or value.
```
my_hash = { "name" => "Eric",
  "age" => 26,
  "hungry?" => true
}

puts my_hash["name"]
puts my_hash["age"]
puts my_hash["hungry?"]
```

Using Hash.new
You can also create a hash using Hash.new, like so:

my_hash = Hash.new
Setting a variable equal to Hash.new creates a new, empty hash; it’s the same as setting the variable equal to empty curly braces ({}).

Adding to a Hash
```
pets = Hash.new
pets["Stevie"] = "cat"
# Adds the key "Stevie" with the
# value "cat" to the hash
```

Accessing Hash Values
```
pets = {
  "Stevie" => "cat",
  "Bowser" => "hamster",
  "Kevin Sorbo" => "fish"
}

puts pets["Stevie"]
# will print "cat"
```

Re)Introduction to Iteration
```
friends = ["Milhouse", "Ralph", "Nelson", "Otto"]

family = { "Homer" => "dad",
  "Marge" => "mom",
  "Lisa" => "sister",
  "Maggie" => "sister",
  "Abe" => "grandpa",
  "Santa's Little Helper" => "dog"
}

friends.each { |x| puts "#{x}" }
family.each { |x, y| puts "#{x}: #{y}" }
```
#Milhouse
Ralph
Nelson
Otto
Homer: dad
Marge: mom
Lisa: sister
Maggie: sister
Abe: grandpa
Santa's Little Helper: dog

Iterating Over Arrays

```
languages = ["HTML", "CSS", "JavaScript", "Python", "Ruby"]
languages.each{|language| puts language}

```

Iterating Over Multidimensional Arrays

```
s = [["ham", "swiss"], ["turkey", "cheddar"], ["roast beef", "gruyere"]]

s.each { |sub_array| sub_array.each { |element| puts element }}
```
#ham
swiss
turkey
cheddar
roast beef
gruyere

Iterating Over Hashes
```
secret_identities = {
  "The Batman" => "Bruce Wayne",
  "Superman" => "Clark Kent",
  "Wonder Woman" => "Diana Prince",
  "Freakazoid" => "Dexter Douglas"
}
  
secret_identities.each do |hero, name| 
  puts "#{hero}: #{name}"
end
```
#The Batman:Bruce Wayne
Superman:Clark Kent
Wonder Woman:Diana Prince
Freakazoid:Dexter Douglas


Multidimensional Arrays
```
my_array = [['apple','grape'],[1,4],[true,false]]
puts my_array
```

Hashes
```
prices = { 
  "apple" => 0.52,
  "banana" => 0.23,
  "kiwi" => 1.42
}

sounds = Hash.new
sounds["dog"] = "woof"
sounds["cat"] = "meow"
```
Iterating Over a Hash
```
lunch_order = {
  "Ryan" => "wonton soup",
  "Eric" => "hamburger",
  "Jimmy" => "sandwich",
  "Sasha" => "salad",
  "Cole" => "taco"
}

lunch_order.each do |person, order| 
  puts order
end
```
#wonton soup
hamburger
sandwich
salad
taco

or can use this one to replace
"lunch_order.each do |person, order| 
  puts order
end"
lunch_order.each{|person,order| puts order}


CREATE A HISTOGRAM
```
puts "Text please: "
text = gets.chomp

words = text.split(" ")
frequencies = Hash.new(0)
words.each { |word| frequencies[word] += 1 }
frequencies = frequencies.sort_by {|a, b| b }
frequencies.reverse!
frequencies.each { |word, frequency| puts word + " " + frequency.to_s }
```
#Text please: 
i am a girl
girl 1
a 1
am 1
i 1

Sorting the Hash
```
colors = { 
  "blue" => 3,
  "green" => 1,
  "red" => 2
}
colors = colors.sort_by do |color, count|
  count
end
colors.reverse!
```
 sample
 ```
 puts "Text please: "
text = gets.chomp

words = text.split

frequencies = Hash.new(0)
words.each{|word| frequencies[word]+=1}
frequencies = frequencies.sort_by do |k,v|
end
frequencies.reverse!
frequencies.each do |word, frequency|
  puts word + " " + frequency.to_s
end
```


# METHODS, BLOCKS, & SORTING
Why Methods?
```
def prime(n)
  puts "That's not an integer." unless n.is_a? Integer
  is_prime = true
  for i in 2..n-1
    if n % i == 0
      is_prime = false
    end
  end
  if is_prime
    puts "#{n} is prime!"
  else
    puts "#{n} is not prime."
  end
end

prime(2)
prime(9)
prime(11)
prime(51)
prime(97)
```

Methold Syntax
he header, which includes the def keyword, the name of the method, and any arguments the method takes. (We’ll get to arguments in the next section)
The body, which is the code block that describes the procedures the method carries out. The body is indented two spaces by convention (as with for, if, elsif, and else statements)
The method ends with the end keyword.
```
def puts_1_to_10
  (1..10).each { |i| puts i }
end

puts_1_to_10 
#1
2
3
4
5
6
7
8
9
10

create your own
```
def greeting
puts "Hello, Rubyist!"
end
greeting
```
#Hello, Rubyist!

call it!
if you call a method called cartoon_fox, the program will start looking for the method with that name and try to execute the code inside it.

If the program doesn’t find a method called cartoon_fox, it will return a NameError. We’ll cover errors in another lesson.
```
def array_of_10
  puts (1..10).to_a
end
array_of_10
```
#[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

Parameters and Arguments
```
def cubertino(n)
  puts n ** 3
end

cubertino(8)
```
#512

Splat
Let’s say you have a method, friend, that puts the argument it receives from the user. It might look something like this:

def friend(name):
  puts "My friend is " + name + "."
end
This is great for just one friend, but what if you want to print out the all of the user’s friends, without knowing how many friend names the user will put in ahead of time?

The solution: splat arguments. Splat arguments are arguments preceded by a *, which tells the program that the method can receive one or more arguments.
```
def what_up(greeting, *friends)
  friends.each { |friend| puts "#{greeting}, #{friend}!" }
end

what_up("hello ", "Ian", "Zoe", "Zenas", "Eleanor")
```
#hello , Ian!
hello , Zoe!
hello , Zenas!
hello , Eleanor!

Let's Learn Return
