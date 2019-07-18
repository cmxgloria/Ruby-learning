# ORDERING YOUR LIBRARY
What You'll Be Building
We noticed in the last lesson that .sort! didn’t have a built-in way of handling sorting in reverse alphabetical order. Now that we know how to write our own Ruby methods, we can fix that!
```
def alphabetize(arr, rev=false)
  if rev
    arr.sort { |item1, item2| item2 <=> item1 }
  else
    arr.sort { |item1, item2| item1 <=> item2 }
  end
end

books = ["Heart of Darkness", "Code Complete", "The Lorax", "The Prophet", "Absalom, Absalom!"]

puts "A-Z: #{alphabetize(books)}"
puts "Z-A: #{alphabetize(books, true)}"
```
#A-Z: ["Absalom, Absalom!", "Code Complete", "Heart of Darkness", "The Lorax", "The Prophet"]
Z-A: ["The Prophet", "The Lorax", "Heart of Darkness", "Code Complete", "Absalom, Absalom!"]

Defining Our Method
def alphabetize
end


Default Parameters
def alphabetize(arr, rev=false)
The first part makes sense—we’re defining a method, alphabetize. We can guess that the first parameter is an array, but what’s this rev=false business?

What this does is tell Ruby that alphabetize has a second parameter, rev (for “reverse”) that will default to false if the user doesn’t type in two arguments.


Sorting
numbers = [5, 1, 3, 8]
numbers.sort!
puts numbers
In the above example, we create a new array called numbers.
Then, we sort the array.
Finally, we print out 1, 3, 5, 8, the sorted array.
In Ruby, there are two sorting methods, .sort or sort!. The first method, .sort, simply returns a sorted array while leaving the original array alone. The second method, .sort!, modifies the actual array.
```
def alphabetize(arr, rev = false)
  arr.sort!
end

numbers = [3, 5, 1, 6]

puts alphabetize(numbers)
```

Sorting With Control Flow
Great! Now we need to add the right logic to our method.
```
numbers = [1, 2, 3, 4, 5]
numbers.reverse!
puts numbers
```
In the example above, we create an array called numbers.
Then, we reverse the array. Like with .sort!, the exclamation mark means we modify the actual array.
Finally, we print out 5, 4, 3, 2, and 1.

After your .sort! call, add an if-else statement. If rev is true, call reverse! on arr, else return arr.

Keep your numbers array and the puts statement so that you can see your work in action!
```
def alphabetize(arr, rev = false)
  arr.sort!
  if rev == true
    arr.reverse!
  else
  	arr
  end
end

numbers = [3, 5, 1, 6]

puts alphabetize(numbers)
```

# HASHES AND SYMBOLS
The Story So Far
Recall that hashes are collections of key-value pairs, where a unique key is associated with some value. For example:

breakfast = { 
  "bacon" => "tasty",
  "eggs" => "tasty",
  "oatmeal" => "healthy",
  "OJ" => "juicy"
}
Remember that keys must be unique, but values can repeat. That’s why we can have more than one key share the value “tasty.”)

We can create hashes several ways, but two of the most popular are

hash literal notation:
new_hash = { "one" => 1 }
and

2. hash constructor notation:

new_hash = Hash.new


Iterating Over Hashes
```
matz = { "First name" => "Yukihiro",
  "Last name" => "Matsumoto",
  "Age" => 47,
  "Nationality" => "Japanese",
  "Nickname" => "Matz"
}

matz.each do |key, value|
  puts [key,value]
end

```
#["First name", "Yukihiro"]
["Last name", "Matsumoto"]
["Age", 47]
["Nationality", "Japanese"]
["Nickname", "Matz"]

if like this
```
matz = { "First name" => "Yukihiro",
  "Last name" => "Matsumoto",
  "Age" => 47,
  "Nationality" => "Japanese",
  "Nickname" => "Matz"
}

matz.each do |key, value|
  puts value
end

```
#Yukihiro
Matsumoto
47
Japanese
Matz


Nil: a Formal Introduction
In many languages, you’ll get an error of some kind. Not so in Ruby: you’ll instead get the special value nil.

Along with false, nil is one of two non-true values in Ruby. (Every other object is regarded as “truthy,” meaning that if you were to type if 2 or if "bacon", the code in that if statement would be run.)

It’s important to realize that false and nil are not the same thing: false means “not true,” while nil is Ruby’s way of saying “nothing at all.”
```
creatures = { "weasels" => 0,
  "puppies" => 6,
  "platypuses" => 3,
  "canaries" => 1,
  "Heffalumps" => 7,
  "Tiggers" => 1
}

creatures["birds"]
```
Go ahead and try to access a key in creatures that doesn’t exist.


Setting Your Own Default
You don’t have to settle for nil as a default value, however. If you create your hash using the Hash.new syntax, you can specify a default like so:

my_hash = Hash.new("Trady Blix")
Now if you try to access a nonexistent key in my_hash, you’ll get "Trady Blix" as a result.

You can always read more hashy goodness in the official Ruby documentation
```
no_nil_hash = Hash.new('Gloria He')
```

A Key of a Different Color
We can certainly use strings as Ruby hash keys; as we’ve seen, there’s always more than one way to do something in Ruby. However, the Rubyist’s approach would be to use symbols.
```
menagerie = { :foxes => 2,
  :giraffe => 1,
  :weezards => 17,
  :elves => 1,
  :canaries => 4,
  :ham => 1
}
puts menagerie
```
#{:foxes=>2, :giraffe=>1, :weezards=>17, :elves=>1, :canaries=>4, :ham=>1}

What's a Symbol?
"string" == :string # false
Above and beyond the different syntax, there’s a key behavior of symbols that makes them different from strings. While there can be multiple different strings that all have the same value, there’s only one copy of any particular symbol at a given time.
The .object_id method gets the ID of an object—it’s how Ruby knows whether two objects are the exact same object. Run the code in the editor to see that the two "strings" are actually different objects, whereas the :symbol is the same object listed twice.

```
puts "string".object_id
puts "string".object_id

puts :symbol.object_id
puts :symbol.object_id
```
#12749900
12749660
802268
802268

Symbol Syntax
Symbols always start with a colon (:). They must be valid Ruby variable names, so the first character after the colon has to be a letter or underscore (_); after that, any combination of letters, numbers, and underscores is allowed.

Make sure you don’t put any spaces in your symbol name—if you do, Ruby will get confused.

rb :my symbol # Don't do this! :my_symbol # Do this instead.

```
my_first_symbol = :my_symbol
```

What are Symbols Used For?
Symbols pop up in a lot of places in Ruby, but they’re primarily used either as hash keys or for referencing method names. (We’ll see how symbols can reference methods in a later lesson.)
```
sounds = {
  :cat => "meow",
  :dog => "woof",
  :computer => 10010110,
}
```
Symbols make good hash keys for a few reasons:

They’re immutable, meaning they can’t be changed once they’re created;
Only one copy of any symbol exists at a given time, so they save memory;
Symbol-as-keys are faster than strings-as-keys because of the above two reasons.

```
symbol_hash = {
  :one => 1,
  :favourite_flower => 'purple',    # Fill in these two blanks!
  :drink=>'coke',
}
puts symbol_hash
```
#{:one=>1, :favourite_flower=>"purple", :drink=>"coke"}

Converting Between Symbols and Strings
```
:sasquatch.to_s
# ==> "sasquatch"

"sasquatch".to_sym
# ==> :sasquatch
```
questions
We have an array of strings we’d like to later use as hash keys, but we’d rather they be symbols.

Create a new variable, symbols, and store an empty array in it.
Use .each to iterate over the strings array.
For each s in strings, use .to_sym to convert s to a symbol and use .push to add that new symbol to symbols.
Print the symbols array.

```
strings = ["HTML", "CSS", "JavaScript", "Python", "Ruby"]
symbols = []

strings.each do |s| 
 symbols.push(s.to_sym)
end 
print symbols
```
#[:HTML, :CSS, :JavaScript, :Python, :Ruby]

```
numbers = [1, 2, 3, 4, 5, 6]
evens = []
numbers.each do |number|
  if number % 2 == 0
    evens.push(number)
  end
end
print evens
# prints '[2, 4, 6]'
```

Many Paths to the Same Summit
Besides using .to_sym, you can also use .intern. This will internalize the string into a symbol and works just like .to_sym:

"hello".intern
# ==> :hello
When you’re looking at someone else’s code, you might see .to_sym or .intern (or both!) when converting strings to symbols.


All Aboard the Hash Rocket!
The hash syntax you’ve seen so far (with the => symbol between keys and values) is sometimes nicknamed the hash rocket style.
```
numbers = {
  :one => 1,
  :two => "two",
  :three => 3,
}
```
This is because the => looks like a tiny rocket!

Let’s build a hash from the ground up using symbols as keys.

However, the hash syntax changed in Ruby 1.9. Just when you were getting comfortable!

The good news is that the changed syntax is easier to type than the old hash rocket syntax, and if you’re used to JavaScript objects or Python dictionaries, it will look very familiar:
```
new_hash = { 
  one: 1,
  two: 2,
  three: 3
}```
```
The two changes are:

1. You put the colon at the end of the symbol, not at the beginning;
2. You don't need the hash rocket anymore.

It's important to note that even though these keys have colons at the end instead of the beginning, they're still symbols!

```rb
puts new_hash
# => { :one => 1, :two => 2, :three => 3 }

sample
```
movies = {
  children: "Moana",
  scifi: "Mortal Kombat",
  history: "Lincoln"
}
puts movies
```
#{:children=>"Moana", :scifi=>"Mortal Kombat", :history=>"Lincoln"}


Dare to Compare
```
require 'benchmark'

string_AZ = Hash[("a".."z").to_a.zip((1..26).to_a)]
symbol_AZ = Hash[(:a..:z).to_a.zip((1..26).to_a)]

string_time = Benchmark.realtime do
  100_000.times { string_AZ["r"] }
end

symbol_time = Benchmark.realtime do
  100_000.times { symbol_AZ[:r] }
end

puts "String time: #{string_time} seconds."
puts "Symbol time: #{symbol_time} seconds."
```
#String time: 0.006994865019805729 seconds.
Symbol time: 0.00441761699039489 seconds.



Becoming More Selective

```
grades = { alice: 100,
  bob: 92,
  chris: 95,
  dave: 97
}

grades.select { |name, grade| grade <  97 }
# ==> { :bob => 92, :chris => 95 }

grades.select { |k, v| k == :alice }
# ==> { :alice => 100 }
```

sample
```
movie_ratings = {
  memento: 3,
  primer: 3.5,
  the_matrix: 5,
  truman_show: 4,
  red_dawn: 1.5,
  skyfall: 4,
  alex_cross: 2,
  uhf: 1,
  lion_king: 3.5
}

good_movies = movie_ratings.select { |name, rating| rating > 3 }
puts good_movies


```
#{:primer=>3.5, :the_matrix=>5, :truman_show=>4, :skyfall=>4, :lion_king=>3.5}

More Methods, More Solutions
```
my_hash = { one: 1, two: 2, three: 3 }

my_hash.each_key { |k| print k, " " }
# ==> one two three

my_hash.each_value { |v| print v, " " }
# ==> 1 2 3
```

sample
```
movie_ratings = {
  memento: 3,
  primer: 3.5,
  the_matrix: 3,
  truman_show: 4,
  red_dawn: 1.5,
  skyfall: 4,
  alex_cross: 2,
  uhf: 1,
  lion_king: 3.5
}
# Add your code below!

movie_ratings.each_key { |title| puts title }
```
#memento
primer
the_matrix
truman_show
red_dawn
skyfall
alex_cross
uhf
lion_king
