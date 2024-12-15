# Defining Functions as Methods of Custom Types

* In Go, you can attach functions to your custom types, which are then referred to as methods.
* A method is a member of a type, rather than a class.
* To define a method, you need to pass in the receiver, which is a reference to the object that the method is being called on.
* The receiver is followed by the method name and parentheses.
* Within the method, you can reference the object with the identifier.

## Example Code

```go
type Dog struct {
  sound string
}

func (d *Dog) Speak() {
  fmt.Println(d.sound)
}

func main() {
  poodle := Dog{sound: "Woof!"}
  poodle.Speak()
}
```

## Changing Exported Fields of an Object

* You can change the exported fields of an object, and then call the method again.
* For example, you can change the `sound` field of the `poodle` object to `"Arf!"` and then call the `Speak` method again.

## Method Overriding

* Go does not support method overriding.
* Each method must have its own unique name.
* However, like all functions, methods can return values, just declare the type assigned to the method.

```go
func (d *Dog) SpeakThreeTimes() {
  d.sound = fmt.Sprintf("%v %v %v", d.sound, d.sound, d.sound)
  fmt.Println(d.sound)
}
```

## Using Pointers as Receivers

* If you want to pass a reference to the object, rather than a copy, you can use pointers as receivers.
* However, this is not necessary in this example, as the method is only modifying the object's fields.

## Conclusion

* The ability to create custom methods for your own types makes Go behave more like a fully Object Oriented language, even without type inheritance.
* A struct can have as many different methods as it needs to accomplish its requirements.
