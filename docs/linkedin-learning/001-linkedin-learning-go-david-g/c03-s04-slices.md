# Manage Ordered Values in Slices

- In Go, a slice is an abstraction layer that sits on top of an array.
- A slice is created when you declare it, and the runtime allocates memory for the array in the background.
- The main difference between slices and arrays is that slices are re-sizable and can be sorted easily.
- To create a slice, you must explicitly declare its length. If you omit the length, the slice will grow dynamically.

Key characteristics of slices:

- Re-sizable
- Can be sorted easily
- Can have dynamic growth

Methods to manipulate slices:

- `append` to add items
- `append` with range to remove items
- `make` to declare a slice with an initial size and capacity (optional)
- Sorting: use the `sort` package, which provides functions for various data types such as `Ints`, `Float64s`, etc.

Example code:

- Declaring a slice explicitly:

```go
colors := [3]string{"red", "green", "blue"}
```

- Creating a slice with dynamic growth:

```go
colors := make([]string, 0)
colors = append(colors, "purple")
```

- Removing items from a slice using `append` with range:

```go
colors := []string{"red", "green", "blue"}
colors = append(colors[:1], colors...)
```

- Declaring a slice with an initial size and capacity:

```go
numbers := make([]int, 5)
numbers[0] = 134
numbers = append(numbers, 200)
```

- Sorting slices using the `sort` package:

```go
import "sort"

numbers := []int{3, 1, 4}
sort.Ints(numbers)
```

## Sample Code

```go
package main

import (
	"fmt"
	"sort"
)

func main() {
	var colors = []string{"Red", "Green", "Blue"}
	fmt.Println(colors)
	colors = append(colors, "Purple")
	fmt.Println(colors)

	// Remove the first item
	colors = append(colors[1:len(colors)])
	fmt.Println(colors)
	// Remove the last item
	colors = append(colors[:len(colors)-1])
	fmt.Println(colors)

	numbers := make([]int, 5, 5)
	numbers[0] = 134
	numbers[1] = 72
	numbers[2] = 55
	numbers[3] = 12
	numbers[4] = 14
	fmt.Println(numbers)

	numbers = append(numbers, 245)
	fmt.Println(numbers)

	sort.Ints(numbers)
	fmt.Println(numbers)
}
```