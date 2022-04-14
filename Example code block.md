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
### 1. Vector
```R
# Create a vector.
student <- c('james','mark',"jane")
print(student)
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

### 2. Matrix
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

```

```R

```

```R

```
