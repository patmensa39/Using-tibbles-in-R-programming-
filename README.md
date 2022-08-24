# Using-tibbles-in-R-programming-
### Using tibbles 
### make sure to install all the packages below. 
pacman::p_load(datasets, pacman, psych, rio, tidyverse)

### the orange dataset 
?Orange
view(Orange)
glimpse(Orange)
class(Orange)

### converting the orange to a tibble

data <- Orange %>% as_tibble() %>% print()
view(data)
class(data)
glimpse(data)

### converting tree to factors and reorder the levels 

data <- data %>% 
  mutate(Tree = factor(Tree, 
                       levels = 1:5)) %>%
  print()

### Graphing circumference as a function of age for each tree 
data %>% ggplot(mapping = aes(age, circumference, fill = Tree)) + 
  geom_point() + geom_smooth(method = "lm") + 
  ggtitle("Predicting Circumference with age by tree")


