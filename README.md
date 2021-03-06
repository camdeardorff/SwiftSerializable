# SwiftSerializable
Simple way to convert any swift object to a format that can be transferred over the network.

The driver behind this project has been many of Apple's new API's that allow a user to transfer a dictionary of data between two devices (specifically between an iPhone and an Apple Watch). With iOS 9, the generics system build into Objective-C and Swift 2.0 gives us the ability to serialize/deserialize any custom object in a generic way. In addition, we can deserialize any child property collections since they are strongly typed and we know what they should be deserialized to.

All you need to do is have the custom objects you want to serialize/deserialize extend the Serializable class and mark them with the @objc tag:

    @objc(Testing)
    internal class Testing: Serializable {
     ...  
    }
    
If your custom class contains references to other custom class entities that you want to serialize/deserialize, simply have those classes extend Serializable and add the @objc tag as well. See the MyPlayground file for an in depth example.
