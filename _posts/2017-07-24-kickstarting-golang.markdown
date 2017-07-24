# Summary
Today during our second meetup, we helped all members setting up golang and installing an IDE. We had a look at the syntax of go and did some examples with functions, error handling, vendoring, packages and visibility.

## main.go

```go
package main

import (
	"fmt"
	"github.com/pkg/errors"
	"helloWorld/something"
)

// example of a function with multiple return values
func someInt() (result int, err error) {

	result = 0
	err = errors.New("Error")

	return result, err
}

// main function. Note: package must be main for executable
func main() {

	somepackage.Test2()

	result, err := someInt()

	if err != nil {
		fmt.Errorf("%s", err)
	}

	fmt.Println("Hello World:", result)
}

```

## second go file in package `somepackage`
somepackage/test.go

```go
package somepackage

// Note: Visibility is handled by upper or lowercase function name
// lowercase: Visible only from inside the package
func test() string {
	return "test1"
}

// uppercase: Visible from inside or outside the package
func Test2() string {
	return "visible"
}
```

## On vendoring
Install tools like govendor or glide
- https://github.com/kardianos/govendor
- https://github.com/Masterminds/glide
