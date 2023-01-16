## Відповіді до 5 лабораторної роботи
0. _Для лабораторної роботи необхідно завантажити zip файл з даними за [посиланням](https://www.dropbox.com/s/i9wi47oyhfb7qlh/rprog_data_specdata.zip?dl=0)_
```
url <- "https://www.dropbox.com/s/i9wi47oyhfb7qlh/rprog_data_specdata.zip?dl=0"
download.file(url, destfile = "specdata.zip", mode = "wb")
unzip("specdata.zip")
path <- "specdata"
```

1. Написати функцію pmean, яка обчислює середнє значення `(mean)` забруднення сульфатами або нітратами серед заданого переліка моніторів.
```
pmean <- function(directory, pollutant, id = 1:332) {
files <- list.files(path = directory, full.names = TRUE)
data <- data.frame()
for (i in id) {
  file <- paste(directory, "/", formatC(i, width = 3, flag = "0"), ".csv", sep = "")
  if (file %in% files) {
      df <- read.csv(file)
      data <- rbind(data, df)
    }
}
mean(data[complete.cases(data[pollutant]), pollutant], na.rm = TRUE)
}
```

2.  _Написати функцію complete, яка виводить кількість повних спостережень (the number of completely observed cases) для кожного файлу_
```
complete <- function(directory, id) {
  files <- sprintf("%03d.csv", id)
  nobs <- lapply(files, function(x) {
    data <- read.csv(file.path(directory, x), header = TRUE, sep = ",")
    sum(complete.cases(data))
  })
  data.frame(id = id, nobs = unlist(nobs))
}
complete("directory/to/data", c(1,2,3))
```

3. _Написати функцію corr, яка приймає два аргументи: directory (папка, де знаходяться файли спостережень) та threshold (порогове значення, за замовчуванням дорівнює 0) та обчислює кореляцію між сульфатами та нітратами для моніторів, кількість повних спостережень для яких більше порогового значення._
```
corr <- function(directory, threshold = 0) {
  # list all csv files in the directory
  files <- list.files(path = directory, pattern = "*.csv", full.names = TRUE)

  # create an empty vector to store correlation values
  cor_vec <- c()

  # loop through each file and calculate the correlation
  for (file in files) {
    data <- read.csv(file)
    nobs <- complete.cases(data$sulfate, data$nitrate)
    if (nobs > threshold) {
      cor_val <- cor(data$sulfate, data$nitrate, use = "complete.obs")
      cor_vec <- c(cor_vec, cor_val)
    }
  }
  return(cor_vec)
}
```
