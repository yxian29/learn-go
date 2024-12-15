# Declare and Initialize Variables

- Go is a statically typed language, which means you must declare the type of each variable during compilation and cannot change its type at runtime.
- There are two ways to declare types:
  - Explicit typing: You use the `var` keyword to declare the type of a variable after it's declared. For example: `var a string = "Hello"`.
  - Implicit typing: The type is inferred based on the initial value assigned to the variable. For example, if you assign a string value to a variable, Go will automatically infer that the variable is a string.
- There are also two ways to initialize variables:
  -Using the `var` keyword and assigning an initial value. For example: `var b int = 42`.
  -Using the colon equals operator (=) inside a function or outside of it (with the `var` keyword). For example: `const c string = "World"`.
- Note that constants declared with the `const` keyword can only be initialized outside of functions and are not subject to implicit typing.

## Sample Code

```go
package main

import "fmt"

const aConst int = 64

func main() {

	var aString = "This is a string"
	fmt.Println(aString)
	fmt.Printf("The variable aString type is %T\n", aString)

	aString1 := "This is also a string"
	fmt.Println(aString1)
	fmt.Printf("The variable aString1 type is %T\n", aString1)

	fmt.Println(aConst)
	fmt.Printf("The variable type is %T\n", aConst)
}
```

## Key points

- Explicit typing requires you to declare the type explicitly after declaring the variable.
- Implicit typing allows Go to infer the type based on the initial value assigned to the variable.
- Colon equals operator (=) is used for initialization inside a function or outside of it (with the `var` keyword).
- Constants declared with the `const` keyword can only be initialized outside of functions.
