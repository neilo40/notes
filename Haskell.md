# Haskell notes
from: https://learnyouahaskell.com/starting-out

# infix/prefix
infix func name is between args, e.g. a == b
prefix func name is before, e.g. div 9 3 
can write prefix as infix with backticks, e.g. 9 `div` 3
/= is not equal (not !=)

# if/then/else
else is mandatory
f x = if x > 100 then x else x * 2
can do over multiple lines, e.g.
f x = if x > 100
	then x
	else x * 2

# functions
function name is f, takes one arg called x and returns one thing
this example has no type definitions
f x = x + x
name cannot begin with capital letter
func can take zero params, e.g. f = "hello".  this is called a definition 

## useful built-in funcs
odd - True if odd
even - True if even

# lists 
all elems must be same data type
can be infinte in length, can change length
concat lists: [1,2,3] ++ [4,5,6]
strings are lists of chars
[] is empty list
indexing: [1,2,3] !! 0 returns 1
head - first elem
tail - everything except first elem
last - last elem
init - everything except last elem
length
null [1,2,3] - checks if empty, true if do, false otherwise
reverse
take 3 [1,2,3,4] - returns the first n elems in list, in this case [1,2,3].  does not error if n > len
drop - returns the list skipping the first n elems.  does not error if n > len
maximum
minimum
sum
product
4 `elem` [1,2,3] returns True if n is in list.  False in this example
cycle [1,2] repeats the list forever: take 6 (cycle [1,2]) would give [1,2,1,2,1,2]
repeat 5 makes an infinite list of the given value, e.g. take 2 (repeat 5) would give [5,5]

# list comprehensions
[x * 2 | x <- [1..10]] - same as [x * 2 for x in range(1, 11)] in python 
[x * 2 | x <- [1..10], x `mod` 2 == 0] - same as [x * 2 for x in range(1,11) if x%2==0]
can have mulitple predicates separated with commas: [x * 2 | x <- [1..10], x `mod` 2 == 0, x /= 6]
can have multiple source lists, takes the product of both lists (e.g. two lists of length 4 will give a source of 16 values:
	[x * 2 | x <- [1,2,3,4], y <- [4,5,6,7]]

# tuples
fixed / known length
can contain different types
(1,2,"foo",False)
for Pairs:
	fst - like head
	snd - like last
zip - takes two lists and makes a list of Pairs (like python) (longer list is truncated in unequal)

# ranges
[1..4] gives [1,2,3,4]
['a'..'c'] gives ['a','b','c']
[2,4..20] gives all even numbers from 2 to 20.  difference between first two values is the step, in this case 4-2=2
reverse list needs a step, e.g. [20,19..1]
ranges are lazy, so can omit upper bound.  e.g. 10 multiples of 6: take 10 [6,12..]

# vars 
let a = "foo" - cannot be modified
_ is same as go - var which you won't use e.g. [1 | _ <- xs], returns a list of 1's as long as xs

# cons
: is the cons operator.  it's an infix
"a":"foo" returns "afoo"
same result as "a" ++ "foo" but lhs must be a single element of the same type as the rhs list.  ++ takes two lists

