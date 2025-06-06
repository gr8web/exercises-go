
Переменные — это именованные значения. Они хранятся в памяти во время выполнения программы.

Существует два способа объявить переменную в Go. Длинная запись с ключевым словом `var`:

```go
var num int = 11
```

И короткая запись:

```go
num := 22
```

Понимание, где лучше использовать короткую, а где – длинную инициализацию нарабатывается практикой. Пока же советуем придерживаться двух правил:
— Использовать короткую запись как можно чаще
— Если где-то необходимо написать через var (например, инициализировать несколько переменных за раз), то все переменные объявляются одинаково.

Значение переменной можно изменять в любой момент:

```go
// двоеточие используется только при инициализации
num := 22
num = 33
```

Однако из-за строгой типизации мы не можем записать в переменную значение другого типа данных:

```go
num := 22
// получим ошибку: cannot use "string" (type untyped string) as type int in assignment
num = "string"
```

Переменные принято называть в camelCase:

```go
longTrickyName := "Josefina"
```

Если не задавать значение переменной при инициализации, она будет иметь «нулевое» значение:

```go
var (
	a string // ""
	b bool   // false
	c int    // 0
)
```

Объявлять переменные можно на уровне функций и пакетов. Переменные на уровне пакета инициализируются при старте программы. Они используются не часто. Например, чтобы не тратить память и процессор на создание новой переменной, мы можем один раз описать статичные ошибки и использовать их в функциях пакета:

```go
package math

import "errors"

// статичная ошибка
var errCannotSum = errors.New("cannot sum")

func sum(...)
```

Стоит сказать пару слов об особенности именования переменных. Из-за стремления к простоте, переменные называются в максимально сокращенном виде, достаточном для понимания. Например:

```go
// НЕ Go way
message := "👎"
buffer := bytes.Buffer{}

// Go way
msg := "👍"
buf := bytes.Buffer{}
```
