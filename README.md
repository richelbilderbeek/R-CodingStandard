# R-CodingStandard

Coding standard for R, combining:
* The book 'Advanced R' by Hadley Wickham, CRC Press, 2014
* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml)
* The document 'Rchaeology: Idioms of R Programming' by Paul E. Johnson, January 28, 2015, [PDF](http://pj.freefaculty.org/R/Rchaeology.pdf)
* The document 'Rtips.  Revival 2014!' by Paul E. Johnson, March 24, 2014, [PDF](http://pj.freefaculty.org/R/Rtips.pdf)

# General


## Avoid lines longer than 80 characters

```
[Example here]
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `The maximum line length is 80 characters`

## Prefer placing spaces around all binary operators 

```
x <- 42
y <- x + 314
z <- y - 42

if (a == b) print("Equal")
if (a != b) print("Unequal")
if (a < b) print("Less")
if (a <= b) print("Less or equal")
if (a > b) print("Greater")
if (a >= b) print("Greater or equal")

Show <- function(s = "Hello World") { # Note the spaces around the =
   # ...
}
```

### Exception

Spaces around ='s are optional when passing parameters in a function call.

```
rep(x = 314, times = 42) # Good
rep(x=314, times=42)     # Okay
```
### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Place spaces around all binary operators (=, +, -, <-, etc.). Exception: Spaces around ='s are optional when passing parameters in a function call.`

## Avoid placing spaces around code in parentheses or square brackets

```
if (debug)   # Good
if ( debug ) # Bad
if (debug )  # Bad
if ( debug)  # Bad

x[1]   #Good
x[ 1 ] #Bad
x[1 ]  #Bad
x[ 1]  #Bad
```

### Exception

Always place a space after a comma:

```
x[1, ] #Good
x[1,]  #Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Do not place spaces around code in parentheses or square brackets. Exception:  Always place a space after a comma.`

## Prefer indenting with two spaces

```
if (x == 42) {
  print("Yes!")
}
```

### Exception

When a line break occurs inside parentheses, 
align the wrapped line with the first character inside the parenthesis.

Extra spacing is okay if it improves alignment of equals signs `=` or arrows `<-`.

```
plot(
  x    = xs,
  y    = ys,
  xlab = "X",
  ylab = "Y",
  main = "Title"
)
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `When indenting your code, use two spaces.  Never use tabs or mix tabs and spaces. Exception: When a line break occurs inside parentheses, align the wrapped line with the first character inside the parenthesis.`
* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Extra spacing (i.e., more than one space in a row) is okay if it improves alignment of equals signs or arrows (<-).`

## Avoid using tabs

```
[Example here]
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `When indenting your code, use two spaces.  Never use tabs or mix tabs and spaces.`

## Avoid placing a space before a comma. Prefer to place a space after a comma

```
t <- sum(x[, 1]) # Good
t <- sum(x[1, ]) # Good
t <- sum(x[,1]) # Bad
t <- sum(x[1,]) # Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Do not place a space before a comma, but always place one after a comma.`
           
## Prefer placing a space before a left parenthesis, except when calling a function

```
if (debug) # Good
if(debug)  # Bad
print("Hello")  #Good
print ("Hello") #Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Place a space before left parenthesis, except in a function call.`






## Prefer putting an opening curly brace at the end of a line. Prefer to put a closing curly brace on its own line

```
# GOOD
if (x == 42) {
  # ...
}

# BAD
if (x == 42)
{
  # ...
}

# BAD
if (x == 42)
  {
  # ...
  }
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `An opening curly brace should never go on its own line; a closing curly brace should always go on its own line.`




## Be consistent in ommitting curly braces when they can be ommitted

You may omit curly braces when a block consists of a single statement:

```
# Good: keeping the curly braces
if (x == 42) {
  print("OK")
}

if (y == 314) {
  print("OK")
}

# Good: ommitting the curly braces
if (x == 42) 
  print("OK")

if (y == 314) 
  print("OK")

# Bad: inconsistency in ommitting the curly braces
if (x == 42) 
  print("OK")

if (y == 314) {
  print("OK")
}
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `You may omit curly braces when a block consists of a single statement; however, you must consistently either use or not use curly braces for single statement blocks.`

## Prefer to begin the body of a block on a new line

```
# OK
if (x == 42) {
  print("OK")
}

# Bad?
if (x == 42) { print("Bad") }
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Always begin the body of a block on a new line.`

## Prefer to surround `else` with braces

```
# OK
if (x == 42) {
  # ...
} else {
  # ...
}


# Bad
if (x == 42) {
  # ...
} 
else {
  # ...
}

# Bad
if (x == 42)
  # ...
else
  # ...
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Surround else with braces. An else statement should always be surrounded on the same line by curly braces.`





## When modifying other people's code, follow their coding standard

```
[Example here]
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Use common sense and BE CONSISTENT. If you are editing code, take a few minutes to look at the code around you and determine its style. If others use spaces around their if clauses, you should, too. If their comments have little boxes of stars around them, make your comments have little boxes of stars around them, too. The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you are saying, rather than on how you are saying it. [...]. But local style is also important. If code you add to a file looks drastically different from the existing code around it, the discontinuity will throw readers out of their rhythm when they go to read it. Try to avoid this.`

## Do not put more than one command on the same line
          
```            
x <- 42; y <- 314 # Bad

# Good:
x <- 42
y <- 314
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Do not terminate your lines with semicolons or use semicolons to put more than one command on the same line`

## Prefer using S3 over S4 

```
[Example here]
```          

### Exceptions

Justifications for an S4 object would be:

 * to use objects directly in C++ code
 * to dispatch on two arguments

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Use S3 objects and methods unless there is a strong reason to use S4 objects or methods. A primary justification for an S4 object would be to use objects directly in C++ code. A primary justification for an S4 generic/method would be to dispatch on two arguments.`

## Avoid mixing S3 and S4

```
[Example here]
```          

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Avoid mixing S3 and S4: S4 methods ignore S3 inheritance and vice-versa`


# Identifiers

## Prefer naming non-constant variables in all lower case separated with dots

```
my.value # Good
myVlicks # OK: this is tolerated
my_value # Bad
my-value # Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Identifiers should be named according to the following conventions. The preferred form for variable names is all lower case letters and words separated with dots (variable.name), but variableName is also accepted.`

## Prefer naming constant variables in kCamelCase

```
kPi <- 3.14
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `constants are named like functions but with an initial k`

## Don't use underscores ( _ ) or hyphens ( - ) in identifiers

```
my.value # Good
myVlicks # OK: this is tolerated
my_value # Bad
my-value # Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Identifiers should be named according to the following conventions. The preferred form for variable names is all lower case letters and words separated with dots (variable.name), but variableName is also accepted.`
* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Don't use underscores ( _ ) or hyphens ( - ) in identifiers`

## Prefer naming functions in CamelCase

```
CalculateVariance # Good
calculateVariance # Bad
calculate_variance # Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `function names have initial capital letters and no dots`

## Prefer the first word of a function being a verb

```
MeasureSpeed # Good
Speed # Bad
```

### Exception

When creating a class object, the function name (constructor) and class name should match

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Make function names verbs`
* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `When creating a class object, the function name (constructor) and class name should match`

## Prefer to start function definition argument lists with the non-defaultable values

```
# Good
Transmogrify <- function(
  x,
  y = 42
)

# Bad
Transmogrify <- function(
  x = 314,
  y
)
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Function definitions should first list arguments without default values, followed by those with default values.`



## Prefer to optionally use line breaks in function definitions between assignments only

```
# Good
Transmogrify <- function(
  x = 314,
  y = 42
)

# Good
Transmogrify <- function(x = 314, y = 42)

# Bad
Transmogrify <- function(x 
  = 314, y = 42)
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `In both function definitions and function calls, multiple arguments per line are allowed; line breaks are only allowed between assignments.`

## Prefer to optionally use line breaks in function calls between assignments only

```
# Good
Transmogrify(
  x = 314,
  y = 42
)

# Good
Transmogrify(x = 314, y = 42)

# Bad
Transmogrify(x 
  = 314, y = 42)
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `In both function definitions and function calls, multiple arguments per line are allowed; line breaks are only allowed between assignments.`






## Prefer to describe a function in comments in the line(s) directly below the function definition

These comments may consist of:

 * a one-sentence description of the function
 * a list of the function's arguments, denoted by Args:, with a description of each (including the data type)
 * and a description of the return value, denoted by Returns:

The comments should be descriptive enough that a caller can use the function without reading any of the function's code.

```
SumFloats <- function(x) {
  # Calculates the sum of a vector of floats
  # Args: x: a vector containing zero or more floating point values
  # Returns: the sum of the vector as a floating point
}
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Functions should contain a comments section immediately below the function definition line. These comments should consist of a one-sentence description of the function; a list of the function's arguments, denoted by Args:, with a description of each (including the data type); and a description of the return value, denoted by Returns:. The comments should be descriptive enough that a caller can use the function without reading any of the function's code.`



          


# Operator use

## Prefer using `<-` over `=` for assignment.
          
```            
x <- 42 # Good
x = 42  # Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Use <-, not =, for assignment`

## Avoid using semicolons `;`
          
```            
x <- 42  # Good
x <- 42; # Bad
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Do not terminate your lines with semicolons or use semicolons to put more than one command on the same line`

# File naming

## Prefer meaningful files names ending in  `.R`

 * Good filenames: `predict_ad_revenue.R`
 * Bad filenames: `predict_ad_revenue.r`,`foo.R`

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `File names should end in .R and, of course, be meaningful`

## Prefer naming unit test files ending in `_test.R`

 * Good filenames: `predict_ad_revenue_test.R`
 * Bad filames: `test_predict_ad_revenue.R`

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Unit tests should go in a separate file named originalfilename_test.R.`




          



# Function use

## Prefer using `typeof()` over `mode()`

`mode()` is an alias of `typeof()` that only exists for S compatibility [1].

### References

 * [1] Wickham, Hadley. Advanced R. CRC Press, 2014. Page 102

## Prefer using `typeof()` over `storage.mode()`

### References

 * [1] Wickham, Hadley. Advanced R. CRC Press, 2014. Page 102


## Avoid using `attach`

```
[Example here]
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `The possibilities for creating errors when using attach are numerous. Avoid it.`

# Miscellaneous



## Be consistent in the ordering of a file

An example ordering:
 * Copyright statement comment 
 * Author comment
 * File description comment, including purpose of program, inputs, and outputs
 * `source()` and `library()` statements
 * Function definitions
 * Executed statements, if applicable, for example `print` and `plot`

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `If everyone uses the same general ordering, we'll be able to read and understand each other's scripts faster and more easily.`



## Prefer to add comments to your code

```
# Determine if expensive calculation can be avoided
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Comment your code`

## Prefer to start an entire-line-comment with `#` and one space

```
# Determine if expensive calculation can be avoided
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Entire commented lines should begin with # and one space.`



## For code directly after code, add two spaces, `#` and then one space

```
if (x == 42) {  # Are we lucky?
  # ...
}
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Short comments can be placed after code preceded by two spaces, #, and then one space.`

## Errors should be raised using stop()

```
if (x < 0) stop()
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Errors should be raised using stop()`

## Prefer to put unit tests in seperate files

See also 'prefer naming unit test files ending in `_test.R`'

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Unit tests should go in a separate file named originalfilename_test.R.`

## Prefer to let your unit tests serve as example function calls

```
[Example]
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Ideally, unit tests should serve as sample function calls (for shared library routines).`

## Prefer to use a consistent style for TODOs

For example:

```
TODO([username]): [Explicit description of action to be taken]
```

Like:

```
TODO(richelbilderbeek): Check if this really works
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Use a consistent style for TODOs throughout your code. TODO(username): Explicit description of action to be taken`
