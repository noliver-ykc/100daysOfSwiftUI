# How to use type annotations
So far we’ve been making constants and variables like this:

let surname = "Lasso"
var score = 0
This uses type inference: Swift infers that surname is a string because we’re assigning text to it, and then infers that score is an integer because we’re assigning a whole number to it.

Type annotations let us be explicit about what data types we want, and look like this:

let surname: String = "Lasso"
var score: Int = 0

sometimes you will want to choose a different type than what swift may automatically infer

var score: Double = 0
Without the : Double part Swift would infer that to be an integer, but we’re overriding that and saying it’s definitely a decimal number.

## data types review
this creates an array of strings:

var soda: [String] = ["Coke", "Pepsi", "Irn-Bru"]
Type annotation isn’t needed there, because Swift can see you’re assigning an array of strings. However, if you wanted to create an empty array of strings, you’d need to know the type:

var teams: [String] = [String]()

Some people prefer to use type annotation, then assign an empty array to it like this:

var cities: [String] = []
I prefer to use type inference as much as possible, so I’d write this:

var clues = [String]()

Values of an enum have the same type as the enum itself, so we could write something like this:

enum UIStyle {
    case light, dark, system
}

var style = UIStyle.light
This is what allows Swift to remove the enum name for future assignments, so we can write style = .dark – it knows any new value for style must be some kind UIStyle

if you can, try and use type inference as much as possible. Even if it means var score = 0.0 so that I get a Double

you can use type annotations best when you dont have an actual value for something yet:
let username: String
// lots of complex logic
username = "@twostraws"
// lots more complex logic
print(username)

Important: Although type annotation can let us override Swift’s type inference to a degree, our finished code must still be possible. For example, this is not allowed:

let score: Int = "Zero"