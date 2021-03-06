_Jumpstart Live (JSL)_
# Day 3
## Loops

### Definitions
<dl>
  <dt>Infinite loop</dt>
  <dd>A loop that runs until you kill the program</dd>
  <dt>Counter-controlled loop</dt>
  <dd>When the number of loops can be determined prior to loop execution (e.g, times, each)</dd>
  <dt>Sentinel-controlled loop</dt>
  <dd>When the number of loops cannot be determined prior to loop execution (e.g, while, until)</dd>
</dl>

### Sentinel-controlled Loops
#### While loop
* Executes code over and over again, while a condition is true

```
# code syntax
while <boolean expression> do
   code
end
```

```ruby
# code example
rand_num = rand(5)
guess = gets.chomp.to_i
while rand_num != guess do
	guess = gets.chomp.to_i
end
```

#### `until` loop
* Executes code over and over again, until the condition is true

```
# code syntax
until <boolean expression> do
   code
end
```

```ruby
# code example
rand_num = rand(5)
guess = gets.chomp.to_i
until rand_num == guess do
	guess = gets.chomp.to_i
end
```

### Counter-controlled loops
#### Iterators
* Iterators are methods
* All iterators require blocks, and execute those blocks as many times as there are iterations
* Iterators return all the elements of a collection, one after the other

##### `each`
* `each` is an iterator that returns each value of the collection, one by one, to the block
* `each` must be associated with a block
* the iteration variable is optional with `each`, but usually used

```ruby
# each syntax
# do ... end is the block
# variable is the iteration variable
collection.each do |variable|
   code
end
```

```ruby
# code example
# prints out all the values of arr, each on its own line
arr = [1,2,3,4,5]
arr.each do |element|
   puts element
end
```

###### `range` Loops
* A range is a set of values with a beginning and an end
* Ranges always include the beginning value
* When two dots are used, the end value is included
* When three dots are used, the end value is not included

```ruby
# code example
# prints out 1,2,3,4 each on its own line
(1..4).each do |i|
	puts i
end
```

```ruby
# code example
# prints out 1,2,3 each on its own line
(1...4).each do |i|
	puts i
end
```

##### `times`
* `times` is an iterator over a certain range of values
* `times` must be associated with a block, but the iteration variable is optional
* `times` starts counting at `0`, and goes up to `1 -` the value placed before `.times`

```ruby
# times syntax no iteration variable
Fixnum.times
   code
end
```

```ruby
# times syntax with iteration variable
Fixnum.times do |variable|
   code
end
```

```ruby
# code example
# prints out "hello" 5 times
5.times do
	puts "hello"
end
```

```ruby
# code example
# prints out 0, 1, 2 each on its own line
3.times do |num|
	puts num
end
```

### Loop Tables
1. `range`/`each`

	```ruby
	(1..3).each do |num|
		puts num * num
	end
	```

	| num | output |
	| :--- | :--- |
	| 1 | 1 |
	| 2 | 4 |
	| 3 | 9 |

2. `range`/`each` with sum

	```ruby
	total = 0

	(1..3).each do |num|
		total = total + num
	end

	puts total
	```

	| num | total | output |
	| :--- | :--- | :--- |
	| - | 0 | - |
	| 1 | 1 | - |
	| 2 | 3 | - |
	| 3 | 6 | - |
	| 3 | 6 | 6 |

3. Create a loop table for the code below, assuming the inputs noted below

	```ruby
	puts "Hello! We are going to total some numbers!"
	puts "Enter a negative number to quit."

	total = 0
	input = gets.chomp.to_i
	while input > -1
	  total += input
	  input = gets.chomp.to_i
	end

	puts "Result: #{total}"
	```

	```
	1. inputs; 0, -1, 2
	2. inputs: 33, 6, 2, 9, 0, -1
	3. inputs: 4.2, 1.1, 9.9, -1.0
	```

### Loop Comparison
1. `times` iteration variable
	* What is the difference between these loops?
	* Which is a better style solution?

	```ruby
	2.times do
	  puts "dance"
	end
	```

	```ruby
	2.times do |i|
	  puts "dance"
	end
	```

### Resources
* [Ada Loops Video](https://adaacademy.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=de97b3c0-a134-4fb5-a671-300f290f38cc) (17:31)