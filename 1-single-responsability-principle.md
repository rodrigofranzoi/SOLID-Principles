## Single Responsibility Principle (SRP)
The Single Responsibility Principle (SRP) is one of the SOLID principles of object-oriented programming and states that a class should have only one reason to change. In other words, a class should have only one responsibility and that responsibility should be completely encapsulated by the class. This makes the code more maintainable and easier to understand, as changes to one part of the code do not affect other parts.

Here's an example in Swift:

Suppose we have a class `Person` that represents a person and has properties such as name, age, and address.

```swift
class Person {
    var name: String
    var age: Int
    var address: String
    
    init(name: String, age: Int, address: String) {
    self.name = name
    self.age = age
    self.address = address
}

func printPerson() {
    print("Name: \(name)")
    print("Age: \(age)")
    print("Address: \(address)")
}
```


However, this class violates the SRP because it has multiple responsibilities. Not only does it store information about a person, but it also prints that information. It would be better to split this class into two separate classes, one to store the information and one to print the information.

```swift
class PersonInfo {
    var name: String
    var age: Int
    var address: String
    
    init(name: String, age: Int, address: String) {
        self.name = name
        self.age = age
        self.address = address
    }
}

class PersonPrinter {
    func printPerson(person: PersonInfo) {
        print("Name: (person.name)")
        print("Age: (person.age)")
        print("Address: (person.address)")
    }
}
```


Now, the two classes have a single responsibility each. The `PersonInfo` class is responsible for storing information about a person, while the `PersonPrinter` class is responsible for printing that information. This makes the code easier to understand and maintain.
