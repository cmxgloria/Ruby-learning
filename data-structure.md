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
