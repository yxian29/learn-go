# Reading a Text File from the Web

* Use the `net/http` package to make HTTP requests and send data to remote hosts.
* Use the `io/ioutil` package to read the response body as a byte array.
* Use the `defer` keyword to close the response body after use.

## Example Code

```go
package main

import (
  "fmt"
  "io/ioutil"
  "net/http"
)

func main() {
  url := "http://example.com"
  resp, err := http.Get(url)
  if err != nil {
    panic(err)
  }
  defer resp.Body.Close()
  bytes, err := ioutil.ReadAll(resp.Body)
  if err != nil {
    panic(err)
  }
  content := string(bytes)
  fmt.Println(content)
}
```

## Parsing JSON Data

* Use a JSON parsing library such as `encoding/json` to parse the JSON data.
* Use the `json.Unmarshal` function to unmarshal the JSON data into a Go struct.
* Use the `json.NewDecoder` function to create a decoder for the JSON data.

```go
import (
  "encoding/json"
)

type Person struct {
  Name string
  Age  int
}

func main() {
  data := []byte(`{"name":"John","age":30}`)
  var person Person
  err := json.Unmarshal(data, &person)
  if err != nil {
    panic(err)
  }
  fmt.Println(person.Name)
  fmt.Println(person.Age)
}
```
