# how to store truth with booleans
let goodDog = true
var gameOver = false

print(gameOver.toggle()) // will print true

You can also use the (!) not.

goodDog = !goodDog
This will also toggle.

# how to join strings together
String concationation
let firstPart = "Hello, "
let secondPart = "world"
let greeting = firstPart + secondPart
print(greeting) // Hello, world

string interpolation

let name = "Taylor"
let age = 26
let message = "Hello, my name is \(name) and I'm \(age) years old."
print(message)

# summary
- Swift lets us create constants using let, and variables using var.
- Swift’s strings contain text, from short strings up to whole novels.
- You create strings by using double quotes at the start and end, but if you want your string to go over several lines you need to use three double quotes at the start and end.
- Swift calls its whole numbers integers, and they can be positive or negative.
- In Swift decimal numbers are called Double, short for double-length floating-point number. That means they can hold very large numbers if needed, but they also aren’t 100% accurate – you shouldn’t use them when 100% precision is required, such as when dealing with money.
- There are lots of built-in arithmetic operators, such as +, -, *, and /, along with the special compound assignment operators such as += that modify variables directly.
- You can represent a simple true or false state using a Boolean, which can be flipped using the ! operator or by calling toggle().
- String interpolation lets us place constants and variables into our strings in a streamlined, efficient way.
