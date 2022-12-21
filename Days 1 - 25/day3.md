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
