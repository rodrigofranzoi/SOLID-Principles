## Liskov Substitution Principle (LSP)
The Liskov Substitution Principle (LSP) states that objects of a superclass should be replaceable with objects of a subclass without altering the correctness of the program. In other words, if a program is written to work with objects of a superclass, it should continue to work correctly when objects of a subclass are used instead.

Here's an example in Swift:

Suppose we have a superclass `Vehicle` that represents a general concept of a vehicle.

```swift
class Vehicle {
    func startEngine() {
        print("Engine started")
    }
}
```


Now, let's say we have a subclass `Car` that represents a specific type of vehicle.

```swift
class Car: Vehicle {
    override func startEngine() {
        print("Car engine started")
    }
}
```


According to the LSP, if a function is written to work with `Vehicle` objects, it should also work with `Car` objects without any problems. For example:

```Swift
func driveVehicle(vehicle: Vehicle) {
    vehicle.startEngine()
    print("Driving vehicle")
}

let car = Car()
driveVehicle(vehicle: car)
```


This will produce the output:

```shell
Car engine started
Driving vehicle
```


As we can see, the function `driveVehicle` was written to work with `Vehicle` objects, but it works just as well with `Car` objects, which are a subclass of `Vehicle`. This demonstrates that the Liskov Substitution Principle is being followed.
