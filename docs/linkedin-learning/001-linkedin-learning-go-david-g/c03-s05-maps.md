# Store Unordered Values in Maps

## Map Basics

- A map in Go is an unordered collection of key-value pairs.
- Maps can be used to store collections of data and access items arbitrarily using their keys.

## Creating a Map

- Use the `make` function to create a new map.
- Specify the key type and associated value type when creating a map, e.g. `states := make(map[string]string)`.
- Output the contents of a map using `fmt.Println(states)`.

## Adding Items to a Map

- Use the `states["WA"] = "Washington"` syntax to add an item to a map.
- Duplicate this line for multiple items.
- Note that the order in which items are added is not guaranteed.

## Retrieving and Removing Items from a Map

- Retrieve an item from a map using the `states["California"]` syntax.
- Remove an item from a map using the `delete(states, "Oregon")` syntax.
- Output the contents of a map after removing or adding an item.

## Iterating Over a Map

- Use a `for` loop with the `range` keyword to iterate over a map: `for k, v := range states { ... }`.
- Note that the order in which items are iterated over is not guaranteed.

## Sorting Items in a Map

- Extract keys from a map as a slice of strings.
- Sort the slice using the `sort.Strings` function.
- Output the sorted slice.

## Example Code Snippet

```go
states := make(map[string]string)
states["WA"] = "Washington"
states["OR"] = "Oregon"
states["CA"] = "California"

fmt.Println(states)

delete(states, "OR")

states["NY"] = "New York"

fmt.Println(states)

for i := range states {
    fmt.Printf("%s %s\n", keys[i], states[keys[i]])
}
```

## Additional Notes

- Maps are unordered collections, so the order in which items are displayed is not guaranteed.
- Slices and maps can be used together to process data in any desired order.

## Sample Code

```go
package main

import (
	"fmt"
	"sort"
)

func main() {
	states := make(map[string]string)
	fmt.Println(states)
	states["WA"] = "Washington"
	states["OR"] = "Oregon"
	states["CA"] = "California"
	fmt.Println(states)

	california := states["CA"]
	fmt.Println(california)

	delete(states, "OR")
	states["NY"] = "New York"
	fmt.Println(states)

	for k, v := range states {
		fmt.Printf("%v: %v\n", k, v)
	}

	keys := make([]string, len(states))
	i := 0
	for k := range states {
		keys[i] = k
		i++
	}
	fmt.Println(keys)
	sort.Strings(keys)
	fmt.Println(keys)

	for i := range keys {
		fmt.Println(states[keys[i]])
	}
}
```
