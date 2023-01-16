## Відповіді до 4 лабораторної роботи

0. _Для лабораторної роботи необхідно завантажити файл з даними за [посиланням](https://www.dropbox.com/s/8k1gjgk8cflmpb6/hw1_data.csv?dl=0)._
```
install.packages("readr")
library(readr)
data_url <- "https://www.dropbox.com/s/8k1gjgk8cflmpb6/hw1_data.csv?dl=0"
data <- read.csv(data_url)
```
1. Які назви стовпців файлу даних? - `colnames(data)`
2.  Виведіть перші 6 строк фрейму даних - `head(data, 6)`
3. Скільки спостерігань (строк) в дата фреймі? - `nrow(data)`
4. Виведіть останні 10 строк дата фрейму. - `tail(data, 10)`
5. Як багато значень «NA» в стовпці «Ozone»? - `sum(is.na(data$Ozone))`
6. Яке середнє (mean) стовпця «Ozone». Виключити «NA» значення. - `mean(data$Ozone, na.rm = TRUE)`
7. Виведіть частину набору даних (subset) зі значенням «Ozone» > 31 та «Temp» > 90. Яке середнє (mean) значень «Solar.R» в цьому наборі даних (subset)?
```
subset_data <- data[data$Ozone > 31 & data$Temp > 90,]
mean(subset_data$`Solar.R`)
```
8. Яке середнє значення (mean) для «Temp» для червня («Month» дорівнює 6)?  
`mean(data[data$Month == 6,"Temp"],na.rm = T)`
9. Яке максимальне значення «Ozone» для травня («Month» дорівнює 5)?  
`max(data[data$Month == 5,"Ozone"],na.rm = T)`
