# how to check a condition is true
swift if statement

if someCondition {
    print("Do something")
}

if a user entered a name that comes after their friend’s name alphabetically, put the friend’s name first. You’ve seen how <, >= and others work great with numbers, but they also work equally well with strings right out of the box:

let ourName = "Dave Lister"
let friendName = "Arnold Rimmer"

if ourName < friendName {
    print("It's \(ourName) vs \(friendName)")
}

if ourName > friendName {
    print("It's \(friendName) vs \(ourName)")
}

Let’s take a look at our third example condition: if adding a number to an array makes it contain more than 3 items, remove the oldest one. You’ve already met append(), count, and remove(at:), so we can now put all three together with a condition like this:

// Make an array of 3 numbers
var numbers = [1, 2, 3]

// Add a 4th
numbers.append(4)

// If we have over 3 items
if numbers.count > 3 {
    // Remove the oldest number
    numbers.remove(at: 0)
}

// Display the result
print(numbers)

.count is too expensive, and so: 
Swift adds a second piece of functionality to all its strings, arrays, dictionaries, and sets: isEmpty. This will send back true if the thing you’re checking has nothing inside, and we can use it to fix our condition like this:

if username.isEmpty == true {
    username = "Anonymous"
}

# How to check multiple conditions

let a = false
let b = true

if a {
    print("Code to run if a is true")
} else if b {
    print("Code to run if a is false but b is true")
} else {
    print("Code to run if both a and b are false")
}

## enums if statements 
enum TransportOption {
    case airplane, helicopter, bicycle, car, scooter
}

let transport = TransportOption.airplane

if transport == .airplane || transport == .helicopter {
    print("Let's fly!")
} else if transport == .bicycle {
    print("I hope there's a bike path…")
} else if transport == .car {
    print("Time to get stuck in traffic.")
} else {
    print("I'm going to hire a scooter now!")

# How to use switch statements to check multiple conditions
switch forecast {
case .sun:
    print("It should be a nice day.")
case .rain:
    print("Pack an umbrella.")
case .wind:
    print("Wear something warm")
case .snow:
    print("School is cancelled.")
case .unknown:
    print("Our forecast generator is broken!")
}

 In the case of an enum, it knows all possible cases the enum can have, so if we miss one or check one twice it will complain.

 If you’ve ever used other programming languages, you might have noticed that Swift’s switch statement is different in two places:

All switch statements must be exhaustive, meaning that all possible values must be handled in there so you can’t leave one off by accident.
Swift will execute the first case that matches the condition you’re checking, but no more. Other languages often carry on executing other code from all subsequent cases, which is usually entirely the wrong default thing to do.

First, yes all switch statements must be exhaustive: you must ensure all possible values are covered. If you’re switching on a string then clearly it’s not possible to make an exhaustive check of all possible strings because there is an infinite number, so instead we need to provide a default case – code to run if none of the other cases match.

For example, we could switch over a string containing a place name:

let place = "Metropolis"

switch place {
case "Gotham":
    print("You're Batman!")
case "Mega-City One":
    print("You're Judge Dredd!")
case "Wakanda":
    print("You're Black Panther!")
default:
    print("Who are you?")
}

We can use fallthrough to run through multple behaviors:

let day = 5
print("My true love gave to me…")

switch day {
case 5:
    print("5 golden rings")
    fallthrough
case 4:
    print("4 calling birds")
    fallthrough
case 3:
    print("3 French hens")
    fallthrough
case 2:
    print("2 turtle doves")
    fallthrough
default:
    print("A partridge in a pear tree")
}
That will match the first case and print “5 golden rings”, but the fallthrough line means case 4 will execute and print “4 calling birds”, which in turn uses fallthrough again so that “3 French hens” is printed, and so on. It’s not a perfect match to the song, but at least you can see the functionality in action!