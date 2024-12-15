# Group Related Values in Structs

- In Go, a struct is a custom data type used to encapsulate both data and methods.
  - Similar to CS structs and Java classes.
  - No inheritance model; each struct is independent with its own fields for data management and optionally its own methods.

- To declare a custom type in Go:
  - Start with the `type` keyword, followed by the name of your type (can be uppercase for exported or lowercase for non-exported).
  - Use an upper case initial character to make the type exported (readable from other parts of the application).

- A struct declaration consists of:
  - The `struct` keyword.
  - An open brace `{}` that separates the fields from the closing bracket.
  - Fields are properties of the struct, where each property is a variable or value associated with the type.

- Field names in Go structs are either exported (uppercase initial character) or non-exported (lowercase initial character).
- The order of field declarations matters; use an upper case initial character to make fields exportable.

- To create an instance of a struct:
  - Use the `var` keyword followed by the variable name and assignment operator.
  - Pass values to the struct in the same order as their declaration.

- To access struct fields:
  - Use the dot operator (`.`).
  - Example: `poodle.Breed` or `poodle.Weight`.

- Methods can be added to structs for encapsulated functionality.
  - Will be discussed in a future chapter.

- To print a string representation of a struct:
  - Use the `fmt.Print()` function with the ` %+V` format specifier, followed by a line feed (`\n`).
  - Example: `fmt.Print("I'm looking at the poodle object.\n")`.

- To debug or inspect struct fields and values:
  - Use the `print F` function.
  - Create a string that looks like `"+V"`, with a line feed at the end.

- Example code snippets:
  - Creating an instance of a struct: `var poodle dog`
  - Accessing struct fields: `poodle.Breed` and `poodle.Weight`
  - Printing a string representation of a struct using `fmt.Print()`
  - Debugging or inspecting struct fields and values with `print F`

## Sample Code

```go
package main

import (
	"fmt"
)

func main() {
	poodle := Dog{"Poodle", 10}
	fmt.Printf("%+v\n", poodle)
	fmt.Printf("Breed: %v\nWeight: %v\n", poodle.Breed, poodle.Weight)
	poodle.Weight = 9
	fmt.Printf("Breed: %v\nWeight: %v\n", poodle.Breed, poodle.Weight)
}

// Dog is a struct
type Dog struct {
	Breed  string
	Weight int
}
```