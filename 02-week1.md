# Basic

## vector and list

- `x <- 2` : assign

- `x <- 0:6` : assign給x 0~6的數字

- class
    
    - numeric

    - character

    - logical

    - complex

- 每一個vector只能有一個class，要混合不同種class在同一個變數裡的話要用list

    - Ex: `x <- list("a", 2, T, 1+4i)`

    - 不過把x print出來的形式不會是原本vector的樣子

## matrices

### matrix(data, nrow, ncol)

- `m = matrix(nrow= 2, ncol=3)`

- `dim(m)`: return (row, col)

> `attributes(m)` 可以看m有什麼東西能夠對他呼叫

- `m = matrix(1:6, nrow= 2, ncol=3)`

```
    [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6

```

### 指定資料和dim

-指定dimesion來創造matrix

```r
n <- 1:10
dim(n) <- c(2,5)
```

### binding rows, cols

- 第三種方式是binding col and row

```r
x <- 1:3
y <- 2:4
cbind(x,y)
rbind(x,y)
```

- 如果兩邊數字不一樣的話也可以bind，不過少的那一邊會重複直到匹配結束

### Factor

- 用來表示catergorical的data

- level(x), table(x)

### Missing Value

- `is.na()`

- `is.nan()`

- NAN is a NA , but the converse isn't true

### Data frame

- used to store tabular data

- 每一列都有名字，可以用`row.names`來呼叫

- 可以輕易的轉乘矩陣：`data.matrix()`

### Names

- 其實不只data frame能夠呼叫names，一般的vector也可以

```
> x <- 1:3
> x
[1] 1 2 3
> names(x) <- c('one', 'two', 'three')
> x
  one   two three 
    1     2     3    
```

- matrix也可以，不過要用到`dimnames()`，傳入一個list來當參數，第一個是row names，第二個是column names