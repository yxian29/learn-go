# Writing and Reading Local Text Files

* To create a file in Go, you can use the `os` package to create a file reference and then use `io.WriteString` to write data to the file.
* To read a file in Go, you can use the `ioutil` package to read the file as an array of bytes and then convert it to a string.
* When working with files, it's very important to close them when you're done using the `defer` keyword.
* The `defer` keyword ensures that the file is closed after the current function has finished executing.

## Example Code

```go
package main

import (
  "fmt"
  "io"
  "io/ioutil"
  "os"
)

func checkError(err error) {
  if err != nil {
    panic(err)
  }
}

func main() {
  content := "Hello from Go!"
  file, err := os.Create("fromString.txt")
  checkError(err)
  length, err := io.WriteString(file, content)
  checkError(err)
  fmt.Printf("Wrote a file with %d characters.\n", length)
  defer file.Close()
}
```

## Reading a File

* To read a file in Go, you can use the `ioutil` package to read the file as an array of bytes and then convert it to a string.
* The `defer` keyword ensures that the file is closed after the current function has finished executing.

```go
func readFile(filename string) ([]byte, error) {
  data, err := ioutil.ReadFile(filename)
  checkError(err)
  return data, nil
}

func main() {
  defer func() {
    defer ioutil.ReadFile("fromString.txt")
  }()
  readFile("fromString.txt")
}
```
