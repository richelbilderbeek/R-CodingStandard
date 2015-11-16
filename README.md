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

            














## Prefer indenting with two spaces

```
if (x == 42) {
  print("Yes!")
}
```

### Exception

When a line break occurs inside parentheses, 
align the wrapped line with the first character inside the parenthesis.

```
[Example here]
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `When indenting your code, use two spaces.  Never use tabs or mix tabs and spaces. Exception: When a line break occurs inside parentheses, align the wrapped line with the first character inside the parenthesis.`

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

 * Good filames: `predict_ad_revenue.R`
 * Bad filenames: `predict_ad_revenue.r`,`foo.R`

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `File names should end in .R and, of course, be meaningful`

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

# Error handling

## Errors should be raised using stop()

```
if (x < 0) stop()
```

### References

* [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml): `Errors should be raised using stop()`













Summary: R Style Rules

    
      
      Curly Braces: first on same line, last on
        own line
      else: Surround else with braces 
      Assignment: use <-, not
        =
      Semicolons: don't use them
       General Layout and Ordering
       Commenting Guidelines: all comments begin
        with # followed by a space; inline comments need two
        spaces before the #
      Function Definitions and Calls
       Function Documentation
       Example Function
       TODO Style: TODO(username)
    





          
          

          

          
          
            Extra spacing (i.e., more than one space in a row) is okay if it
            improves alignment of equals signs or arrows (<-).
          
plot(x    = x.coord,
     y    = data.mat[, MakeColName(metric, ptiles[1], "roiOpt")],
     ylim = ylim,
     xlab = "dates",
     ylab = metric,
     main = (paste(metric, " for 3 samples ", sep = "")))

          

            Do not place spaces around code in parentheses or square brackets.
            
 Exception:  Always place a space after a comma.
          
          
            GOOD:if (debug)
x[1, ]
          

            BAD:if ( debug )  # No spaces around debug
x[1,]  # Needs a space after the comma 

          
Curly Braces
    
            An opening curly brace should never go on its own line; a closing
            curly brace should always go on its own line.  You may omit curly
            braces when a block consists of a single statement; however, you
            must consistently either use or not use curly braces for
            single statement blocks.
          
          
if (is.null(ylim)) {
  ylim <- c(0, 0.06)
}
          

            xor (but not both)
          
          
if (is.null(ylim))
  ylim <- c(0, 0.06)
          

            Always begin the body of a block on a new line.
          
          
            BAD:
            
 if (is.null(ylim))
              ylim <- c(0, 0.06)
            
 if (is.null(ylim))
              {ylim <- c(0, 0.06)} 
          

          Surround else with braces
    
            An else statement should always be surrounded on the
            same line by curly braces.
          
if (condition) {
  one or more lines
} else {
  one or more lines
}

          

            BAD:

          
          
if (condition) {
  one or more lines
}
else {
  one or more lines
}

          

            BAD:

          
          
if (condition)
  one line
else
  one line


        
          
          


     Organization 
        General Layout and Ordering
          
            If everyone uses the same general ordering, we'll be able to
            read and understand each other's scripts faster and more easily.
          
          
            Copyright statement comment 
            Author comment
            File description comment, including purpose of
              program, inputs, and outputs
            source() and library() statements
            Function definitions
            Executed statements, if applicable (e.g.,
               print, plot)
          
          
            Unit tests should go in a separate file named
            originalfilename_test.R.
          
        Commenting Guidelines
          
            Comment your code. Entire commented lines should begin with
            # and one space.
          
          
            Short comments can be placed after code preceded by two spaces,
            #, and then one space.
          
# Create histogram of frequency of campaigns by pct budget spent.
hist(df$pct.spent,
     breaks = "scott",  # method for choosing number of buckets
     main   = "Histogram: fraction budget spent by campaignid",
     xlab   = "Fraction of budget spent",
     ylab   = "Frequency (count of campaignids)")

        
Function Definitions and
          Calls
          
            Function definitions should first list arguments without default
            values, followed by those with default values.
          
          
            In both function definitions and function calls, multiple
            arguments per line are allowed; line breaks are only allowed
            between assignments.
            
GOOD:
          
PredictCTR <- function(query, property, num.days,
                       show.plot = TRUE)

           BAD:
PredictCTR <- function(query, property, num.days, show.plot =
                       TRUE)

          
 Ideally, unit tests should serve as sample function calls (for
            shared library routines).
          
        Function Documentation
           Functions should contain a comments section immediately below
            the function definition line. These comments should consist of a
            one-sentence description of the function; a list of the function's
            arguments, denoted by Args:, with a description of
            each (including the data type); and a description of the return
            value, denoted by Returns:. The comments should be
            descriptive enough that a caller can use the function without
            reading any of the function's code.
          

        Example Function

CalculateSampleCovariance <- function(x, y, verbose = TRUE) {
  # Computes the sample covariance between two vectors.
  #
  # Args:
  #   x: One of two vectors whose sample covariance is to be calculated.
  #   y: The other vector. x and y must have the same length, greater than one,
  #      with no missing values.
  #   verbose: If TRUE, prints sample covariance; if not, not. Default is TRUE.
  #
  # Returns:
  #   The sample covariance between x and y.
  n <- length(x)
  # Error handling
  if (n <= 1 || n != length(y)) {
    stop("Arguments x and y have different lengths: ",
         length(x), " and ", length(y), ".")
  }
  if (TRUE %in% is.na(x) || TRUE %in% is.na(y)) {
    stop(" Arguments x and y must not have missing values.")
  }
  covariance <- var(x, y)
  if (verbose)
    cat("Covariance = ", round(covariance, 4), ".\n", sep = "")
  return(covariance)
}


TODO Style


  Use a consistent style for TODOs throughout your code.
  
TODO(username): Explicit description of action to
    be taken

