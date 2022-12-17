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
