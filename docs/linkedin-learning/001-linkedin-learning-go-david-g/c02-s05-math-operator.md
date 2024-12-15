# Use math operators

## Notes

- Go supports mathematical operators from C-style languages, including:
  - Usual math operators for addition, subtraction, multiplication, and division
  - Bitwise operators
- Note: Go does not implicitly convert numeric types.
- Example of trying to add an integer and a float without conversion:
  - Integer + Float results in error message "invalid operation"
- To perform mathematical operations between different data types, use the following approach:
  - Convert one value to match the type of the other
  - Use functions with the same name as the target type (e.g. `float64` function for converting an integer to a float)
- For more complex mathematical operations beyond simple operators, use the math package:
  - Provides functions and constants for tasks such as rounding numbers
  - Example: using the `round` function from the math package to round a value to the nearest integer

## Sample code

- Wrap value in target type as a function call

```go
package main

import (
	"fmt"
)

func main() {

	var anInt int = 5
	var aFloat float64 = 42
	sum := float64(anInt) + aFloat
	fmt.Printf("Sum: %v, Type: %T\n", sum, sum)
}
```

- For other operations, use math package

```go
package main

import (
	"fmt"
	"math"
)

func main() {

	var aFloat = 3.14159
	var rounded = math.Round(aFloat)
	fmt.Printf("Original: %v, Rounded: %v\n", aFloat, rounded)
}
```
