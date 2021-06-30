Open Tok Leak Signal
==============================

Added a timer that fires a signal every 0.1 seconds and it leaks.

![Uploading Capture d’écran 2021-06-30 à 21.23.59.png…]()


```swift
  timer = Timer.scheduledTimer(withTimeInterval: 0.1, repeats: true, block: { [weak self] _ in
            guard let self = self else { return }
            self.session.signal(withType: "nintendo", string: "Hello its me mario", connection: nil, error: nil)
        })
        timer?.fire()
```
