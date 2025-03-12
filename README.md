prac 10 logistic regression
input <- mtcars[,c("am","cyl","hp","wt")]
print(head(input))
input <- mtcars[,c("am","cyl","hp","wt")]
am.data = glm(formula = am ~ cyl + hp + wt, data=input, family = binomial)
print(summary(am.data))

prac 7 classification algo
library(party)
print(head(readingSkills))
input.dat <- readingSkills[c(1:105),]
png(file = "C:/BI17/decision_tree.png")  # Save the file in your home directory
output.tree <- ctree(nativeSpeaker ~ age + shoeSize + score, data = input.dat)
plot(output.tree)
dev.off()

prac 9 linear regression
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y ~ x)
print(relation)
print(summary(relation))
a <- data.frame(x = 170)
result <- predict(relation, a)
print(result)
png("C:/BI17/pract9.png")
plot(y, x, col = "blue", main = "Height and Weight Regression",
     abline(lm(x ~ y)), cex = 1.3, pch = 16, xlab = "Weight in kg", ylab = "Height in cms")
dev.off()

prac 8 clustering algorithm
# Load the Iris dataset
newiris <- iris

# Remove the Species column
newiris$Species <- NULL

# Perform K-means clustering with 3 clusters
kc <- kmeans(newiris, 3)

# Print the cluster means
print(kc$centers)

# Print the clustering vector
print(kc$cluster)

# Print the within-cluster sum of squares by cluster
print(kc$withinss)

# Print the between-cluster sum of squares
print(kc$betweenss)

# Print the total sum of squares
print(kc$totss)

# Print the available components of the K-means result
print(names(kc))

# Print the table of Species vs. cluster
print(table(iris$Species, kc$cluster))

# Plot the clustered data
png(file="C:/B117/kmeans.png")
plot(newiris[,c("Sepal.Length", "Sepal.Width")], col=kc$cluster)
points(kc$centers[,c("Sepal.Length", "Sepal.Width")], col=1:3, pch=8, cex=2)
dev.off()
