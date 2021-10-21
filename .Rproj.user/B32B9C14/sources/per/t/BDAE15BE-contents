library(rpart)
library(rpart.plot)
library(rattle)

iris.uci <- read.csv(url("http://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data"), header=FALSE)

colnames(iris.uci)<-c("sepal.length","sepal.width","petal.length","petal.width","species")

# a 35th amostra está incorreta
iris.uci[35,]

# Correção da 35th amostra
iris.uci[35,4] = 0.2

# a 38th amostra está incorreta
iris.uci[38,]

# Correção da 38th amostra
iris.uci[38,2:3] = c(3.6,1.4)

# eliminando a palavra Iris da coluna species
iris.uci$species <- mapvalues(iris.uci$species, from =
                                c("Iris-setosa", "Iris-versicolor", "Iris-virginica"),
                              to = c("setosa", "versicolor", "virginica"))

head(iris.uci)

iris.tree <- rpart(species ~ sepal.length + sepal.width + petal.length + petal.width, iris.uci, method="class")

iris.tree

prp(iris.tree, type=2, extra="auto", nn = TRUE, branch=1, varlen=0, yesno=2)

# rattle()