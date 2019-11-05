# Lesson 10 - Parameters and Results

# Exercise: Verbing Your Noun

Remember back to the Functions playground when you rewrote “Row, row, row your boat”? In that playground, the functions were all very specific. To change the first line of the verse, you had to rewrite the function.

Functions that can take arguments can be much more general.

## Exercise

Write a function that returns a sentence like “Row, row, row your boat” when given a verb and a noun argument. The function should look like this when you call it:
 ```let line = openingLine(verb: "Row", noun: "Boat")```
 
 ```swift
 func openingLine(verb: String, noun: String) -> String {
    return "\(verb), \(verb), \(verb), your \(noun)"
}

let line = openingLine(verb: "drive", noun: "car")
print(line)

// Output: drive, drive, drive, your car
```

# Exercise: Using Return Values

You’ve learned that functions are the building blocks of programs, but so far you’ve mostly used functions one at a time. In this exercise, you'll use the results of one function to influence the work that's done by another.

The function ```impossibleBeliefsCount``` takes several numbers of reported unlikely incidents. It then prints the number of impossible things to be believed:

```swift
func impossibleBeliefsCount(pigsFlying: Int, frogsBecomingPrinces: Int, multipleLightningStrikes: Int) -> Int {
    let total = pigsFlying + frogsBecomingPrinces + multipleLightningStrikes
    return total
}
```

## Exercise

Update the ```impossibleBeliefsCount``` function so that instead of printing the value, it returns it as an Int.

```impossibleThingsPhrase``` creates a phrase using string interpolation:

```swift
func impossibleThingsPhrase(numberOfImpossibleThings: Int, meal: String) -> String {
    return "Why, I've believed as many as \(numberOfImpossibleThings) before \(meal)"
}
```

## Exercise
Update the ```impossibleThingsPhrase``` function so that, instead of using its two internal constants, it takes two arguments: ```numberOfImpossibleThings``` as an ```Int``` and ```meal``` as a ```String```.
Now you have two functions that take parameters and return values.

## Exercise
Call ```impossibleBeliefsCount``` and store the result in a constant.
Call ```impossibleThingsPhrase```, passing in the result of ```impossibleBeliefsCount``` as one of the arguments.

```swift
let numberOfBeliefs = impossibleBeliefsCount(pigsFlying: 5, frogsBecomingPrinces: 6, multipleLightningStrikes: 7)
let phrase = impossibleThingsPhrase(numberOfImpossibleThings: numberOfBeliefs, meal: "supper")
print(phrase)
```

# Exercise: Argument Label

Functions and their arguments should be named so that they read like a clear instruction when they’re called. To make this easier, you can give parameters two names - an argument label to be used when calling the function and a parameter name to be used within the function’s body.

```swift 
func score(withReds reds: Int, greens: Int, golds: Int) -> Int {
    let pointsPerRed = 5
    let pointsPerGreen = 10
    let pointsPerGold = 30
    
    let redScore = reds * pointsPerRed
    let greenScore = greens * pointsPerGreen
    let goldScore = golds * pointsPerGold
    
    return redScore + greenScore + goldScore
}
let finalScore = score(withReds: 5, greens: 3, golds: 3)
```

## Exercise
Add an argument label to the function definition so it reads like this when you call it:
 ```let finalScore = score(withReds: 5, greens: 3, golds: 3)```
 
# Exercise: No Argument Label

Some functions names are descriptive enough that they don’t need a label for their argument. To write a function that can be called with an argument only, you use _ where you'd normally specify the argument label.

The function below has an unnecessary argument label when you call it.

```swift
func holler(_ phrase: String) -> String {
    return "⚡️\(phrase)!!⚡️"
}

holler("Thank you, this is very nice.")
holler("I'm not sure that was necessary.")
```
