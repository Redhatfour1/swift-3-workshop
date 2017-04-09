<<<<<<< HEAD
## Lab-1-prework  
#### 1. Open the `CFS3ToDoList.xcodeproj` using Xcode 8, provided in this repository.  
#### 2. Ensure in Xcode that you are on the **lab-1** branch.  
![Imgur](http://i.imgur.com/3hl3ne1.png)  
#### 3. In the `CFS3ToDoList` folder on the left, click on `Swift3Workshop.playground`.  

## Lab-1  
## Constants and Variables  
> Use `let` to make a constant and `var` to make a variable.  
The value of a constant doesn’t need to be known at compile time, but you must assign it a value exactly once.  
This means you can use constants to name a value that you determine once but use in many places.  



#### 1. In `Swift3Workshop.playground`, under `//Constants and Variables`. Type the following:  
```swift
var myVariable = 42
myVariable = 50
```  
This is creating a variable in Swift. This variable is mutable, meaning we can change the value that is assigned to it.  

#### 2. Next, we will declare a constant, meaning it's value cannot be changed or mutated.  
```swift
let myConstant = 4
myConstant = 10
```  

**Note the error we get:**  
![Imgur](http://i.imgur.com/wPWExau.png)  
What does the error say?  
> If you can't see the error details, click on the red error to the left of the line numbers. This will show a short description of the error.  

Remove `myConstant = 10` to clear the error.  

> As an iOS Developer, one of the best practices we follow is that every value we declare should start as a `let` constant. If you need to change the value, go back and make it a `var` declaration when needed.  This helps to make sure you never accidentally have a value change, or unnecessarily change a value that you did not intend to.  

## Type Inference  
> Note: You don’t always have to write types explicitly. Providing a value when you create a constant or variable lets the compiler infer its type. In the example above, the compiler infers that myVariable and myConstant are integers because their initial values are integers.  

In the playground, below the above code, Add the following:  
```swift
let myName : String = "Adam"
```  
Notice that this is how you explicitly tell the compiler that `myName` is a String. This is not necessary in this case because the compiler can infer that this is a String based off of the initial value we give it. Change the above line to the following:  
```swift
let myName = "Adam"
```  

This works great most of the time. But, be aware that the compiler cannot ALWAYS make this inference accurately. In some situations, we will need to explicitly say what type a value has. We will see this later in lab.  

## Numeric Types  
### Integers  
> Note: Integers are whole numbers with no fractional component, such as 42 and -23. Integers are either signed (positive, zero, or negative) or unsigned (positive or zero).  

> Note: Swift provides signed and unsigned integers in 8, 16, 32, and 64 bit forms. These integers follow a naming convention similar to C, in that an 8-bit unsigned integer is of type UInt8, and a 32-bit signed integer is of type Int32. Like all types in Swift, these integer types have capitalized names.  

1. Under `//Numeric Type` in our playground, write the following: 
```swift
let minValue = UInt8.min
let maxValue = UInt8.max
```  
This will show you the max and min values of the `UInt8` type.  

> In most cases, you don’t need to pick a specific size of integer to use in your code. Swift provides an additional integer type, Int, which has the same size as the current platform’s native word size:

  > On a 32-bit platform, Int is the same size as Int32.  
  > On a 64-bit platform, Int is the same size as Int64.  

> Unless you need to work with a specific size of integer, always use Int for integer values in your code. This aids code consistency and interoperability. Even on 32-bit platforms, Int can store any value between -2,147,483,648 and 2,147,483,647, and is large enough for many integer ranges.

### Floating Point Values  
> Note: In Swift 3, `Double` represents a 64-bit floating-point number.
`Float` represents a 32-bit floating-point number. Double has a precision of at least 15 decimal digits, whereas the precision of Float can be as little as 6 decimal digits.  

> The appropriate floating-point type to use depends on the nature and range of values you need to work with in your code. In situations where either type would be appropriate, Double is preferred.  

To give examples of the accuracy of `Double` and `Float`, add the following 2 lines underneath the above code:  
```swift
let myFloat : Float = 1.234937
let myDouble : Double = 1.234937987231234
```  

Your playground should now look similar to the following:  
![Imgur](http://i.imgur.com/MTLA3M1.png)  

Play with the above values for a moment to get a feel for the accuracy of both.  

## Strings  
> Note: A string is a series of characters, such as "hello, world" or "albatross". Swift strings are represented by the String type. The contents of a String can be accessed in various ways, including as a collection of Character values.

In Playground, under `//String`, type the following:  
```swift
let someString = "Some string literal value"
```  
Remember, the above is inferred by the compiler to be a String.  
To initialize an empty String, you can do either of the following:  
```swift
var emptyString = ""
var anotherEmptyString = String()
```  
The 2nd uses the designated initializer of the `String()` type.  
More on this later.  

You can also use basic operators on String types to create new Strings.  
In your playground, add the following:  
```swift
let firstName = "Adam"
let lastName = "Wallraff"

var fullName : String

fullName = firstName + " " + lastName
```  

There are many other powerful operations for String manipulation to look into. Check out the documentation here: [Swift 3 Programming Guide - Strings](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/StringsAndCharacters.html)  
## Tuples  
> Note: A tuple is a type that represents data composed of more than one value of any type. Use a tuple to make a compound value—for example, to return multiple values from a function. The elements of a tuple can be referred to either by name or by number.  

In playground, under `//Tuples`, type the following:  
```swift
let tuple = (description: "Not Found", code: 401)
```  
Then access values in the tuple with the following:  
```swift
tuple.description
```

## Collection Types  
> Great resource for Collection Types: [Here](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/CollectionTypes.html)  

### Sets  
> A set is an unordered collection of unique values of the same type. It can be extremely useful when you want to ensure that an item doesn't appear more than once in your collection, and the order of your items isn't important. Sets also do not have type inference. You **must** be explicit when declaring `Set` types.  

In playground, under `//Set`, type the following:  
```swift
let set: Set = [1, 2, 3, 4]
```

> Note: One of the most powerful features of sets is their support of set operations, which let you combine two sets into one, create a set with only the common values of two sets, and more. 

Here are some of the more powerful `Set` operations to research:
* union(_:) `creates a new set with all the values of the two sets`  
* intersection(_:) `creates a new set with only the values contained in both sets`  
* subtract(_:) `creates a new set by removing values that appear in the second set`  
* symmetricDifference(_:) `creates a new set with the values that appear in both of the sets, without duplicates`  

Back in our playground, write the following underneath the above `let set: Set = [1, 2, 3, 4]
`:  
```swift
let setB: Set = [1,9,8,4,2,8]
```  

Then, observe what happens when we do the following:
```swift
let result = set.intersection(setB)
```  

As you may have guessed from the result on the right, this produced a brand new `Set` with only the values that both sets contain in common.  

Take a moment to try the other `Set` methods.  

> For more information on these operations, visit the provided link to [Collection Types](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/CollectionTypes.html)  

### Arrays  
> An array is an ordered collection of values of the same type. The elements in the array are zero-indexed, which means the index of the first element is 0. Arrays are useful when you want to store your items in a particular order.  

In our playground, let's create a few different arrays in a few different ways!  
Write the following underneath `//Array`:  
```swift
let stringsArray = [String]()
let planetArray = ["Mars", “Jupiter"]
var intArray = [Int](repeating: 0, count: 5)
```  

> Note: You can also make all kinds of changes to mutable arrays: adding and removing elements, updating existing values, and moving elements around into a different order.

Let's make some changes to the `intArray`  
Add the following below the above declaration:  
```swift
intArray.append(100)
intArray.append(10)
intArray.insert(1000, at: 0)
```  
> Note: The above `insert(_:at:)` function inserts the value of `1000` at index: 0. Index 0 is referencing the first object in the array. Indexes always start at 0 and increase for each object in the array.

Now that we've added some additional values, lets remove the `10` we added:  
```swift
intArray.remove(at: 7)
```  

> This not only removes the object at the specified index, but returns the value being removed in case the developer wants to do anything else with the removed value. 

Let's change the above line to allow us to store the value we removed from the array.  
Change the above line to the following:  
```swift
let removedValue = intArray.remove(at: 7)
```  

> Note: It is also good practice to make sure you never try to access a value that is "Out of Range". If you ever see a crash or error regarding this, this means that you have tried to access a value at an index that doesn't exist.  

Your playground should, by this point, look similar to the following:  
![Imgur](http://i.imgur.com/UoXLvie.png)  

### Dictionaries  
> A dictionary is an unordered collection of pairs, where each pair is comprised of a key and a value. Dictionaries are useful when you want to look up values by means of an identifier. The same key can't appear twice in a dictionary, but different keys may point to the same value. All keys have to be of the same type and all values have to be of the same type.

Let's take a look at how to declare a dictionary.  
In your playground, underneath the `//Dictionary` comment, add:
```swift
let dictionaryOne = [String : String]()
var dictionaryTwo = ["name" : "Mars"]
```  
Note that both of these lines declare a dictionary of type `[String: String]`.  

The primary difference again being that the second dictionary has a starting value and the first is created but empty.  
With the `let` declaration making the first dictionary immutable, this makes the first dictionary pretty useless...  

Just as we saw with arrays, we can add new values to mutable dictionaries.  
Try this following the above declaration:
```swift
dictionaryTwo["location"] =  "Home"
```  
The above line adds a new *key* to `dictionaryTwo` called "location" and sets its value to be the String "Home".  

This is great, but Mars isn't our home...At least for most of us.  
So let's change the value for the "Name" key.  
We do this by adding the following line:  
```swift
dictionaryTwo["name"] =  "Earth"
```  

> There are some very powerful uses for dictionaries. For more information of what they are capable of doing and what other methods they have, check out Apple's documentation here: [Dictionaries](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/CollectionTypes.html)  

## Control Flow  
> Swift provides a variety of control flow statements. These include `while` loops, `if` statements, `switch` statements, and more to execute different branches of code based on certain conditions.

> Swift also provides a `for-in` loop that makes it easy to iterate over arrays, dictionaries, ranges, strings, and other sequences.

### For-In Loops  
> Note: You use the for-in loop to iterate over a sequence, such as ranges of numbers, items in an array, or characters in a string. Swift 3 deprecated the traditional `for i` for loop.  

Let's start by declaring a simple for loop that loops 5 times.
In our playground, beneath the `//For-In Loop` line, let's add:
```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
```  

We can see that our loop runs 5 times and multiplies the `index` value by 5 each time.  
We will talk more about the `...` a little later.  

But now let's loop over the objects in one of our arrays from earlier.  
Under the above `for-in` loop, type the following:  
```swift
for value in intArray{
    print(value)
}
```  
As we can see in the console, this is looping through each number held in our `intArray`.  

Your playground should resemble the following:  
![Imgur](http://i.imgur.com/lVFLp4G.png)  

For dictionaries, we can loop through and get a reference to both the *key* and *value*. Remember though that dictionaries are not sorted.  


Below our previous loop, let's practice this by looping through our `dictionaryTwo`:  
```swift
for (key, value) in dictionaryTwo{
    print("Key: \(key), Value: \(value)")
}
```  

We can see that our matching keys and values are printed to the console.  

### While Loops and Repeat While  
> A while loop performs a set of statements until a condition becomes false. These kinds of loops are best used when the number of iterations is not known before the first iteration begins. Swift provides two kinds of while loops.

1. `while` evaluates its condition at the start of each pass through the loop.  
2. `repeat-while` evaluates its condition at the end of each pass through the loop.  

In playground, let's find the section labeled `//While Loop`.  
Then we can write the following:  
```swift
var counter = 1

while counter <= 100 {
    //do some stuff
    counter += 1
}
```  

`repeat-while` loops are exactly the same as `while` with one exception.  
`repeat-while` loops will **always** execute the code they contain at least once.  

Let's try this.  
Underneath the `//Repeat While` type:
```swift
var repeatCount = 100

repeat{
    print("This will print at least once.")
}while repeatCount < 10
```  
As you can see, `repeatCount` starts with a value well over 10, which is the condition of the loop. But we still get one execution of the code inside the repeat statement scope.  

### If Statements  
> If statements in Swift are very much like `if` statements in other languages. In its simplest form, the if statement has a single if condition. It executes a set of statements only if that condition is true.  

We will try a quick exaple of this.  
In our playground, underneath `//If Statement`, insert the following code:  
```swift
var temperatureInFahrenheit = 30
if temperatureInFahrenheit <= 32 {
    print("It's very cold. Consider wearing a scarf.")
}
```  

Now, let's change ` temperatureInFahrenheit` to be:  
```swift
var temperatureInFahrenheit = 50
```  
And we will add a simple else statement, making our if statement look like this:  
```swift
if temperatureInFahrenheit <= 32 {
    print("It's very cold. Consider wearing a scarf.")
} else {
    print("It's not that cold. Wear a t-shirt.")
}
```  

We can also additionally have `else if` statements that allow us to handle other specific situations. Let's add one to the above if.  

Change the above `if` statement to the following:  
```swift
if temperatureInFahrenheit <= 32 {
    print("It's very cold. Consider wearing a scarf.")
} else if temperatureInFahrenheit == 0{
    print("It's way too cold! Get inside!")
} else {
    print("It's not that cold. Wear a t-shirt.")
}
```  
Now, if we manipulate the `temperatureInFahrenheit` value, we can see it handles each of our situations.  

### Switch Statements  
> Swift’s switch statement is considerably more powerful than its counterpart in many C-like languages. Because the cases of a switch statement do not fall through to the next case in Swift, it avoids common C errors caused by missing break statements.  
> A switch statement considers a value and compares it against several possible matching patterns. It then executes an appropriate block of code, based on the first pattern that matches successfully. A switch statement provides an alternative to the if statement for responding to multiple potential states.  

> NOTE: All Switch statements must be exhaustive. This means that a majority of the time, you will need to account for a `default` case. As we will in the following demo.  

Every switch statement consists of multiple possible cases, each of which begins with the `case` keyword.  

let's start with a simple switch over a character.  
In our playground, underneath `//Switch Statement`, add:  
```swift
let someCharacter: Character = "z"
switch someCharacter {
case "a":
    print("The first letter of the alphabet")
case "z":
    print("The last letter of the alphabet")
default:
    print("Some other character")
}
```  

#### Ranges  
Ranges allow developers to specify a range. Let's take a look.  

Underneath the above `switch` statement, let's add:
```swift
let approximateCount = 12

let countDescription : String

switch approximateCount {
case 0:
    countDescription = "none"
case 1...5:
    countDescription = "a few"
case 5..<12:
    countDescription = "several"
case 12, 24, 36, 48:
    countDescription = "dozens of"
case 100..<1000:
    countDescription = "hundreds of"
default:
    countDescription = "unknown"
}
```  

Notice in the above `switch` statement, we can handle lots of different kinds of cases.  

`case 12, 24, 36, 48:` shows that we can chain together different values and assign them the same functionality.  

Range types:
* `..<` - This range goes from the left value up to the right value, but noninclusive of the right value.  
* `...` - Same as above but **inclusive** of the right value.  

Following the above code, let's switch over a tuple.  
```swift
let somePoint = (1, 1)

switch somePoint {
case (0, 0):
    print("(0, 0) is at the origin")
case (_, 0):
    print("(\(somePoint.0), 0) is on the x-axis")
case (0, _):
    print("(0, \(somePoint.1)) is on the y-axis")
case (-2...2, -2...2):
    print("(\(somePoint.0), \(somePoint.1)) is inside the box")
default:
    print("(\(somePoint.0), \(somePoint.1)) is outside of the box")
}
```  

Notice that in the above switch, we access the values inside the tuple with a `.0` or `.1`. If you don't give default names to these parameters, this is how you would have to access them.  

We can also restructure the above switch to make it easier to understand by changing it to the following:
```swift
let somePoint = (x: 1,y: 1)

switch somePoint {
case (0, 0):
    print("(0, 0) is at the origin")
case (_, 0):
    print("(\(somePoint.x), 0) is on the x-axis")
case (0, _):
    print("(0, \(somePoint.y)) is on the y-axis")
case (-2...2, -2...2):
    print("(\(somePoint.x), \(somePoint.y)) is inside the box")
default:
    print("(\(somePoint.x), \(somePoint.y)) is outside of the box")
}
```  

By giving the tuple named parameters, we can access these parameters as we would expect.  

At this point, your playground should look something like this:  
![Imgur](http://i.imgur.com/62zC1fy.png)  

## Optionals  
> Optionals can be tricky, for more information I would recommend reading Apple's documentation on optionals [Here](https://developer.apple.com/reference/swift/optional).  

> Swift introduced optional types, which handle the absence of a value. Optionals say either “there is a value, and it equals x” or “there isn’t a value at all”. Using optionals is similar to using nil with pointers in Objective-C, but they work for any type, not just classes. Not only are optionals safer and more expressive than nil pointers in Objective-C, they are at the heart of many of Swift’s most powerful features.

> You use optionals in situations where a value may be absent. An optional represents two possibilities: Either there is a value, and you can unwrap the optional to access that value, or there isn’t a value at all.  

Navigate to the `//Optionals` portion of our playground.  

We can define an optional String type here:
```swift
var surveyAnswer: String?
```  

Then, we can implement the following `if` statement to check if the value is `nil`:  
```swift
if surveyAnswer != nil{
    print("SurveyAnswer is not nil.")
}
```  
In our case, the value is nil because we never assigned it to a specific value.  
Lets change that.  

beteen the declaration of `var surveyAnswer: String?` and our `if` statement, lets assign a value to surveyAnswer:
```swift
surveyAnswer = "This was so much fun!!!"
```  

Your if statement should now hit and should show `SurveyAnswer is not nil.` on the right like so:
![Imgur](http://i.imgur.com/spAuwpw.png)  

#### Optional Binding  
> You use optional binding to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. Optional binding can be used with if and while statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action.  

So, we can "unwrap" our optionals, by adding the following statement to the bottom of our playground:

```swift
if let surveyAnswer = surveyAnswer{
    print(surveyAnswer)
}
```  
The above basically says if I can unwrap this value, then let me use it as a non-optional within the scope of the `if` statement.  

If this value is nil, the `if let` statement is passed over.  

#### Coding Challenges
> If you have extra time, here are some good challenges to attempt on your own. Please hold any questions related to these challenges till the end of the day to allow instructors to keep pace for the day.  

1. Declare an array of strings containing all the names of the planets within our solar system. Create a for loop to iterate over each planet name. Inside the for loop, write an if statement that checks if the array contains a value for "Earth". If it does, print("YAY Earth!").  

2. Declare a tuple that can hold 4 values. These values should be called `x`, `y`, `width`, and `height`. Then write a corresponding switch statement to handle different cases of this tuple.  

3. Declare a Dictionary of type `[Int: String]`. Give it some default values. Then, remove a value for a specific key. Lastly, once the value has been removed, print the count of objects in the Dictionary to the console. This will take some research.  

## Before Continuing
#### 1. With the `CFS3ToDoList.xcodeproj` open in Xcode, go to the top menu bar and select source control.  
#### 2. Select `commit` to commit the work you have done up to this point.  
#### 3. Make sure to leave a detailed commit message for yourself.  
#### 4. Once you have commited your changes, go back to the Source Control menu.
#### 5. Hover over your project and select `Switch to Branch`.  
#### 6. Select Lab-2. You may see all the lab-1 code jump into the project.  
  > This is to ensure that all participants can keep pace with the workshop.  
  
=======
## Lab-2-prework  
#### 1. Ensure in Xcode that you are on the **lab-2** branch.  
#### 2. Click on `Swift3Workshop.playground` on the left.  
#### 3. Navigate to the section labeled with `//-----LAB-2-----//`  
## Lab-2  

## Classes & Structs  
> NOTE: When talking about the differences between classes and structs. The **primary** difference is that one is a data type and one is a reference type. A data type is created once and then copied when assigned to other variables. A reference type means that if you assign a value to another variable, both variables are technically pointing to the same object in memory. This will make more sense as we start to code.

### Structures  
> Structures, or structs, are one of the named types in Swift that allow you to encapsulate related properties and behaviors. You can define it, give it a name and then use it in your code.  

> Examples of good candidates for structures include:  
* The size of a geometric shape, perhaps encapsulating a width property and a height property, both of type Double.  
* A way to refer to ranges within a series, perhaps encapsulating a start property and a length property, both of type Int.  
* A point in a 3D coordinate system, perhaps encapsulating x, y and z properties, each of type Double.  

> In all other cases, define a class, and create instances of that class to be managed and passed by reference. In practice, this means that most custom data constructs should be classes, not structures.  

In our playground, find the `//Classes and Structs` line.  
Let's start by defining a simple `struct`.  
```swift
struct ScreenLocation{  
    var x: Int
    var y: Int
}
```  

Now we can test creating a new instance of this `ScreenLocation` struct.  
Directly underneath the above declaration add:  
```swift
let location = ScreenLocation(x: 0, y: 0)
```  

> As mentioned earlier, we can see the copy on assignment by assigning our new location to another location.  

Under the above line add the following:  
```swift
var location2 = location
location2.x = 10

location2.x
location.x
```  

Your playground should now appear like the following:  
![Imgur](http://i.imgur.com/pzLERtw.png)  

It won't be apparent until we take a look at implementing classes, but structs, when assigned, create a copy. This is why we see that the 2 screen locations have different `x` values. This is what we would expect in this case.  

> Also note that structs give us a "free" initializer. We will discuss initializers in more detail in a moment.  

### Classes  
> Classes are much like structures - they are named types, have stored properties and can define their own methods/functions. Classes are reference types instead of value types. They have substantially different capabilities than structures.  

Below the above struct exercise, lets add a new class:
```swift
class Person{
    var name: String
    var age: Int
}
```  

> Note that we get an **ERROR**. This is because with classes, we don't get a default initializer for "free". We are responsible for implementing the initializer ourselves.  

Change the above `Person` class to add the following `init` function:
```swift
class Person{
    
    var name: String
    var age: Int
    
    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }
    
}
```  

The function that we have added is the `Person` initializer. This is what is called when a new instance of this object is created, or **initialized**. We will talk more about functions later.  

> Note the use of `self` here. `self` in this context is referencing the new instance of this class. `self` is similar to `this` in JavaScript.

Now, let's take a look at creating a new instance of our `Person` class.  
Under the above `Person` class declaration add the following:  
```swift
let myPerson = Person(name: "Adam", age: 30)
```  

We can do some powerful things with initializers. Let's try changing the above `init(name: String, age: Int)` to the following:
```swift
class Person{
    
    var name: String
    var age: Int
    
    init(name: String, age: Int = 0) {
        self.name = name
        self.age = age
    }
    
}
```  

We have now added a default value to `age`. This means when creating new `Person` instances, we have 2 initializers built into 1. We can optionally create a `Person` with a `name` and `age`, or conversly, we can create a new `Person` with just a `name`, and the `age` would default to 0.  

We can test this by adding creating another instance of `Person`:
```swift
let myFriend = Person(name: "Joe")
```  

Your playground should look similar to this:  
![Imgur](http://i.imgur.com/yUVoJO8.png)  

We can now see that we have 2 initializers made from the implementation of 1.  

Again, we discussed how classes are **Reference** types. To demonstrate this we can do the following.  

Beneath the declaration of `myFriend`, add:
```swift
var otherPerson = myPerson

otherPerson.age = 100
myPerson.age
```  

We can now see on the right that `myPerson.age` gives us 100.  This is because when we created `otherPerson` and assigned it to `myPerson`, instead of making a new "copy" like our struct did, it assigned a new **reference** to `myPerson` called `otherPerson`. This means that both variables are pointing to the same object in memory, so if you change one, it affects both.  

> Note: This **copy** vs **reference** concept is important to keep in mind when designing your objects. If you don't pay attention to this, you can end up with issues where you are changing objects values that are not intended to be changed.  

## Protocols  
> Swift protocols define a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. The protocol can then be adopted by a class, structure, or enumeration to provide an actual implementation of those requirements. Any type that satisfies the requirements of a protocol is said to conform to that protocol.  

> Protocols allow us to create a kind of list of "rules" that any type adopting the protocol has to follow or implement. A way to define an interface or a template for an actual concrete type such as a struct or class or enumeration. With a protocol, you can define a common set of behaviors and then define the actual types that implement them.  

A great resource for Protocols: [Apple Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Protocols.html)  

In our playground, find the line that reads `//Protocols`.  
Now, create the following protocol:  
```swift
protocol DogYears{
    var age : Int { set get }
    
    func ageInDogYears() -> Int
}
```  

> This protocol specifies that it requires a function called `ageInDogYears` to be implemented. This means any type that conforms to this protocol needs to implement this function.  

> This protocol also specifies a required variable called `age`. To look more into variables and constants in your protocols, I recommend reading the Apple Documentation for protocols here: [Apple Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Protocols.html#//apple_ref/doc/uid/TP40014097-CH25-ID267).  

> We will get to more on functions later.  

Now, below the above protocol, we can create a new class.  
Let's try the following:  
```swift
class Dog: DogYears{
    
}
```  
Notice the error that we get. This is because we have not yet implemented the method/function required by the `DogYears` protocol.  

Let's get the dog class to conform to the protocol.  
Change the `Dog` class to the following:  
```swift
class Dog: DogYears{
    
    var age = 1
    
    func ageInDogYears() -> Int {
        return age * 7
    }
}
```  

If you haven't already, notice that as you type, Xcode gives us a nice auto complete:  
![Imgur](http://i.imgur.com/C0JNYs8.png)  

This is a great tool to take advantage of as much as possible. To go with the auto complete suggestions, just simply press `Enter` when you have the method you want highlighted.  

> We will see how we can have very powerful and dynamic protocols through extensions in a little bit.  

## Inheritance  
> An important concept to understand when developing in Swift is **Inheritance**. Inheritance allows us to create complex objects that inherit functionality from a `superClass`. 

Let's take a quick look at our `Person` class.  
Now lets create a subclass of `Person` called `Student`.  
`Student` will inherit the properties and methods of its superClass `Person`.  

Find the `//Inheritance` line.  
Beneath it add the following:  
```swift
class Student: Person{
    
    var studentID: String?
    var classNumber: Int?
    
}
```  

This has just created a new Type called `Student`.  
Now let's create an instance of a `Student`:  
```swift
let student1 = Student(name: "Mike")
```  

We can also now assign the `studentID` and `classNumber` we added to the class.  
```swift
student1.classNumber = 401
student1.studentID = "s786sf67822g29"
```  

> It is important to know that in Swift there is a rule of **Single Inheritance**, meaning that an object can only have 1 superClass. But, we can continue to extend the functionality of objects using protocols and extensions(we will cover shortly).  

Let's make our new `Student` class conform to the `DogYears` protocol.  
Change your above implementation of the `Student` class to the following:  
```swift
class Student: Person, DogYears{
    
    var studentID: String?
    var classNumber: Int?
    
    func ageInDogYears() -> Int {
        return age * 7
    }
}
```  

Your playground should now look like this:  
![Imgur](http://i.imgur.com/Fz2vsrr.png)  

> Note that inside the `ageInDogYears` function, we can access a property called `age`. This is because of the inheritance of `Student` from `Person`. `Person` has a property called `age` and because `Student` inherits from `Person`, `Student` also has an `age` property.  

## Extensions  
> Extensions add new functionality to an existing class, structure, enumeration, or protocol type. This includes the ability to extend types for which you do not have access to the original source code (known as retroactive modeling). Extensions are similar to categories in Objective-C.  

For more information on Extensions, read: [Apple Documentation - Extensions](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Extensions.html#//apple_ref/doc/uid/TP40014097-CH24-ID151)  

> So, you may have noticed, but with our `DogYears` protocol, we implemented the `ageInDogYears` function in both our `Student` and `Dog` class. One of the big benefits to extensions is that we can give our protocols default implementation. This means that if we wanted, we could make `ageInDogYears` not required. Then, any object that conforms to the `DogYears` protocol would have the functionality of `ageInDogYears` by default, unless they chose to implement it differently.  

Back in our playground, find the `DogYears` protocol declaration and add the following:  
```swift
extension DogYears {
    func ageInDogYears() -> Int{
        return age * 7
    }
}
```  

Now we can remove the function from our `Student` class and `Dog` class.  

At this point, your playground should look similar to this:  
![Imgur](http://i.imgur.com/7rAtLgD.png)  

> Note that either of the classes comforming to the `DogYears` protocol could reimplement the method to change its functionality.

We can also use Extensions to extend classes that are not directly available to us.    

In our playground, find the line `//Extension` and add the following:  
```swift
extension String{
    
    func length()-> Int{
        return self.characters.count
    }
    
}
```    

Now we can try using our extension with the following:  
```swift
let myString = "This is a test string"
myString.length()
```  

## Functions  
> Functions are self-contained chunks of code that perform a specific task. You give a function a name that identifies what it does, and this name is used to “call” the function to perform its task when needed. A function lets you define a block of code that performs a given task. Functions take can take in parameters and can return values.  

> As we've already seen, you define a function using the `func` keyword. After that comes the name of the function, followed by `()`. After the parentheses comes an opening brace, followed by the code you want to run in the function, followed by a closing brace.

> You can give your function parameters, which lets the function perform differently depending on the data passed into it via its parameters. Functions can also return a value. The caller of the function can assign the return value to a variable or constant.

In the playground, find the line `//Functions`.  
Here, we can define the following function:  
```swift
func greet(person: String) -> String {
    let greeting = "Hello, " + person + "!"
    return greeting
}
```  

We can then test using our function with the following:  
```swift
greet(person: "Errbody")
```

> Functions can have default parameter values similar to what we did earlier with our initializer.  

Change your function to look like this:
```swift
func greet(person: String = "Errbody") -> String {
    let greeting = "Hello, " + person + "!"
    return greeting
}
```  
We can see that there are now 2 ways to call this function by giving it a try.  
Change `greet(person: "Errbody")` to:
```swift
greet(person: "Adam")
greet()
```  

Your playground should look something like this:  
![Imgur](http://i.imgur.com/CgeiCQh.png)  

As you can see, we now have 2 independant ways of calling our `greet()` function.  

> Along with default parameter values, we can also use something called **Variadic Parameters**.

Under the above `greet()` line of code in our playground, write the following:  
```swift
func addThese(numbers: Int...)-> Int{
    
    var total = 0
    
    for number in numbers{
        total += number
    }
    
    return total
}
```

Now we can use this function underneath the declaration as follows:  
```swift
addThese(numbers: 0,1,2,3,4,5)
```  

We should see a 15 on the left like so:  
![Imgur](http://i.imgur.com/Q2IHFyT.png)  

> Functions can also be passed into other functions allowing us to create some new functionality to our programs.  

In our playground, under the `addThese(numbers: 0,1,2,3,4,5)` line above, add the following:  
```swift
func changeStuff(number: Int, callback:(Int)->()){
    callback(number * number)
}
```  
Then, to use the function, we call it like this:  
![Imgur](http://i.imgur.com/zkOql60.png)  

Using auto complete to complete the function call, you should see something like this:  
![Imgur](http://i.imgur.com/nmJ1hzU.png)  

Now, with the `(Int)->()` highlighted, press enter.  
This should "open" the callback function into a closure.  

Your playground should look like this before moving forward:  
![Imgur](http://i.imgur.com/xUl1UOd.png)  

## Closures  
> Closures are a difficult concept to understand for new Swift developers. A closure is really just a function with no name. You can assign them to variables and pass them around like any other value.  

> Closures are so named because they have the ability to "close over" the variables and constants within the closure's own scope. This simply means that if a closure wants to access, store and manipulate the value of any variable or constant from the surrounding context, it can.  

In the last screenshot above, we can see what a closure looks like.  
Back in our playground, move the following code to be underneath the `//Closures` line.  
```swift
changeStuff(number: 10) { (results) in
    
}
```  

In the above code, the closure is the:
```swift
{ (results) in
    
}
```  

This essentially is where we provide the closures functionality to be passed into the `changeStuff` function.  

Because of the difficulty typically involved with understanding closures we practice and talk about them in heavy detail in the iOS 401 class.  

To read more on closures, read the Apple docs [Here](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Closures.html#//apple_ref/doc/uid/TP40014097-CH11-ID94).

#### Coding Challenges  
> If you have extra time, here are some good challenges to attempt on your own. Please hold any questions related to these challenges till the end of the day to allow instructors to keep pace for the day.  

1. Create a function that takes in an array of `Int`'s, loops through them, and returns a sum of all the numbers as an `Int`.  

2. Create a function that takes in a `String` and checks if it is a palindrome and returns a Bool(True or False).  

3. Create a new class of your choice that conforms to the `DogYears` protocol, but changes the default implementation.  

## Before Continuing  
#### 1. With the `CFS3ToDoList.xcodeproj` open in Xcode, go to the top menu bar and select source control.  
#### 2. Select `commit` to commit the work you have done up to this point.  
#### 3. Make sure to leave a detailed commit message for yourself.  
#### 4. Once you have committed your changes, go back to the Source Control menu.  
#### 5. Hover over your project and select `Switch to Branch`.  
#### 6. Select Lab-3. You may see all the lab-2 code jump into the project.  
  > This is to ensure that all participants can keep pace with the workshop.  
>>>>>>> dbacb3d4c30a78d406b752272e1d0c5749ae1f36
