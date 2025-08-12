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

#discussion for group: do we want to exclude sites outside of the Erie basin?

#calculate PSR as ratio among M3 parameters
soilP <- soilP %>%
  mutate(PSR = (m3_p_mgkg / 31)/ ((m3_fe_mgkg / 56)+(m3_al_mgkg / 27)))

#plot WEX (y) against PSR (x)
p <- ggplot(soilP, aes(PSR, wex_po4_mgkg)) +
  geom_point()
p
#run regression
#find change point