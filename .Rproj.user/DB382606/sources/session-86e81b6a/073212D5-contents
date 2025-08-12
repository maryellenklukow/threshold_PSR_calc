library(tidyverse)

soilP_file <- "multi-proj_soil_nutrient_WY25-v1.0_20250812.csv"
soilP <- read.csv(soilP_file)
head(soilP)

soilP <- soilP %>%
  select(project_code,
         coord_y,
         coord_x,
         datetime,
         tp_mgkg:wex_po4_mgkg) %>%
  na.omit()

total_samples <- nrow(soilP)
#1884

#calculate PSR as ratio among M3 parameters
#plot WEX (y) against PSR (x)
#run regression
#find change point