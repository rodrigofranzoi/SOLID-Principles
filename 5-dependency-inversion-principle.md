## Dependency Inversion Principle (DIP)
The Dependency Inversion Principle (DIP) states that high-level modules should not depend on low-level modules; both should depend on abstractions.

Here's an example in Swift:

Suppose we have a class User that has a property notifier of type Notifier, which is responsible for sending notifications.

```swift
class User {
    var notifier: Notifier
    
    init(notifier: Notifier) {
        self.notifier = notifier
    }
    
    func performAction() {
        // Perform action
        notifier.sendNotification()
    }
}
```

In this example, the User class depends on the concrete Notifier class. This violates the DIP because the high-level User class is tightly coupled to the low-level Notifier class, making the code less flexible and harder to maintain.

To fix this, we can create an abstraction, a protocol NotificationSender, that defines the functionality required by the User class.

```swift
protocol NotificationSender {
    func sendNotification()
}

class User {
    var notifier: NotificationSender
    
    init(notifier: NotificationSender) {
        self.notifier = notifier
    }
    
    func performAction() {
        // Perform action
        notifier.sendNotification()
    }
}
```

Now, the User class depends on the abstraction NotificationSender, making the code more flexible and easier to maintain. The concrete Notifier class can conform to the NotificationSender protocol and provide the implementation details for sending notifications.

```swift
class Notifier: NotificationSender {
    func sendNotification() {
        // Send notification
    }
}
```

By adhering to the DIP, the high-level User class is decoupled from the low-level Notifier class, making the code more flexible, maintainable, and testable.