
# Use the math package

## Mathematical Operations in Go

- **Integer Operations**
  - Declare multiple integer variables at once using the same statement
  - Use the `+` operator to add values together, e.g., `i1 + i2 + i3`
  - Use `fmt.Println` to print the result of an addition operation
- **Floating Point Operations**
  - Declare multiple floating point variables at once using the same statement
  - Use the `+` operator to add values together, e.g., `f1 + f2 + f3`
  - Experience precision issues with simple operations due to binary storage format
  - Use the `math/big` package to manage complex numbers and improve precision
- **Rounding Floating Point Numbers**
  - Use `math ROUND` function to round a floating point number to a specified precision
  - Multiply by a power of 10 before rounding, e.g., `floatSum - 100`
  - Divide by the same power of 10 after rounding, e.g., `(floatSum - 100) / 100`
- **Constants and Functions from the Math Package**
  - Use `math.Pi` to access the value of pi
  - Use formatting verbs like `%f` to print floating point numbers with specified precision

## Sample Code

```go
package main

import (
	"fmt"
	"math"
)

func main() {

	i1, i2, i3 := 12, 45, 65
	intSum := i1 + i2 + i3
	fmt.Println("Integer sum:", intSum)

	f1, f2, f3 := 23.5, 65.1, 76.3
	floatSum := f1 + f2 + f3
	fmt.Println("Float sum:", floatSum)

	floatSum = math.Round(floatSum*100) / 100
	fmt.Println("The sum is now", floatSum)

	circleRadius := 15.5
	circumference := circleRadius * 2 * math.Pi
	fmt.Printf("Circumference: %.2f\n", circumference)
}
```