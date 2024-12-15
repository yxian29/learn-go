# Convert string inputs to other types

## Notes

- Use bufio's new reader function and OS standard object to get user input as strings
- Need additional packages:
  - strconv for string conversion
  - strings for string manipulation functions
- Copy line of code, modify to parse a number instead of text
- Create variable numInput, assign the result of reader.ReadString with newline delimiter
- Convert string to number using strconv.ParseFloat
  - Trim whitespace from input using strings.TrimSpace
  - Parse float 64 as default for 64-bit operating system
- Evaluate error object:
  - If err is nil, proceed normally
  - If err is not nil, print the error message and exit
- Use conditional code to handle both successful and failed parses
- Save changes and run the application again in integrated terminal
- Test parsing with valid and invalid input values

## Sample code

```go
package main

import (
	"bufio"
	"fmt"
	"os"
	"strconv"
	"strings"
)

func main() {

	reader := bufio.NewReader(os.Stdin)
	fmt.Print("Enter text: ")
	input, _ := reader.ReadString('\n')
	fmt.Println("You entered:", input)

	fmt.Print("Enter a number: ")
	numInput, _ := reader.ReadString('\n')
	aFloat, err := strconv.ParseFloat(strings.TrimSpace(numInput), 64)
	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println("Value of number:", aFloat)
	}
}
```
