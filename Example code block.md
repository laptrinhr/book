## Chapter 01:	R Basics

```R
# Print a text
print("Hello World")
```

```R
# Declare a variable helloString
helloString <- "Hello" 
print (helloString) # print hello
```

## Chapter 02: R Data Types
### 2.1. Vector
```R
# Create a vector.
student <- c('james','mark',"jane")
print(student)
```

```R
# Get the class of our vector.
print(class(student))
```

```R
# A numeric vector
vector1 <- c(1, 2, 5.3, 6, -2,4) 
# A logical vector
vector2 <- c(TRUE, TRUE, TRUE, FALSE, TRUE) 
print(vector1) 
print(vector2)
```

```R
# A numeric vector 
vector1 <- c(1,2,5.3,6,-2,4) 
# A logical vector
vector2 <- c(TRUE,TRUE,TRUE,FALSE,TRUE)
# Access 2nd and 4th elements of the vector 
print(vector1[c(2,4)]) 
# Access 1st and 4th elements of the vector
print(vector2[c(1,4)])
```

```R
# A numeric vector from start value to end value
v <- 1:8; v
```

```R
# Declare vector of numbers with descending value
v <- 2:-2; v
```

```R
# Using seq() function
seq(1, 3, by=0.7) # define the step size
```

```R
# Define vector length
seq(1, 5, length.out = 4)
```

```R
# Change the value of vector's element
x <- 1:5
x[3] = 7; x
```

```R
# Handle data on multiple elements
x[x<4] = 0; x
```

```R
# Delete a vector
x <- NULL; x
```

### 2.2. Matrix
```R
# Create a matrix.
M = matrix( c('x','x','y','z','t','x'), nrow = 2, byrow = TRUE)
print(M)
```

```R
# Another way to define a maxtrix
matrix(1:12, nrow = 4)
matrix(1:12, nrow = 4, byrow = TRUE)
```

```R
# Change columns and rows name of matrix
x <- matrix(1:12, nrow = 4, dimnames = list(c("W","X","Y" ,"Z"), c("A","B","C")))
print(x)
```

```R
# Get columns and rows name of matrix
colnames(x)
rownames(x)
```

```R
# Using cbind() and rbind() functions to define matrix
cbind(c(1, 6, 9),c(3, 5, 8))
rbind(c(1, 6, 9),c(3, 5, 8))
```

```R
# Access sub-matrix include 1st and 2nd rows, 2nd and 3rd columns
x[c(1, 2),c(2, 3)]

# If the column field is left blank then all columns will be accessed.
x[c(1, 2), ] # Column field is emplty.
```

```R
# Remove element with negative index
x[-1, ]
```
 
```R
# If the result has only 1 row or 1 column then it will be degraded to vector
class(x)
x[1, ]
class(x[1, ])
# The drop = FALSE property can be used to prevent matrix-to-vector degradation
x[1, , drop = FALSE]
class(x[1, , drop = FALSE])
```

```R
# The matrix can be used as a vector using the index of the elements
# Note that the index of an element will be column-typed.
x
x[1:4]
x[c(3,5,7)]
```

```R
# The value of an element in a matrix can be accessed and changed using the element's index
x
x[1,3] <- 5
x
```

```R
#The elements of a matrix can also be accessed and batch processed with a single query condition
x[x<3] <- 0; x
```

```R
#The rbin() and cbin() functions can be used to add new rows and columns to an existing matrix
cbind(x, c(1, 1),  c(2, 2)) #add new columns
rbind(x,c(3,3,3), c(3,3,3)) #add new rows
```

```R
# We can remove rows and columns from a matrix by assigning it to its submatrix
x <- x[ , -c(1,2), drop = FALSE]
x
```

### 2.3. List
```R
# Create a list.
sampleList <- list(c("a","b","c"),1.27, sin)
# Print the list.
print(sampleList)
```

```R
# Check if an R-object is a list using typeof() or class() Functions
typeof(sampleList)
class(sampleList)
```

```R
# Get number of elements in the list
length(sampleList)
```

```R
# remove 1st element in the list
sampleList <- sampleList [-1]
print(sampleList)
# add a element into list
sampleList <- c(sampleList, 15)
print(sampleList)
```

### 2.4. Array
```R
# Create an array
arr <- array(c('cat', 'dog'),dim = c(2,3,2)) 
print(arr)
```

### 2.5. Data frame
```R
# Create a data frame
index <- 1:3
names <- c("Steve", "Bill", "Mark")
ages <- c(21, 34, 55)
staffData <- data.frame("index"=index, "name"=names, "age"=ages) 
str(staffData)
```

```R
# Display data frame
staffData
```

```R
# The elements of the data frame can be accessed using row and column indexes
staffData[1,2]
```

```R
# The [], [[]] and $ operators allow access to the data frame's data fields as a list.
staffData["name"]
staffData$name
staffData[["name"]]
```

```R
# Introduction about "tree" data set
str(trees)
```

```R
# Get n element of "tree" data set
head(trees, n = 5)
```

```R
# R allows users to access and use data frame data in the form of matrices.
trees[c(1,3,5,7,9), ]
```

```R
# Get all data that satisfy the condition
trees[trees$Height < 66, ]
```

```R
# Change the value of an element in the data frame
staffData[1, "name"] <- "Tim"
staffData
```

```R
# The rbind() function can be used to add data to a data frame
rbind(staffData ,list(4, "Larry", 35))
```

```R
# cbind() function allows to add a new column of data to the data frame
pos <- c("Guard", "Officer", "IT")
cbind(staffData,  "position" = pos)
```

```R
# Add new columns to the data frame using assignments
pos <- c("Guard", "Officer", "IT")
staffData$position <- pos; staffData
```

```R
# To delete a column of data in the data frame, simply assign the value NULL to it
staffData$position <- NULL; staffData
```

```R
# Delete a data record by assigning that data frame to its child data frame 
# with a negative index row of data to be deleted.
staffData <- staffData[-1,]; staffData
```

### 2.6. Factor
```R
# Create a factor
d <- c("high", "low", "v.high", "low", "v.low", "high", "high")
f <- factor(d); f
```

```R
# Redefine the order of levels in factor
vecLevel <- c("v.high","high","low","v.low")
f <- factor(f, levels = vecLevel); f
```

```R
# Create a factor using gl() function
fruits <- c("Apple", "Lemon", "Orange", "Banana")
f_fruits <- gl(2, 3, labels = fruits); 
f_fruits
```

```R
# Access and change elements of factor
f_fruits[3] <- "Orange"
f_fruits[4] <- "Banana"
f_fruits
```

### 2.7. String
```R
# Create a string
str <- "Hello! I'm a R coder."
str
```

```R
# Strings can be concatenated using the paste() function.
x <- "Hello!"
y <- "How are you"
z <- "today"
hello <- paste(x, y, z , "?", sep = " ")
hello
```

```R
# Get length of string
nchar(hello)
```

```R
# Convert all characters in a string to uppercase or lowercase
tolower(hello)
toupper(hello)
```

```R
# Get a substring
substring("The quick brown fox", 5, 15)
```

## Chapter 03: R Variables and Constants 
### 3.1. Variable
```R
# use rightward  and leftward operator to create or assign a value to a variable
var1 <- c(1,2,3,4) -> var2
# use equal operator
var3 = c("R", "programming language")
# print variables
print(var1)
print(var2)
print(var3)
```

```R
# Check variable data type in R
x <- "Hello"
cat("The class for x is",class(x),"\n") 
x <- 34.5
cat("and, x becomes a(n)",class(x),"\n") 
x <- list(c("a", "b"), 12)
cat("Lastly, x changed to",class(x),"\n")
```

```R
# List all existing variables
ls()
```

```R
# List all existing variables with pattern
ls(pattern = "ar")
```

```R
# Delete a variable
rm(var3)
var3
```

```R
# Delete all variables
rm(list = ls())
ls()
```

### 3.1. Constant
```R
# The data type of a constant
typeof(10)
typeof(8L)
typeof(7i)
```

```R
# Built-in constants
pi
LETTERS
letters
month.name
month.abb
```

```R
# Input data from keyboard
name <- readline(prompt="Name: ") 
age <- readline(prompt="Age: ")
# convert the character to an integer 
age <- as.integer(age)
print(paste("Hi", name, "next year you will be", age+1, "years old."))
```

## Chapter 04: R Operators
### 4.1. Arithmetic operators
```R
# Example of arithmetic operators
cat("Input two numbers x and y","\n")
x <- readline(prompt="x = ")
x <- as.integer(x)
y <- readline(prompt="y = ")
y <- as.integer(y)
cat("x + y =", x + y, "\n")
cat("x - y =", x - y, "\n")
cat("x * y =", x * y, "\n")
cat("x / y =", x / y, "\n")
cat("x %/% y =", x %/% y, "\n") 
cat("x %% y =", x %% y, "\n") 
cat("x ^ y =", x^y, "\n")
```

### 4.2. Relational operators
```R
# Example of relational operators
cat("Input two numbers x and y","\n")
x <- readline(prompt="x = ")
x <- as.integer(x)
y <- readline(prompt="y = ")
y <- as.integer(y)
cat("x < y is", x < y, "\n")
cat("x > y is", x > y, "\n")
cat("x <= y is", x <= y, "\n")
cat("x >= y is", x >= y, "\n")
cat("x == y is", y == x, "\n") 
cat("x != y is", y != x, "\n")
```

### 4.3. Logical operators
```R
# Example of logical operators
x <- c(FALSE, TRUE, 0, 9)
y <- c(TRUE, FALSE, FALSE, TRUE)
cat("!x =",!x,"\n")
cat("x&y =",x&y,"\n")
cat("x&&y =",x&&y,"\n")
cat("x|y =",x|y,"\n")
cat("x||y =",x||y,"\n")
cat("xor(x,y) =",xor(x, y),"\n")
```

### 4.4. Assignment operators
```R
# Example of assignment operators
x <- "a"; x
1:9 -> x; x
x = 10; x
```

### 4.5. Operator precedence
```R
# Operators with higher precedence are always executed first
1 + 5 * 3
(1 + 5) * 3
```

## Chapter 05: Decision Making in R 
### 5.1. If statement
```R
# Example of if statement
cat("Input your mark from 0 to 100", "\n")
mark <- readline("Your mark: ")
if (mark >= 50){
   cat("You passed the exam", "\n")
}
if (mark < 50){
   cat("You failed the exam", "\n")
}
```

### 5.2. if…else statement
```R
# Example of if…else statement
cat("How old are you?", "\n")
age <- readline("Your age: ")
if (age < 18){
   cat("Your age is less than 18", "\n")
} else {
   cat("Your age is above 18", "\n")
}
```

### 5.3. if…else ladder
```R
# Example of if…else ladder
cat("Input your mark from 0 to 100", "\n")
mark <- readline(" Your mark: ")
if (mark > 89){
   cat(" You get an A graded")
} else if (mark > 69){
   cat(" You get an B graded")
} else if (mark > 54){
   cat(" You get an C graded")
} else if (mark > 49){
   cat(" You get an D graded")
} else {
   cat(" You get an F graded")
}
```

### 5.3. switch statement
```R
# Example of switch statement
x <- 2
y <- switch(x,"apple","lemon","orange")
print(y)
```

```R
# If the value of the variable is out of range, the switch statement will return NULL
x <- 5
y <- switch(x,"apple","lemon","orange")
print(y)
```

```R
# The switch statement also allows a string to be used as an input argument
switch("name","name" = "John", "age" = 20, "country" = "USA")
```

## Chapter 06: R loops
### 6.1. Repeat loop
```R
# Example of repeat loop
count <- 0
repeat {
   count <- count + 1
   cat("Count:", count, "\n")
   if (count >= 4) {
       break
   }
}
```

```R
# Stop loop conditional
n <- readline("Please enter a number n = ")
n <- as.integer(n)
count <- 2
repeat {
    if (n%%count == 0 || count == n%/%2) {
        break;
    }
    count <- count + 1
}
if (count < n%/%2) {
    cat(n, "is not a prime number")
} else {
    cat(n, "is a prime number")
}
```

### 6.2. while loop
```R
# Example of while loop
count <- 1
while (count < 5) {
    cat("Count:", count, "\n")
    count <- count + 1
}
```

```R
# Stop loop conditional
# Please run as R script file
cat("Lottery ticket vending machine", "\n")
cat("Please input six numbers from 00 to 99: ", "\n")
count <- 1
ticket <- 1:6
while (count <= 6) {
    cat(count, ". ")
    ticket[count] <- readLines("stdin", 1)
    count <- count + 1
}
cat("Your ticket: ", "\n")
ticket
```

### 6.3. for loop
```R
# Example of for loop
for (month in month.abb[1:6]) {
    cat(month, " ")
}
```

```R
sentence <- unlist(strsplit("the quick brown fox jump over the lazy dog", ""))
count <- 0
for (char in sentence) {
    if (char == 'o') {
        count <- count + 1
    }
}
cat(count, "of 'o' character(s) found")
```

### 6.4. Next statement
```R
# Use next statement to skip current loop
values <- 1:10
for (x in values) {
    if (x %% 2 == 0) {
        next
    }
    cat(x, " ")
}
```

```R
n <- 15942039485511122
count <- 0
while (n != 0) {
    remainder <- n %% 10
    n <- n%/%10
    if (remainder != 5) {
        next
    }
    count <- count + 1;
}
cat(count,"digit(s) 5 found!")
```

## Chapter 07: Functions
### 7.1. Function definition
```R
# A function to return the squares of numbers in # a sequence.
squaresSequence <- function(n) { 
    for(value in 1:n) {
        square <- value^2
        print(square)
    }
}
```

```R
# function to print a raised to the power b result <- a^b
pow <- function(a, b) {
    result <- a^b
    print(paste(a,"^", b, "=", result))
}

```

```R
# Call the function squaresSequence() 
# and pass number 5 as an argument.
squaresSequence(5)
```

```R
# Call function example
fullName <- function(firstName, lastName) {
    cat(firstName, lastName, "\n");
}

# function call with params in order without names
fullName("Steve", "Job")

# function call with params passing value by names
fullName(lastName="Job", firstName="Steve")
```

```R
# Use default parameter in function
division <- function(x, y, precision = 6){
    result <- round(x/y, digits = precision)
    cat(result, "\n");
}
division(x = 7, y = 3)
division(x = 7, y = 3, precision = 2)
```

### 7.2. Return function
```R
# Return value from function
circleArea <- function(r) {
    result <- pi*r*r;
    return (result)
}
radius <- 5
area <- circleArea(radius)
cat("The area of a circle with radius", radius, "is:", area)
```

```R
# Return in the middle of the function
check <- function(value) {
    if (value > 0) {
        return ("value is Positive")
    }
    else if (value < 0) {
        return ("value is Negative")
    }
    else {
        return ("value is Zero")
    }
    cat("Unreachable statement")
}
result <- check(-6)
cat(result)
```

```R
# Multiple return values function
multi_return <- function() {
employee <- list("name" = "John", "age" = 20, "dept" = "ICT") 
    return(employee)
}
employee <- multi_return()
employee$name 
employee$age 
employee$dept
```

### 7.3. Scope variable
```R
# Global variable
x <- 1
func_one <- function(){
    y <- 2
    func_two <- function(){
        z <- 3 
    }
}
```

```R
# Local variable
x <- 9
func_one <- function(){
	x <- 12
	print(x)
}
func_one() 
print(x)
```

```R
# Using super assignment for global variable
x <<- 4
func_one <- function(){ 
    y <<- 7
}
func_two <- function(){ 
    print(y)
    x <<- 9
}
func_one()
func_two()
print(x)
```

### 7.4. Recursive functions
```R
# A recursive function to calculate factorial 
recur_factorial <- function(n) {
    if (n == 0) 
        return (1) 
    else
        return (n * recur_factorial(n-1))
}
recur_factorial(6)
recur_factorial(0)
recur_factorial(4)
recur_factorial(9)
```

## Chapter 08: Classes and Objects
### 8.1. S3 class
```R
# Declare class S3
student <- list(name = "Bob", age = 20, GPA = 3.2) 
class(student) <- "Student"
```

```R
# S3 Class constructor
student <- list(name="Bob", age=20, GPA= 3.2) 
# create a class from list
class(student) <- "Student"
# create a constructor for class "student" 
Student <- function(name, age, gpa) {
    # check age must be an integer
    if(age != round(age))
        stop("age must be an integer")
    value <- list(name=name, age=age, GPA=gpa)
    # set a class using attr function 
    attr(value, "class") <- "Student"
    value
}
newStudent <- Student("John", 19, 3.8)
newStudent
```

```R
# Create S3 object with invalid parameter
otherStudent <- Student("Alice", 18.4, 3.8)
```

### 8.2. Methods and generic functions
```R
# List all methods of a generic function
methods(print)
```

```R
# List all generic functions have default method
methods(class="default")
```

```R
# Declare method for a generic function
print.Student <- function(obj) { 
    cat("Name:", obj$name, ";")
    cat("Age: ", obj$age, ";")
    cat("GPA: ", obj$GPA, "\n")
}
print(student)
```

```R
# To see how to implement these generic functions, use their names without arguments as follows
print
plot
```

```R
# Declare my own generic function
myPrint <- function(obj) {
    UseMethod("myPrint")
}
```

```R
# Declare default method for our generic function
myPrint.default <- function(obj) {
    cat("this is my way to print\n")
}
```

```R
# Call our generic function
myPrint(student)
```

```R
# Defines handling methods for objects of class Student
myPrint.Student <- function(obj) {
    cat("Student name: ", obj$name, "\n")
    cat("Age: ", obj$age, "years old\n")
    cat("GPA: ", obj$GPA, "points\n")
}
myPrint(student)
```

### 8.3. S4 class
```R
# Declare class S4
setClass("Student", slots = list(name = "character",  age = "numeric", GPA = "numeric"))
```

```R
# Declare object of S4 class
student <- new("Student", name = "Steve", age = 21, GPA = 3.2)
show(student)
```

```R
# Checking S4 class object
isS4(student)
isS4(1:5)
```

```R
# Define S4 class generator
Student <- setClass("Student", slots=list(name="character",  age="numeric", GPA="numeric"))
Student
```

```R
# Using class generator to create object
Student(name="Jane", age=19, GPA=3.7)
```

```R
# Accessing and changing slot value in class S4
student@name
student@age
student@GPA
student@name <- "Tim"
show(student)
```

```R
# Accessing and changing slot value in class S4 using slot function
slot(student,"age") 
slot(student,"age") <- 22
show(student)
```

### 8.4. Generic functions with S4 class
```R
# Check if a function is a generic function used in class S4
isS4(show) 
isS4(print)
```

```R
# Define new generic functions for S4 class
setMethod("show", "Student", 
    function(object) {
        cat("Student information: \n")
        cat("Name:", object@name, "\n")
        cat("Age:", object@age, "years old\n")
        cat("GPA:", object@GPA, "points\n")
    }
)
```

```R
# Using new generic functions
s1 <- new("Student", name="Kate", age=18, GPA=3.3)
s1
```

### 8.5. Reference Class
```R
# Define a reference class
setRefClass("Student", fields = list(name = "character",  age = "numeric", GPA = "numeric"))
```

```R
# Declare an object
s <- Student(name="Paul",age=20,GPA=3.9)
show(s)
```

```R
# Accessing and changing slot value in reference class
s$name 
s$age 
s$GPA
s$name <- "Kevin"
show(s)
```

### 8.6. Reference methods
```R
# Define a reference methods
student <- setRefClass("Student",
    fields = list(
        name = "character", 
        age = "numeric", 
        GPA = "numeric"), 
    methods = list(
        increase_age = function(value) {
            age <<- age + value
        },
        decrease_age = function(value) {
            age <<- age - value
        }
    )
)
```

```R
# Using reference methods
s <- Student(name="Peter", age=21, GPA=3.3)
s$increase_age(2)
s$age
s$decrease_age(3)
s$age
```

```R

```

```R

```

```R

```

```R

```

```R

```

```R

```

```R

```

```R

```
 
9 R for Data Science
10 R for Machine Learning

Conclusion
