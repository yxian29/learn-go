# Get Input From The Console

## Notes

- To take user input, use functions from the "bufio" package.
  - Import packages: "bufio" and "os".
- In main function:
  - Delete existing code
  - Create reader variable and initialize it with bufio.NewReader(os.Stdin)
- Display prompt to user using fmt.Print with a space at the end.
- Pause application by creating two variables:
  - input: string of user's input (without error handling for now)
  - _error: potential error object (ignore if not needed, name with underscore)
- Initialize input and error variables with reader.ReadString('\n')
- Print out what was entered using fmt.Print
- To run the application correctly from Visual Studio Code:
  - Run "go run ." command in terminal.

## Sample Code

```go
package main

import (
	"bufio"
	"fmt"
	"os"
)

func main() {

	reader := bufio.NewReader(os.Stdin)
	fmt.Print("Enter text: ")
	input, _ := reader.ReadString('\n')
	fmt.Println("You entered:", input)
}
```
