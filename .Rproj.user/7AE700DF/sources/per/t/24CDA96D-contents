install.packages("dplyr")
install.packages("plotly")
install.packages("ggplot2")
install.packages("lubridate")
install.packages("tidyr")
library(dplyr)
library(plotly)
library(ggplot2)
library(lubridate)
library(tidyr)

POAR2018 <- read.csv("iDAV CW Datasets/POAR_2018.csv", skip = 4)
POAR2019 <- read.csv("iDAV CW Datasets/POAR_2019.csv", skip = 4)
POAR2020 <- read.csv("iDAV CW Datasets/POAR_2020.csv", skip = 4)
POAR2021 <- read.csv("iDAV CW Datasets/POAR_2021.csv", skip = 4)
POAR2022 <- read.csv("iDAV CW Datasets/POAR_2022.csv", skip = 4)
POAR2023 <- read.csv("iDAV CW Datasets/POAR_2023.csv", skip = 4)


# Combine all data
POARTOTAL <- bind_rows(POAR2018, POAR2019, POAR2020, POAR2021, POAR2022, POAR2023)

#rename PM10 cause length of column name is too long
POARTOTAL <- POARTOTAL %>%
  rename(PM10 = PM.sub.10..sub..particulate.matter..Hourly.measured.)

# Filter specific dates
december_2018 <- filter(POARTOTAL, grepl("20-12-2018", Date) & !is.na(PM10) & PM10 != "")
january_2019 <- filter(POARTOTAL, grepl("03-01-2019", Date) & !is.na(PM10) & PM10 != "")
march_19th_2020 <- filter(POARTOTAL, grepl("19-03-2020", Date) & !is.na(PM10) & PM10 != "")
march_26th_2020 <- filter(POARTOTAL, grepl("26-03-2020", Date) & !is.na(PM10) & PM10 != "")
june_2020 <- filter(POARTOTAL, grepl("29-06-2020", Date) & !is.na(PM10) & PM10 != "")
november_2020 <- filter(POARTOTAL, grepl("10-11-2020", Date) & !is.na(PM10) & PM10 != "")
december_2020 <- filter(POARTOTAL, grepl("20-12-2020", Date) & !is.na(PM10) & PM10 != "")
january_2021 <- filter(POARTOTAL, grepl("03-01-2021", Date) & !is.na(PM10) & PM10 != "")
november_2021 <- filter(POARTOTAL, grepl("29-11-2021", Date) & !is.na(PM10) & PM10 != "")
july_2022 <- filter(POARTOTAL, grepl("25-07-2022", Date) & !is.na(PM10) & PM10 != "")
july_2023 <- filter(POARTOTAL, grepl("24-07-2023", Date) & !is.na(PM10) & PM10 != "")

TOTAL_DATE <- bind_rows(december_2018, 
                        january_2019, 
                        march_19th_2020, 
                        march_26th_2020, 
                        june_2020, 
                        november_2020,
                        december_2020,
                        january_2021,
                        november_2021,
                        july_2022,
                        july_2023)

# visualisation
fig1 <- plot_ly(TOTAL_DATE, 
                x = ~time, 
                y = ~PM10,
                color = ~Date,
                type = 'scatter', 
                mode = 'lines+markers') %>%
  layout(title = "PM10 Levels by Date",
         xaxis = list(title = "Time"),
         yaxis = list(title = "PM10 Concentration"))

fig1