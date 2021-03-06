R Style Guide
========================================================
author: based on Hadley Wickham's Style Guide
date: 2016-06-07
autosize: true

Goal of R Style Guide
========================================================
To make our R code easier to read, share, and verify


Goal of R Style Guide
========================================================
> "Good coding style is like using correct punctuation. You can manage without it, but it sure makes things easier to read. As with styles of punctuation, there are many possible variations. The following guide describes the style that I use. You don’t have to use my style, but **you really should use a consistent style.**"  
> --- Hadley Wickham

Why is Style Important?
========================================================
Writing code for communication is important because your code will have one author (you!) but multiple readers:

- You, when you're writing it
- Me, coworkers, and friends
- Github users
- Future you, when you look at the code in 6 months later


Why is Style Important?
========================================================
- When you’re writing code with others, it’s a good idea to agree on **a common style** up-front
- Since no style is strictly better than another, working with others may mean that you’ll need to **sacrifice** some preferred aspects of your style


Notation and Naming: File Names
========================================================
File names should be **meaningful** and end in **`.R`**

    # Good
    fit-models.R
    utility-functions.R

    # Bad
    foo.r
    stuff.r


Notation and Naming: File Names
========================================================
If files need to be run in sequence, **prefix** them with numbers:

    0-download.R
    1-parse.R
    2-explore.R
    3-visualize.R


Notation and Naming: Object Names
========================================================
> "There are only two hard things in Computer Science: cache invalidation and naming things." 
>
> --- Phil Karlton


Notation and Naming: Object Names
========================================================
- Variable and function names should be **lowercase**
- Use an **underscore** (**`_`**) to separate words within a name
- Generally, *variable* names should be **nouns** and *function* names should be **verbs**
- Strive for names that are **concise** and **meaningful**


Notation and Naming: Object Names
========================================================

```r
# Good
day_one
day_1

# Bad
first_day_of_the_month
DayOne
dayone
djm1
```


Notation and Naming: Object Names
========================================================
Where possible, avoid using names of **existing** functions and variables


```r
# Bad
T <- FALSE
c <- 10
mean <- function(x) sum(x)
```


Syntax: Spacing
========================================================
- Place spaces around all infix operators (`=`, `+`, `-`, `<-`, etc.)
- The same rule applies when using `=` in function calls
- Always put a space after a comma, and never before


```r
# Good
average <- mean(feet / 12 + inches, na.rm = TRUE)

# Bad
average<-mean(feet/12+inches,na.rm=TRUE)
```


Syntax: Spacing
========================================================
There's a small exception to this rule: `:`, `::` and `:::` don't need spaces around them


```r
# Good
x <- 1:10
base::get

# Bad
x <- 1 : 10
base :: get
```


Syntax: Spacing
========================================================
Place a space before left parentheses, except in a function call


```r
# Good
if (debug) do(x)
plot(x, y)

# Bad
if(debug)do(x)
plot (x, y)
```

Syntax: Spacing
========================================================
**Extra spacing** (i.e., more than one space in a row) is **ok** if it improves alignment of equal signs or assignments (`<-`)


```r
list(
  total = a + b + c, 
  mean  = (a + b + c) / n
)
```


Syntax: Spacing
========================================================
Do not place spaces around code in parentheses or square brackets (unless there's a comma, in which case see above)


```r
# Good
if (debug) do(x)
diamonds[5, ]

# Bad
if ( debug ) do(x)  # No spaces around debug
x[1,]   # Needs a space after the comma
x[1 ,]  # Space goes after comma not before
```


Syntax: Curly Braces
========================================================
- An **opening curly brace** should **never** go on its own line and should always be followed by a new line
- A **closing curly brace** should **always** go on its own line, unless it's followed by `else`


Syntax: Curly Braces
========================================================
Always indent the code inside curly braces


```r
# Good

if (y < 0 && debug) {
  message("Y is negative")
}

if (y == 0) {
  log(x)
} else {
  y ^ x
}
```


Syntax: Curly Braces
========================================================

```r
# Bad

if (y < 0 && debug)
message("Y is negative")

if (y == 0) {
  log(x)
} 
else {
  y ^ x
}
```


Syntax: Curly Braces
========================================================
It's **ok** to leave very short statements on the same line:


```r
if (y < 0 && debug) message("Y is negative")
```


Syntax: Line Length
========================================================
- Try to limit your code to **80 characters** per line
- This fits comfortably on a printed page with a reasonably sized font
- If you find yourself running out of room, this is **a good indication** that you should **encapsulate** some of the work in a separate function


Syntax: Indentation
========================================================
- When indenting your code, use **two spaces**
- **Never** use tabs or mix tabs and spaces


Syntax: Indentation
========================================================
If a function definition runs over multiple lines, indent the second line to where the definition starts:


```r
long_function <- function(a = "a long argument", 
                          b = "another argument", 
                          c = "another long argument") {
  # As usual code is indented by two spaces.
}
```


Syntax: Assignment
========================================================
Use `<-`, not `=`, for assignment


```r
# Good
x <- 5
# Bad
x = 5
```


Organisation: Commenting Guidelines
========================================================
- **Comment your code**
- Each line of a comment should begin with the comment symbol and a single space
- Comments should explain the **why**, not the what


Organisation: Commenting Guidelines
========================================================
Use commented lines of `-` and `=` to break up file into easily readable chunks


```r
# Load data ---------------------------

# Plot data ---------------------------
```


formatR package by Yihui Xie
========================================================
- http://yihui.name/formatR/
- Format R code **automatically** and provides:
  - A function `tidy_source()` to format R source code
  - A **Shiny app** as a user interface
- Makes it easier to clean up poorly formatted code
- Make sure to read the introduction before using it


References
========================================================
- [Advanced R by Hadley Wickham](http://adv-r.had.co.nz/Style.html)
- [Google R Style Guide](https://google.github.io/styleguide/Rguide.xml)
- [formatR](http://yihui.name/formatR/)


Spaces vs. Tabs
========================================================
[Silicon Valley](https://youtu.be/cowtgmZuai0)
