## Chapter 01: R căn bản

```R
# Print a text
print("Hello World")
```

```R
# Declare a variable helloString
helloString <- "Hello" 
print (helloString) # print hello
```

## Chapter 02: Kiểu dữ liệu trong R
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

```R

```
