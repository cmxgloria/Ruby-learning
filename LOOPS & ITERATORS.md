
Danger: Infinite Loops!
```
i = 0
while i < 5
  puts i
  # Add your code here!
  i=i+1
  
end
```

The 'Until' Loop
```
counter = 1
until counter > 10
  puts counter
  # Add code to update 'counter' here!
  counter += 1
end
```

More Assignment Operators
 +=, -=, *=, and /=.
 
 The 'For' Loop
 ```
 for num in 1...10
  puts num
end
#1 2 3 4 5 6 7 8 9
```

Inclusive and Exclusive Ranges
The reason this program counted to 9 and not 10 was that we used three dots in the range; this tells Ruby to exclude the final number in the count: for num in 1...10 means “go up to but don’t include 10.” If we use two dots, this tells Ruby to include the highest number in the range.
```
for num in 1..15
  puts num
end
# print 1 to 15 includidng
```

Building Your Own
```
for num in 1..20
   puts num
 end
 ```
 The Loop Method
 loop { print "Hello, world!" }
In Ruby, curly braces ({}) are generally interchangeable with the keywords do (to open the block) and end (to close it). Knowing this, we can write a smarter loop than the one above: rb i = 0 loop do i += 1 print "#{i}" break if i > 5 end

The break keyword is our Get Out of Jail Free card: it breaks a loop as soon as its condition is met.
```
i = 20
loop do 
  i -= 1
  print "#{i}"
 break if i <= 0
end
# 191817161514131211109876543210
```

Next!
```
i = 20
loop do
  i -= 1
  next if i % 2 != 0
  print "#{i}"
  break if i <= 0
end
#181614121086420
```
 sample
 ```
 for i in 1..5
  next if i%2==0
  print i
end
#135
```

Saving Multiple Values
array

The .each Iterator
 The syntax looks like this:

object.each { |item| 
  # Do something 
}
You can also use the do keyword instead of {}:

object.each do |item| 
  # Do something 
end
The variable name between | | can be anything you like: it’s just a placeholder for each element of the object you’re using .each on.


```
array = [1,2,3,4,5]

array.each do |x|
  x += 10
  print "#{x}"
end
#1112131415
```

Try It Out!
```
odds = [1,3,5,7,9]
odds.each do |odd| 
  print odd*2
end
#26101418
```
Make sure to use print rather than puts, so your output appears on one line.


```
numbers = [1, 2, 3, 4, 5]

# one way to loop
numbers.each { |item| puts item }

# another way to loop
numbers.each do |item|
  puts item
end
#
1
2
3
4
5
1
2
3
4
5

```


The .times Iterator
```
10.times { print "Chunky bacon!" }
```

Looping with 'While'
```
i = 3
while i > 0 do
  print i
  i -= 1
end
```
sample
```
i = 1
while i <= 50
  print i
  i += 1
end
```

Looping with 'Until'

```
i = 3
while i > 0 do
  print i
  i -= 1
end

j = 3
until j == 0 do
  print j
  j -= 1
end
#321321
```

sample
```
i = 1
until i == 51
  print i
  i += 1
end
```

Looping with 'For'
```
for k in 1..3
  print k
end
```

Loop the Loop with Loop
```
i = 0
loop do
  print "Ruby!"
  i += 1
  break if i == 30
end
```

Iterating with .times
```
30.times {print "Ruby!"}
```

# Redact
```
puts "Text to search through: "
text = gets.chomp
puts "Word to redact: "
redact = gets.chomp

words = text.split(" ")

words.each do |word|
  if word != redact
    print word + " "
  else
    print "REDACTED "
  end
end
```
//Text to search through: 
i am the queen
Word to redact: 
you are my girl
i am the queen

Getting the User's Input

The .split Method
Ruby has a built-in method for this called .split; it takes in a string and returns an array. If we pass it a bit of text in parentheses, .split will divide the string wherever it sees that bit of text, called a delimiter. For example,

text.split(",")
tells Ruby to split up the string text whenever it sees a comma.

redact
```
puts "Enter some text: "
text = gets.chomp

puts "Enter words to redact: "
redact = gets.chomp

words = text.split(" ")
words.each { | word | print word }
```
//Enter some text: 
how big is it
Enter words to redact: 
it is small.
howbigisit

Control Flow Know-How
```
puts "Enter some text: "
text = gets.chomp

puts "Enter words to redact: "
redact = gets.chomp

words = text.split(" ")
words.each { |word| 
  if word == redact
    print "REDACTED "
  else
 		print word + " "
  end }
  ```
  
# data sructures









