## Відповіді до 1 лабораторної роботи

1. _Створити змінні базових (atomic) типів. Базові типи: character, numeric, integer, complex, logical._
   ```
   char_variable <- "Hello"
   num_variable <- 3.14
   int_variable <- 42
   complex_variable <- 2+3i
   logic_variable <- TRUE
   ```


2. _Створити вектори, які: містить послідовність з 5 до 75; містить числа 3.14,  2.71, 0, 13; 100 значень TRUE._
   ```
   seq_vector <- 5:75
   num_vector <- c(3.14, 2.71, 0, 13)
   logic_vector <- rep(TRUE, 100)
   ```

3. _Створити наступну матрицю за допомогою **matrix**, та за допомогою **cbind**_
   ```
   matrix_1 <- matrix(c(0.5, 1.3, 3.5, 3.9, 131, 2.8, 0, 2.2, 4.6, 2, 7, 5.1), nrow = 3, ncol = 4, byrow = TRUE)
   matrix_2 <- cbind(c(0.5, 1.3, 3.5), c(3.9, 131, 2.8), c(0, 2.2, 4.6), c(2, 7, 5.1))
   ```

4. _Створити довільний список (list), в який включити всі базові типи._
   ```
   basic_types_list <- list(char_variable, num_variable, int_variable, complex_variable, logic_variable)
   ```
   
5. _Створити фактор з трьома рівнями «baby», «child», «adult»._
   ```
   age_factor <- factor(c("baby", "child", "adult", "child", "adult"), levels = c("baby", "child", "adult"))
   ```

6. _Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA,  11. Знайти кількість значень NA._
   ```
   vec <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
   first_NA_index <- which(is.na(vec))[1]
   NA_count <- sum(is.na(vec))
   ```

7. _Створити довільний data frame та вивести в консоль._
   ```
   df <- data.frame(name = c("Alice", "Bob", "Charlie"), age = c(25, 30, 35), gender = c("female", "male", "male"))
   print(df)
   ```

8. _Змінити імена стовпців цього data frame._
   ```
   colnames(df) <- c("Full Name", "Age", "Sex")
   ```
