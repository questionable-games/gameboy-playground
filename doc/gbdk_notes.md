# GBDK Notes
## General Programming Rules

From https://videlais.com/2016/07/03/programming-game-boy-games-using-gbdk-part-1-configuring-programming-and-compiling/:

* Objects, as they might exist in other languages, aren’t in C. And you can’t use structs to mirror this functionality, either. Most of your code will be based on functions and arrays.
* Whenever possible, use globals, too. Instead of defining a variable within a function, define it once and then, if possible after, re-use that same name as a way to cut down on calls to the stack.
* Instead of using “int”, use “UINT8” at all times.
* Other than in a few specific cases, most values will be in hexadecimal.
