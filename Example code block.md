## Chapter 01: R căn bản

```R
# print a text
print("Hello World")
```

```R
# declare a variable helloString
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
# a numeric vector
vector1 <- c(1, 2, 5.3, 6, -2,4) 
# a logical vector
vector2 <- c(TRUE, TRUE, TRUE, FALSE, TRUE) 
print(vector1) 
print(vector2)
```

```R
# a numeric vector 
vector1 <- c(1,2,5.3,6,-2,4) 
#a logical vector
vector2 <- c(TRUE,TRUE,TRUE,FALSE,TRUE)
# access 2nd and 4th elements of the vector 
print(vector1[c(2,4)]) 
# access 1st and 4th elements of the vector
print(vector2[c(1,4)])
```

```R
# a numeric vector from start value to end value
v <- 1:8; v
```

```R
# Declare vector of numbers with descending value
v <- 2:-2; v
```

```R
# using seq() function
seq(1, 3, by=0.7) # define the step size
```

```R
# define vector length
seq(1, 5, length.out = 4)
```

```R
# change the value of vector's element
x[3] = 7; x
```

```R
# handle data on multiple elements
x[x<4] = 0; x
```

```R
# delete a vector
x <- NULL; x
```

### 2. Matrix
```R
# Create a matrix.
M = matrix( c('x','x','y','z','t','x'), nrow = 2, byrow = TRUE)
print(M)
```

```R
# another way to define a maxtrix
matrix(1:12, nrow = 4)
matrix(1:12, nrow = 4, byrow = TRUE)
```

```R
# change columns and rows name of matrix
x <- matrix(1:12, nrow = 4, dimnames = list(c("W","X","Y" ,"Z"), c("A","B","C")))
print(x)
```

```R
# get columns and rows name of matrix
colnames(x)
rownames(x)
```

```R
# using cbind() and rbind() functions to define matrix
cbind(c(1, 6, 9),c(3, 5, 8))
rbind(c(1, 6, 9),c(3, 5, 8))
```

```R
# access sub-matrix include 1st and 2nd rows, 2nd and 3rd columns
x[c(1, 2),c(2, 3)]

# if the column field is left blank then all columns will be accessed.
x[c(1, 2), ] # Column field is emplty.
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
