# Go

<a name="go-beginner"></a>

<details>
<summary>What are some characteristics of the Go programming language?</summary><br><b>

- Strong and static typing - the type of the variables can't be changed over time and they have to be defined at compile time
- Simplicity
- Fast compile times
- Built-in concurrency
- Garbage collected
- Platform independent
- Compile to standalone binary - anything you need to run your app will be compiled into one binary. Very useful for version management in run-time.

Go also has good community.
</b></details>

<details>
<summary>What is the difference between <code>var x int = 2</code> and <code>x := 2</code>?</summary><br><b>

The result is the same, a variable with the value 2.

With <code>var x int = 2</code> we are setting the variable type to integer while with <code>x := 2</code> we are letting Go figure out by itself the type.
</b></details>

<details>
<summary>True or False? In Go we can redeclare variables and once declared we must use it.</summary>

False. We can't redeclare variables but yes, we must used declared variables.
</b></details>

<details>
<summary>What libraries of Go have you used?</summary><br><b>

This should be answered based on your usage but some examples are:

- fmt - formatted I/O
  </b></details>

<details>
<summary>What is the problem with the following block of code? How to fix it?

```
func main() {
    var x float32 = 13.5
    var y int
    y = x
}
```

</summary><br><b>
</b></details>

<details>
<summary>The following block of code tries to convert the integer 101 to a string but instead we get "e". Why is that? How to fix it?

```
package main

import "fmt"

func main() {
    var x int = 101
    var y string
    y = string(x)
    fmt.Println(y)
}
```

</summary><br><b>

It looks what unicode value is set at 101 and uses it for converting the integer to a string.
If you want to get "101" you should use the package "strconv" and replace <code>y = string(x)</code> with <code>y = strconv.Itoa(x)</code>
</b></details>

<details>
<summary>What is wrong with the following code?:

```
package main

func main() {
    var x = 2
    var y = 3
    const someConst = x + y
}
```

</summary><br><b>

Constants in Go can only be declared using constant expressions.
But `x`, `y` and their sum is variable.
<br>
<code>const initializer x + y is not a constant</code>
</b></details>

<details>
<summary>What will be the output of the following block of code?:

```
package main

import "fmt"

const (
	x = iota
	y = iota
)
const z = iota

func main() {
	fmt.Printf("%v\n", x)
	fmt.Printf("%v\n", y)
	fmt.Printf("%v\n", z)
}
```

</summary><br><b>

Go's iota identifier is used in const declarations to simplify definitions of incrementing numbers. Because it can be used in expressions, it provides a generality beyond that of simple enumerations.
<br>
`x` and `y` in the first iota group, `z` in the second.
<br>
[Iota page in Go Wiki](https://github.com/golang/go/wiki/Iota)
</b></details>

<details>
<summary>What _ is used for in Go?</summary><br><b>
	
It avoids having to declare all the variables for the returns values.
It is called the [blank identifier](https://golang.org/doc/effective_go.html#blank).
<br>
[answer in SO](https://stackoverflow.com/questions/27764421/what-is-underscore-comma-in-a-go-declaration#answer-27764432)
</b></details>

<details>
<summary>What will be the output of the following block of code?:

```
package main

import "fmt"

const (
	_ = iota + 3
	x
)

func main() {
	fmt.Printf("%v\n", x)
}
```

</summary><br><b>

Since the first iota is declared with the value `3` (`+ 3`), the next one has the value `4`
</b></details>

<details>
<summary>What will be the output of the following block of code?:

```
package main

import (
	"fmt"
	"sync"
	"time"
)

func main() {
	var wg sync.WaitGroup

	wg.Add(1)
	go func() {
		time.Sleep(time.Second * 2)
		fmt.Println("1")
		wg.Done()
	}()

	go func() {
		fmt.Println("2")
	}()

	wg.Wait()
	fmt.Println("3")
}
```

</summary><br><b>

Output: 2 1 3

[Aritcle about sync/waitgroup](https://tutorialedge.net/golang/go-waitgroup-tutorial/)

[Golang package sync](https://golang.org/pkg/sync/)
</b></details>

<details>
<summary>What will be the output of the following block of code?:

```
package main

import (
	"fmt"
)

func mod1(a []int) {
	for i := range a {
		a[i] = 5
	}

	fmt.Println("1:", a)
}

func mod2(a []int) {
	a = append(a, 125) // !

	for i := range a {
		a[i] = 5
	}

	fmt.Println("2:", a)
}

func main() {
	sl := []int{1, 2, 3, 4}
	mod1(s1)
	fmt.Println("1:", s1)

	s2 := []int{1, 2, 3, 4}
	mod2(s2)
	fmt.Println("2:", s2)
}
```

</summary><br><b>

Output: <code><br>
1 [5 5 5 5]<br>
1 [5 5 5 5]<br>
2 [5 5 5 5 5]<br>
2 [1 2 3 4]<br>
</code>

In `mod1` a is link, and when we're using `a[i]`, we're changing `s1` value to.
But in `mod2`, `append` creats new slice, and we're changing only `a` value, not `s2`.

[Aritcle about arrays](https://golangbot.com/arrays-and-slices/),
[Blog post about `append`](https://blog.golang.org/slices)
</b></details>

<details>
<summary>What will be the output of the following block of code?:

```
package main

import (
	"container/heap"
	"fmt"
)

// An IntHeap is a min-heap of ints.
type IntHeap []int

func (h IntHeap) Len() int           { return len(h) }
func (h IntHeap) Less(i, j int) bool { return h[i] < h[j] }
func (h IntHeap) Swap(i, j int)      { h[i], h[j] = h[j], h[i] }

func (h *IntHeap) Push(x interface{}) {
	// Push and Pop use pointer receivers because they modify the slice's length,
	// not just its contents.
	*h = append(*h, x.(int))
}

func (h *IntHeap) Pop() interface{} {
	old := *h
	n := len(old)
	x := old[n-1]
	*h = old[0 : n-1]
	return x
}

func main() {
	h := &IntHeap{4, 8, 3, 6}
	heap.Init(h)
	heap.Push(h, 7)

  fmt.Println((*h)[0])
}
```

</summary><br><b>

Output: 3

[Golang container/heap package](https://golang.org/pkg/container/heap/)
</b></details>
