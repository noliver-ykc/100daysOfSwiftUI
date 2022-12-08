# swift for complete beginners
 swift(2014) is apples original language while swiftui(2019) is the framework for it, mainly allowing it to draw things out and work with ui. 
________________
# about this course
file > new > playground > (ios== macOs) blank

MacOs playgrounds are the simplest and fastest ways to learn swift easily and thus we shall be using it for a good portion of the course.
_________________
# how to create variables and constants 
import Cocoa - importing the standard library similar to with C  

var is the standard changable variable generated automatically in playgrounds. 

var greeting = "Hello, playground" 
Swift does not require you to put a semi colon at the end. You can but... no reason to really. 

Constants in swift begin with the let keyword. 

let character = "Daphne"

To pring the contents of a variable wrap it like so ↓
print(playerName)

On the left side of the code where the line numbers are a blue play button should appear. Choose any amount of lines to play and use this to run your code in the terminal.
_________________
# How to create Strings
let result = "You win"

If you want "" to appear within your string, make sure to put double backslashes like so ↓
let quote = "Then he tapped a sign saying \"Believe\" and walked away."

For multiline strings you need three quotation marks↓
let movie = """
A day in
the life of an
Apple engineer
"""
＊Multiline strings arent actually used that often compared to single line

**Manipulating strings**
To print the length of a string you can use .count. 
let name = "Nicole"
print(name.count) // 5

Uppercase 
print(name.uppercased()) // NICOLE

*note about the parathesis, if youre asking to read data its not needed. if youre asking it to change data then it is needed (not always true)
let movie = "A day in the life"
print(movie.hasPrefix("A day")) // true
print(movie.hasSuffix("life")) // true

strings in swift are as with most languages case sensitive.
_________________
# How to store whole numbers
let store = 10

let bigNumb = 100_000_000
when writing long numbers in swift it is in convention to break apart using underscores which swift will ignore when reading

swift allows writing compand assignment operators such as: count += 2 or count /= 2

let number = 30
other cool built in function print(120.isMultiple(of: 3))
_________________
# Todays Takeaways 
- let keyword is used for constants, var keyword is used for variables.
- to print contents of a variable use: print(variableName)
- Swift variables are written in camel case.
- To include quotes inside of your string, write in the following format let quote = "Then he tapped a sign saying \"Believe\" and walked away."
- when writing long numbers in swift it is in convention to break apart using underscores which swift will ignore when reading
- swift allows writing compand assignment operators such as: count += 2

