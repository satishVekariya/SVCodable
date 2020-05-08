# SVCodable

Simple JSON Object conversion with help of `Codable` and `extension`.

[![Platform](https://img.shields.io/badge/platform-iOS-green.svg)]()
![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)
[![Swift Package Manager](https://rawgit.com/jlyonsmith/artwork/master/SwiftPackageManager/swiftpackagemanager-compatible.svg)](https://swift.org/package-manager/)

SVCodable is a extension written in Swift that makes it easy for you to convert your model objects (classes and structs) to and from JSON.

# The Basics
To support mapping, a class or struct just needs to implement the ```Codable``` protocol which includes the following functions:


### To JSON:

```
struct Message: Codable {
    let sender: String
    let text: String
    let time: TimeInterval
}

let message = Message(sender: "Kaka", text: "Hello", time: 12345678910)

let jsonDictionary:[String : Any] = message.toJSON()
let jsonString:String? = message.toJSONString()
let jsonData:Data? = message.toJSONData()

```

### From JSON:

```
let messageStr = """
    {
       "sender": "Kaka",
       "text": "Hello",
       "time": 12345678910
    }
"""

let message = Message.map(JSONString: messageStr)

```
