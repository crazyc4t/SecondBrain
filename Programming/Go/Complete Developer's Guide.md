# Why Go?
- In demand language used by high-profile companies
- Simplistic and easy to understand by design
- Built-in dependency management
  - Package registry
- Familiar C-style syntax

# Technical features
- First-class concurrency primitives
  - Perfect for backend programming
- Type safety enforced by compiler
- Memory-safe, no use-after-free bugs
  - Garbage collected; no need to manage memory 
- Compiles to machine code for very fast speeds

# About the course
- Lectures, demos, and hands-on coding exercises
  - Working with the go CLI
  - Utilizing the Go package ecosystem & docs
- Coverage of concepts like pointers, memory and concurrency
- Recap exercises to cover the topics learned in a section
- Final project building a fully functional GUI desktop application

# My goal
To create anigo, a go app that permits to watch anime from the command line!

# Setup

## Install go 

### Linux

For openSUSE:

`sudo zypper in go`

For debian/ubuntu:
`sudo apt install go`

For Arch btw:
`sudo pacman -S go`

For fedora:
`sudo dnf install go`

### Windows & MacOS
Open a web browser and go to go's official page https://go.dev and download your package.

## Text Editor
I'll recommend two editors since atom is no longer on development, I'll go with:
- Codium (FOSS binaries of VScode)
- Neovim (Best editor ever)

### Codium
You need to install the go extension on the extensions tab.

### Neovim
This is a bit complex so am not going to deep dive, just install the treesitter for go, and the LSP server, you will be good to go (hehe got it?)

# Introduction to go 

## Packages and modules

### About packages 
- Packages are go's way of organizing code 
- Programs are written as one or more packages 
  - Packages can be imported from the go package registry
- Packages should be focused and perform a single thing
  - Argument parsing
  - Drawing graphics
  - Handling HTTP requests

### Using packages

```go 
import "name"

import (
  "name"
  "namespace/packageName"
)
```

- Can import everything using a dot (.)
  - No need to reference package name in code 
- Imports can be renamed

```go 
import (
  . "name"
  pk "namespace/packageName"
)
```

### Modules 
- Modules are a collection of packages 
- Created by having a go.mod file in the root directory of your project
  - Can be managed by the go CLI
- Contains information about your project
  - Dependencies, Go version, package info
- All go projects have a go.mod file

## Data types 

- All data in programs consists of binary numbers (0&1)
- A data type is a way that the program can interpret the binary numbers
- Numbers, letters and words are all different types:
  - 15
  - y 
  - hello

**Data types in go**

- Go is a statically typed language
  - Data types must be provided by the programmer
- Go uses type inference to determine what type of data it is working with
  - Data types only need to be provided in specific circumstances
  - Can always specify the type if desired
    - Compiler error if wrong type is used (type safety)

### Primitive data types
- All primitive data types in go are numeric
- Type indicated in code is a convention
  - It's possible that the data is invalid for the given type 
    - Only applies when working with user input or manually manipulating the binary data.

**Signed integer types**
- int8
- int16
- int (best one)
- int32
- int64

**Unsigned integer types**
Are positive-only integers, and they include zero.
- uint8
- byte
- uint16
- uint 
- uint32
- uint64
- uintptr (pointer size)

**Other data types**
- float32 (decimals)
- float64 (decimals)
- complex64 (real & imaginary)
- complex128 (real & imaginary)
- bool (true or false)

**Type aliases**
- Possible to create type aliases
- Same in every way to another type, just a different name 
- Useful for providing indication of what kind of data is being utilized
```go 
type UserId int
type Direction byte
type Speed float64
type Velocity Speed
```

## Strings & Runes

### Runes
- Text is represented using the **rune** type:
  - Similar to char in other programming languages
- Rune is an alias for int32
- Can represent any symbol

### Strings
- String is the data type for storing multiple runes 
- Strings are just an array of bytes and a string length

### Creation
Runes: 'a', 'R'
Strings: "Miau"
Raw literal: `let's code g! \n this escape sequence will be printed out as is`

## Go CLI
- The `go` command is used to:
  - Update Dependencies
  - Build & test projects
  - Manage artifacts
  - Format source code

### Everyday go commands
- build: builds the project & emits an executable binary
  - build -race: checks for concurrency problems
- run: runs the project directly; no output executable
- mod: manages modules and dependencies
  - mod tidy: updates dependencies 
- test: runs the project's test suite
- fmt: formats all source files

## Variables
- Variables provide a way to store & access data in your program 
- Data within can vary
- Alias to data in memory 
- Storing data to a variable is called assignment
- Variables have multiple components:
  - Name 
  - Data 
  - Type

### Single creation 
`var example = 3`

`var example int = 3`

`var example int`
`example = 3`

### Compound creation 
`var a, b, c = 1, 2, "sample"`

```go 
var (
  a int = 1 
  b int = 2 
  c = "sample"
)
```

### Create & Assign
`example := 3`
`a, b := 1, 4`

### Other 
- Variables can be reassigned & assigned to other variables:
  - `a := 1`
  - `a = 3`
  - `b := a` (copy)

- Variable names can be only used once per scope

### Defaults
- Variables that are declared but not assigned will automatically have a default value
- String default: ""
- Number default: 0
- Other: nil (equal to null)

### Comma ok
- "Comma, ok" idiom is a special case
-  Allows a variable to be reassigned in a creation statement

This is wrong:
```go 
a := 1 
var a = 5
```

Since we have already created the variable 

This is ok:
```go 
a, b := 1, 2
c, b := 3, 4
```

Because we are using the comma, ok case where after the comma we can reassign the value of a variable

### Naming 
- Go variable naming convention is camelCase:
  - `myLongVariableName := "hi`
- Use names appropriate for the date

### Constants
- Constants can be created with the `const` keyword
- The value of the constant will never change, it can't be reassigned
- The naming convention is the same but starting with a capital letter
- `const MaxSpeed = 30`

## Functions

- Most basic building block of Go programs 
- Allows functionality to be isolated, which makes programs easier to:
  - Test, debug, extend, modify, read, write, document
- Functions are simple: they take data as input and return data as output
  - input and output data is optional

### Creating functions 
```go 
func name(param1 type, param2 type) type {
// body
}
```

Being `param1` & `param2` the input data specified with each type, and the output data needs to be specified what type will be

If your parameters use the same type, you can list them with commas and at the end specify the type, for example:
`func sum(num1, num2 int) int {}`

You should name functions with camelCase.

## Operators

| Addition | Substraction | Multiplication | Division  | Remainder |
| -------- | ------------ | -------------- | --------- | --------- |
| + +=     | -  -=        | *  *=          | /  /=     | %  %=     |

### Relational Operators

| Less than | Less than or equal to | Greater than | Greater than or equal to | equal to | not equal to |
| <         | <=                    | >            | >=                       | ==       | !=           |


### Logic Operators
| And | Or | Not |
| &&  | || | !   |

## If else

**Flow control**
- Program code executes line-by-line
- Flow control is a way to interrupt this process
  - Different code can be executed based on conditions
- Conditions are programmer-defined and can be as many as needed

```go 
if condition {
// do something
} else if otherCondition {
// do something 
} else {
// do something else
}
```

### Statement initialization
Go permits to create a variable on the if else block, separated by a semi-colon:
```go 
if i := 5; i < 10 {
// do something with i
}
```

### Early return 
- Use early return to stop processing within a function as soon as possible 
  - Maximizes performance
  - All data needed for the function is ready after error checkinh
    - Clean code

```go 
token, err := getSession("alice")
if err != nil {
  return
}
```

## Switch
- Switch is used to easily check multiple conditions 
  - Alternative to many if/else blocks
- Switches execute from top to bottom
- Optionally have a default action

```go 
x := 3
switch x {
case 1:
  // do something if x == 1
case 2:
  // do something if x == 2
default:
  // do something if there's no case that can cover it
}
```

### Conditional statement
```go 
switch result := calculate(5); {
case result > 10:
  // do something 
case result == 6:
  // do something 
}
```

### Case list
```go 
switch x {
case 1, 2, 3:
  // ...
case 10, 20, 30:
  // ...
}
```

### Fallthrough
- Fallthrough will continue checking the next case no matter if it was accomplished or not

```go 
switch letter {
case ' ':
case 'a', 'e', 'i', 'o', 'u':
  fmt.Println("A vowel")
}
case 'A', 'E', 'I', 'O', 'U':
  fmt.Println("Vowels are capital case")
default:
  fmt.Println("miau")
```

## Loops
- It is often required to repeat actions in code more than once or to iterate over the items in a collection 
  - This are accomplished using Loops
- Go uses the `for` keyword for repetition

### For: basic 
`for i := 0; i < 10; i++ { // do something }`

- Post statement is executed on each loop iteration
- Execution continues as long as the condition is true

### For: while
- The while keyword is not available on go 
`for i < 10 { i++ }`

### For: infinite
- Infinite loops are usually used for servers
  - Use the break keyword to exit (break out of) the loop

```go 
for {
  if miau {
    break 
  }
}
```

### Continue 
- Use the continue keyword to skip the current loop 
```go 
for i := 0; i < 10; i++ {
  if i%2 == 0 {
      continue 
  }
  fmt.Println(i)
}
```

## Structures
- Allow data to be stored in groups
  - Similar to a "class" in other programming languages
  - Each data point in the structure is called a field
  - Storing data in groups is usually more efficient
- Possible to associate functionality with Structures
  - Helps organize code and data.

### Defining a structure
```go 
type Sample struct {
    field string 
    a, b int
}
```

### Instantiating a structure 
```go 
data := Sample{"word", 1, 2}
// word == field, a == 1, b == 2
```

If you don't indicate a value during instantiation it will receive default values.

`data := Sample{a: 5}`

### Accessing fields 
```go 
word := data.field
data.a = 10
```

### Anonymous structures 
- It's possible to create anonymous/inline structures inside of a function
- Useful when working with library functions or when shipping data across a network.
  - Can easily define the data structure as-needed.
- Inline structs created using `var` will have default values 
- Shorthand version must have each field defined

**Assigned on the go**
```go 
var sample struct {
  field string
  a, b int
}{
  "hello",
  1, 2,
}
```

**Default values**
```go 
var sample struct {
  field string
  a, b int
}

sample.field = "hello"
sample.a = 9
```

## Arrays
- Arrays are a way to store multiple pieces of the same kind of data 
  - Data is stored consecutively in an "array" of data
  - Each piece of data is called an element
- To access items in the array, an **array index** is used 
  - The index starts at 0, meaning 0 items from the array start 
- Arrays are fixed-size and cannot be resized

### Creating an array 
- Elements not addressed in array initialization will be set to default values
`var myArray [3]int`
`myArray := [3]int{7,8,9}`

**Best way**
`myArray := [...]int{7,8,9,4}`

### Accessing array elements 
`myArray[0] = 7`
`item1 := myArray[0]`

### Iteration 
- Good practice to assign the element to a variable during iteration 
  - Easier to read in large functions/nested loops 
```go 
myArray := [...]int{7,8,9}

for i := 0; i < len(myArray); i++ {
    item := myArray[i]
    fmt.Println(item)
}
```

### Bounds
Attempting to access an element outside the bounds of an array will result in an error.

## Slices 
- Slices are companion types that work with Arrays
- They enable a "view" into an array
  - Views are dynamic and not fixed in size
- Functions can accept a slice as a function parameter 
  - Any size array can be operated upon via slice

### Creating a slice 
- Slices and an underlying array can be created at the same time
`mySlice := []int{1,2,3}`

- Accessing elements in a slice is the same as an array
`item1 := mySlice[0]`

### Slice syntax
- Slice syntax can create slices from specific elements in an array or other slice
`slice[a:b]`
Being `a` the start index and `b` the end index

`a` is inclusive and `b` exclusive

- Omitting `a` means "start at 0"
- Omitting `b` means "to the end"

### Slice syntax example 
```go 
numbers := [...]int{1, 2, 3, 4}
slice1 := numbers[:] // [1, 2, 3, 4]
slice2 := numbers[1:] // [2, 3, 4]
slice3 := numbers[:1] // [2]
slice4 := numbers[:2] // [1, 2]
slice5 := numbers[1:3] // [2, 3]
```

- It is an error to slice past the array length

### Dynamic arrays 
- Slices can be used to create arrays that can be extended
  - The append() function can add additional elements 
    ```go 
    numbers := []int{1, 2, 3}
    numbers = append(numbers, 4, 5, 6)
    ```
  - 3 dots can be used to extend a slice with another slice 
    ```go 
    part1 := []int{1, 2, 3}
    part2 := []int{4, 5, 6}
    combined := append(part1, part2...)
    ```

### Preallocation
- Slices can be preallocated with specific capacities
  - The make() function is used to preallocate a slice 
- Useful when number of elements is known but their values don't 
`slice := make([]int, 10)`

### Slices to functions 
- Functions parameters which require a slice can work with slices of any size 
```go 
func iterate(slice []int) {
  for i := 0; i < len(slice); i++ {
      // .. 
  }
}

small := []int{1}
big := []int{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
iterate(small)
iterate(big)
```

### Multidimensional slices 
```go 
board := [][]string{
  // type declaration is optional
  []string{"_", "_", "_"},
  {"_", "_", "_"},
  {"_", "_", "_"},
}

board[0][0] = "X"
board[2][2] = "O"
board[1][2] = "X"
board[1][0] = "O"
board[0][2] = "X"
```

## Maps

- Maps are a commonly used data structure that stores data in key-value pair 
- Extremely high performance when the key is known
- Unordered - data is stored in random order

### Making a map 
```go 
myMap := make(map[string]int)

myMap := map[string]int{
    "item 1": 1,
    "item 2": 2,
    "item 3": 3,
}
```

### Map operations
```go 
myMap := make(map[string]int)
//Insert
myMap["Favorite number"] = 5
// Read 
fav := myMap["Favorite number"]
missing := myMap["age"] //default value 
// delete
delete(myMap, "favorite number")
// check existance
price, found := myMap["price"]
if !found {
  fmt.Println("price not found")
  return
}
```

### Iteration 
```go 
myMap := make(map[string]int)
for key, value := range myMap {}
```

## Pointers 
- Functions calls in Go are "pass by value"
  - A copy of each function argument is made, regardless of size
    - Potentially slow for large data structures
    - More difficult to manage program state 
- This can be changed by using pointers

- Pointers are variables that "point to" memory 
- The value of the variable itself is a memory address 
  - Accessing the data requires dereferencing the pointer 
  - This allows changing values that exist elsewhere in the program

### Creating pointers 
- We use the asterisk (*) when used with a type indicates the value is a pointer 
- Ampersand (&) creates a pointer from the variable 
  
```go 
value := 10 
var valuePtr *int // pointer to integer
valuePtr = &value // pointer to variable
valuePtr2 := &value
```

### Using pointers
- Asterisk (*) when used with a pointer will dereference the pointer 
  - This provides access to the actual data it points to

```go 
func increment(x *int) {
    *x += 1
}

i := 1
increment(&i)
```

## Receiver functions

- Modified function signature which allows dot notation
- Makes writing some types of functionality more convenient
- Allows simple mutation of existing structures
	- Similar to modifying a class variable in other languages

```go
type Coordinate struct {
	X, Y int
}

func (coord *Coordinate) shiftBy(x, y int) { // starts with parameters then name
	coord.X += x
	coord.y += y
}

coord := Coordinate{5, 5}
coord.shiftBy(1, 1) // more readable with dot notation
// being coord the *Coordinate parameter, with 1, 1 being x, y
```

- Receiver functions provide the "dot" notation for structs
	-  Creating more convenient APIs
- Pointer receivers can modify a struct
- Value receivers can't modify a struct
- Common to use pointers receivers
