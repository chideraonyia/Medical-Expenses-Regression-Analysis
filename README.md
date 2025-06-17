# Medical-Expenses-Regression-Analysis
A model that forecasts medical expenses using linear regression with k-means

# Data exploration & Preparing the data
* insurance <- read.csv("insurance.csv", stringsAsFactors = TRUE)
* str(insurance)
* summary(insurance$expenses)
* hist(insurance$expenses)
* table(insurance$region)
   
--(Exploring Relationships among features i.e The correlation matrix)
* cor(insurance[c("age", "bmi", "children", "expenses")])
  
--(Visualizing Relationships Among Features)
* pairs(insurance[c("age", "bmi", "children", "expenses")])
* install.packages("pysch")
* library(psych)
* pairs.panels(insurance[c("age", "bmi", "children", "expenses")])

# Training A Model on the Data
* ins_model <- lm(expenses ~ age + children + bmi + sex + smoker + region,
                data = insurance)
* ins_model <- lm(expenses ~ ., data = insurance)
* ins_model

# Evaluating Model Performance 
* summary(ins_model)

# Improving Model Performance 
--(Model Specification - Adding Non-Linear Relationships)
* insurance$age2 <- insurance$age^2

--(Transformation - Converting a Numeric Variable to a Binary Indicator)
* insurance$bmi30 <- ifelse(insurance$bmi >= 30, 1, 0)








