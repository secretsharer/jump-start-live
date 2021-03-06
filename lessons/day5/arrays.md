_Jumpstart Live (JSL)_
# Day 5

## Arrays
Arrays are ordered collections of data that can be accessed with a 0-based index. Arrays are also part of a family of data structures, data structures organize and store information.

### Why Arrays?
Instead of having to create individual variables, arrays are often used to group data together and make it easy to access.

Consider wanting to store the daily temperature averages for the month of December. You could create 31 variables to store those temperatures but that might be hard to manage, not to mention, many lines of code. Then, if you later decide to store the temperatures for the entire year, it becomes almost impossible to handle.

A perfect solution to this is to use an array. Now you have one name to reference all of the temperatures, and you can easily access the temperature from a specific day.

### Array Indexes
Array indexes start at 0, and increase by 1. You cannot change the indexes of an array. 

```ruby
nums = [34, 78, 45]
```

| Index | Value |
| :--- | :--- |
| 0 | 34 |
| 1 | 78 |
| 2 | 45 |
| 3 | nil |

You can also use negative indexes to look at the array from the end

| Index | Value |
| :--- | :--- |
| -1 | 45 |
| -2 | 78 |
| -3 | 34 |
| -4 | nil |

### Create

#### Using []
```ruby
# creates an empty array named list
list = []

# creates an array named list, storing 1, 2, 3
list = [1, 2, 3]
```

#### Array.new
* Can pass parameters to initialize to certain values

```ruby
# creates an empty array named list
list = Array.new

# creates an array of length 3, storing nil in each index
list = Array.new(3)

# creates an array of length 5, storing "Ada" in each index
ada = Array.new(5, "Ada")

# passes a block as a parameter
# creating an array of multiples of 2, named mult2
mult2 = Array.new(5) { |i| i * 2 }
```

### Printing an Array
* If you use `puts` to display an array, it will list each element on its own line
* Instead use `print` or `puts` with string interpolation and the array will display as a comma separated list, which is usually easier to read

```ruby
arr = Array.new(3, 0)
# This will display ..
# 0
# 0
# 0
puts arr

# This will display ...
# [0, 0, 0]
print arr

# This will display ...
# [0, 0, 0]
puts "#{arr}"
```

### Change and Access
Array elements can be accessed with their indexes

```ruby
list =  [0, 1, 2]
list[0] = 7
list[1] = -1
list[2] = 33
# list is now [7, -1, 33]
puts list[-1] # 33
puts list[-2] # -1
puts list[-3] # 7
puts list[-4] # nil
puts list[9]  # nil
```

### Add to end
Elements can be added to the end of an array using two different notations

#### push
Push, can accept 1 or more elements

```ruby
list = ["apple", "orange", "kiwi"]
list.push("banana")
# list is now ["apple", "orange", "kiwi", "banana"]
list.push("pear", "nectarine")
# list is now ["apple", "orange", "kiwi", "banana", "pear", "nectarine"]
```

#### shovel
The shovel method (`<<`) can only accept 1 element

```ruby
list = [true, false]
list << false
# list is now [true, false, false]
list << false, true # error!
```

It is possible to have an array of arrays, but be careful when using shovel (i.e., don't shovel an array onto an array, unless that is your intention)

```ruby
nums = [4, 5, 6]
# shoves an array holding 7 onto nums
nums << [7]
# arary is now [4, 5, 6, [7]]
```

### Iterating over an array
Iterating over an array, is a process to look at each element of an array and perform some action.

You can use either a `do ... end` block or a block with curly braces for the each method. By convention `do ... end` should be used for multi-line blocks, and curly braces for single-line blocks. Keep in mind though, that curly braces have higher precedence when compared to `do ... end` blocks.

#### each
```ruby
nums = [1, 3, 5]
nums.each do |num|
  puts num
end

nums.each { |num| puts num }
```

#### each with index
```ruby
nums = [2, 4, 6]
nums.each_with_index do |num, index|
  puts "#{index}: #{num}"
end

nums.each_with_index { |num, index| puts "#{index}: #{num}" }
```

### Useful array methods

| Method | Description |
| :--- | :--- |
| `arr.length` | Returns the number of elements currently stored in arr |
| `arr.empty?` | Returns `true` if there are no elements in arr, otherwise returns `false` |
| `arr.first` | Returns the first element from arr |
| `arr.last` | Returns the last element from arr |
| `arr.take(n)` | Returns the first n elements from arr |
| `arr.include?(element)` | Returns `true` if element is stored in arr, otherwise returns `false` |

### Exercises

1. Create an array which will store the square of each value between 2 and 5, inclusive.

  ```ruby
  list = []
  (2..5).each do |i|
    list.push(i * i)
  end
  ```

  ```ruby
  list = Array.new(4) { |i| (i + 2) * (i + 2) }
  ```

2. Given an array that contains three people, Ada Lovelace, Anita Borg, and Margaret Hamilton (1) Add one new person of your choice, (2) Output Annie Easley using the array, (3) Replace Ada Lovelace with Megan Smith

  ```ruby
  people = ["Ada Lovelace", "Annie Easley", "Margaret Hamilton"]
  people << "Grace Hopper"
  puts people[1] # outputs Annie Easley
  people[0] = "Megan Smith"
  # list is now ["Megan Smith", "Annie Easley", "Margaret Hamilton"]
  ```

3. On paper, create an array which will store the names of people that inspire you. Then write down two different ways you can access the second-to-last name in your array?  

4. On paper, create an array which stores the numbers 1 – 15. Then write down two different ways of accessing the middle number?  

5. On paper, write code that will create an array named powers_of_2, and stores the fist 10 powers of 2

### Resources
* [Ada Arrays Video](https://adaacademy.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=5fb869d2-db52-4cd2-a1cc-238e0e084fa5) (15:34)
* [Ruby Documentation on Arrays](http://ruby-doc.org/core-2.4.0/Array.html)
