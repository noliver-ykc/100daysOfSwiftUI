# how to store ordered data in arrays
var beatles = ["John", "Paul", "George", "Ringo"] // array of strings
let numbers = [4, 8, 15, 16, 23, 42] // array of integers
var temperatures = [25.3, 28.2, 26.4] // array of doubles

print(beatles[0]) // "John"
beatles.append("Adrian") // the swift version of .push

Swift is very heavily typed (type safety) so you cannot do
numbers.append("Bob")
Everything must be the same type in a singl array.

You also cant mix types like so ↓
let firstBeatle = beatles[0]
let firstNumber = numbers[0]
let notAllowed = firstBeatle + firstNumber

arrays are usually typed (specialized arrays), so even when you create an empty array it can be like this
var albums = Array<String>()

A simpler way to create an empty array is
var albums = [String]()

If you provide an inital value, swift will figure out the type based off that.

## some cool array tricks
var characters = ["Lana", "Pam", "Ray", "Sterling"]
print(characters.count)

characters.remove(at: 2)
print(characters.count)

characters.removeAll()
print(characters.count)

let bondMovies = ["Casino Royale", "Spectre", "No Time To Die"]
print(bondMovies.contains("Frozen"))

let cities = ["London", "Tokyo", "Rome", "Budapest"]
print(cities.sorted())

let presidents = ["Bush", "Obama", "Trump", "Biden"]
let reversedPresidents = presidents.reversed()
print(reversedPresidents) // ReversedCollection<Array<String>>(_base: ["Bush", "Obama", "Trump", "Biden"])
i dont really get .reversed
# how to store and find data in dictionaries
let employee2 = [
  "name": "Taylor Swift",
  "job": "Singer",
  "location": "Nashville"
]
name, job, location are keys and the other side are values.

print(employee2["name"])
print(employee2["job"])
print(employee2["location"])

However if your code is just like this youll get an error from xcode
along the lines of “Expression implicitly coerced from 'String?' to 'Any’”.

when you access data inside a dictionary, it will tell us “you might get a value back, but you might get back nothing at all.” Swift calls these optionals because the existence of data is optional - it might be there or it might not.

Swift will even warn you when you write the code, albeit in a rather obscure way – it will say “Expression implicitly coerced from 'String?' to 'Any’”, but it will really mean “this data might not actually be there – are you sure you want to print it?”

Optionals are a pretty complex issue that we’ll be covering in detail later on, but for now I’ll show you a simpler approach: when reading from a dictionary, you can provide a default value to use if the key doesn’t exist.

Here’s how that looks:

print(employee2["name", default: "Unknown"])
print(employee2["job", default: "Unknown"])
print(employee2["location", default: "Unknown"])

this way youll always get a string back, whether it be the actual value-- or the string unknown

unlike arrays, dictionaries are not typed
let hasGraduated = [
  "Eric": false,
  "Maeve": true,
  "Otis": false,
]

let olympics = [
  2012: "London",
  2016: "Rio de Janeiro",
  2021: "Tokyo"
]

print(olympics[2012, default: "Unknown"])

var heights = [String: Int]()
heights["Yao Ming"] = 229
heights["Shaquille O'Neal"] = 216
heights["LeBron James"] = 206

you can also overwrite dictionaries as you see fit
var archEnemies = [String: String]()
archEnemies["Batman"] = "The Joker"
archEnemies["Superman"] = "Lex Luthor"

archEnemies["Batman"] = "Penguin"
