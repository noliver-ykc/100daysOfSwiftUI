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

# How to use sets for fast data lookup
Sets do not store order and may not contain duplicates
let people = Set(["Denzel Washington", "Tom Cruise", "Nicolas Cage", "Samuel L Jackson"])

and then print(people)
you could get denzel, tom sam, nick
or nick, denzel, tom, sam
or anyother combination every single time you run the code.
instead of thinking of sets as a line of data, its best to think of it as a bag.
there is no guarentee that everytime you pull out a name youll pull it all out in order

The second important difference when adding items to a set is visible when you add items individually. Here’s the code:

var people = Set<String>()
people.insert("Denzel Washington")
people.insert("Tom Cruise")
people.insert("Nicolas Cage")
people.insert("Samuel L Jackson")
Notice how we’re using insert()? When we had an array of strings, we added items by calling append(), but that name doesn’t make sense here – we aren’t adding an item to the end of the set, because the set will store the items in whatever order it wants.

sets specialize in FAST LOOKUP

# how to create and use enums

enums are basically like a drop down list of values.
enum Weekday {
  case monday
  case tuesday
  case wed
  case thru
  case fri
}
var day = Weekday.monday

you can only call Weekday.(something in the case list)
so you cant call Weekday.Sunday as that is not on the weeklist

you can shorten to this

enum Weekday {
  case monday, tuesday, wednesday, thursday, friday
}
var day = Weekday.monday
day = .tuesday
day = .friday
// day is initalized as a weekday so you dont need to write Weekday anymore.

theyre faster for swift to work with and free of human error ffrom us typing the code a billion times
