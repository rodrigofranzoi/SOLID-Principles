## Open/Closed Principle (OCP)
The Open/Closed Principle (OCP) is another one of the SOLID principles of object-oriented programming and states that a class should be open for extension, but closed for modification. In other words, a class should be designed in a way that new features can be added without modifying the existing code.

Here's an example in Swift:

Suppose we have a class `Rectangle` that represents a rectangle with properties such as width and height.

```swift
class Rectangle {
    var width: Int
    var height: Int
    
    init(width: Int, height: Int) {
        self.width = width
        self.height = height
    }
    
    func area() -> Int {
        return width * height
    }
}
```

Now, suppose we want to add a new type of shape, such as a circle. We could add a new class for circles, but that would require modifying the existing code and would not adhere to the OCP. Instead, we can define a new protocol `Shape` and extend the `Rectangle` class to conform to the `Shape` protocol.

```swift
protocol Shape {
    func area() -> Int
}

extension Rectangle: Shape { }

class Circle {
    var radius: Int
    
    init(radius: Int) {
        self.radius = radius
    }
    
    func area() -> Int {
        return Int(Double.pi * Double(radius * radius))
    }
}
```


Now, we can create a `Shape` array and add both rectangles and circles to it without having to modify the existing code.

```swift
var shapes: [Shape] = [Rectangle(width: 10, height: 20), Circle(radius: 5)]

for shape in shapes {
    print("Area: (shape.area())")
}
```


This demonstrates how the OCP can be used to add new features to a codebase without modifying the existing code, making the code more maintainable and flexible.
