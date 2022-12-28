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

## enums case 
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