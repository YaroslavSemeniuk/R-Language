## Відповіді до 3 лабораторної роботи

1. _Функція add2(x, y), яка повертає суму двох чисел._
```
add2 <- function(x, y){
x + y
}
```

2. _Функція above(x, n), яка приймає вектор та число n, та повертає всі елементі вектору, які більше n. По замовчуванню n = 10._
```
above <- function(x, n = 10){
x[x > n]
}
```

3. _Функція `my_ifelse(x, exp, n)`, яка приймає вектор x, порівнює всі його елементи за допомогою exp з n, та повертає елементи вектору, які відповідають умові expression. Наприклад, `my_ifelse(x, “>”, 0)` повертає всі елементи x, які більші 0. Exp може дорівнювати `“<”, “>”, “<=”, “>=”, “==”`. Якщо exp не співпадає ні з одним з цих виразів, повертається вектор x._
```
my_ifelse <- function(x, exp, n){
if(exp == "<") x[x < n]
else if(exp == ">") x[x > n]
else if(exp == "<=") x[x <= n]
else if(exp == ">=") x[x >= n]
else if(exp == "==") x[x == n]
else x
}
```

4. _Функція `columnmean(x, removeNA)`, яка розраховує середнє значення `(mean)` по кожному стовпцю матриці, або data frame. Логічний параметр `removeNA` вказує, чи видаляти NA значення. По замовчуванню він дорівнює **TRUE**._
```
columnmean <- function(x, removeNA = TRUE){
if(removeNA) colMeans(x, na.rm = TRUE)
else colMeans(x)
}
```

**Приклади:**
```
x <- rnorm(100)
n <- 20
exp <- ">"
y <- data.frame(a = rnorm(100), b = 1:100, cc = sample(letters, 100, replace = TRUE))
z <- c(1, 2, 3, NA, 4, NA, 5, NA)
```
```
add2(1, 2)
above(x, n)
my_ifelse(x, exp, 0)
columnmean(y)
```
