# AskSteve
Ask Steve is a repository with summarized topics about development on Apple platforms

## (WIP)
## Inspecting Variables with LLDB 
This was inspired by [Inspecting Variables with LLDB - Intermediate Debugging in iOS - raywenderlich.com](https://www.youtube.com/watch?v=WwBUcof0lKw), it summarizes the video idea and add some reference and comments

### References
[LLDB to GDB Command Map](https://lldb.llvm.org/lldb-gdb.html)

### po
Evaluate an expression on the current thread. Displays any returned value with formatting controlled by the type's author.  
Expects 'raw' input (see 'help raw-input'.)
```
<raw-input> -- Free-form text passed to a command without prior interpretation, allowing spaces without requiring quotes.  
To pass arguments and free form text put two dashes ' -- ' between the last argument and any raw input.

Syntax: `po <expr>`

Command Options Usage:
  `po <expr>`
```

`po` is an abbreviation for `expression -O  --`

```
(lldb) expr -o -- [SomeClass returnAnObject]
or using the po alias:
(lldb) po [SomeClass returnAnObject]
```

```
// `po` prints `debugDescription` from `CustomDebugStringConvertible` protocol
(lldb) p self.myVariable
```

### p
`p` is an abbreviation for `expression`

```
// execute `aMethod()` and print the result, *careful with side effects when calling methods*
(lldb) p self.myVariable.aMethod()
```
### po


### c
```
// same as clicking continue when debugging
(lldb) c
```

### frv
```
// when executed against some method call, it won’t run, so *no side effects*
(lldb) fr v self.myVariable.aMethod() error: "getSomeInfo()" is not a member of "(MyModel) self.myModel"
```

