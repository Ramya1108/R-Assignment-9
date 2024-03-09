CODE:

knitr::opts_chunk$set(echo = TRUE)

data(iris)

plot(iris$Sepal.Length, iris$Sepal.Width,

     xlab = "Sepal Length",

     ylab = "Sepal Width",

     main = "Scatter Plot of Sepal Length vs. Sepal Width")

library(lattice)

xyplot(Sepal.Width ~ Sepal.Length, data = iris,

       groups = Species,

       type = c("p", "g"),

       auto.key = list(columns = 3),

       xlab = "Sepal Length",

       ylab = "Sepal Width",

       main = "Scatter Plot of Sepal Length vs. Sepal Width by Species")

library(ggplot2)

ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) +

  geom_point() +

  labs(x = "Sepal Length", y = "Sepal Width",

       title = "Scatter Plot of Sepal Length vs. Sepal Width by Species")



EXPLANATION:

1.knitr::opts_chunk$set(echo = TRUE): This line sets an option in the knitr package to include the code when the document is rendered. It's useful for producing reports or documents with embedded R code and its output.

2.data(iris): Loads the iris dataset. It's a built-in dataset in R containing measurements for 150 iris flowers from three species: setosa, versicolor, and virginica.

3.plot(iris$Sepal.Length, iris$Sepal.Width, ...): This line creates a basic scatter plot using base R graphics. It plots Sepal Length on the x-axis and Sepal Width on the y-axis using the iris dataset.

4.library(lattice): Loads the lattice package, which provides an alternative system for creating plots in R.

5.xyplot(...): This function creates a scatter plot using lattice graphics. It plots Sepal Width against Sepal Length, grouping the points by species. It also adds a key to identify the species.

6.library(ggplot2): Loads the ggplot2 package, which is a powerful package for creating graphics in R.

7.ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) + ...: This line initiates a ggplot object. It specifies the data (iris) and the aesthetics (aes) mapping Sepal Length to the x-axis, Sepal Width to the y-axis, and Species to the color. It then adds a layer of points using geom_point(), and sets labels for the axes and the title of the plot using labs() function.
