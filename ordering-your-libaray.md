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

