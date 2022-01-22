# Artificial-Intelligence
For this project we have used genetic algorithm. A general flow of genetic algorithm has already been given. Following are the steps that have been used to solve the problem statement

Since we are supposed to optimise the parameters of the given CNN network, a general CNN network is made considering the constraints mentioned.
First the parameters are initialized with a range of available choices.
The Roulette fitness function is written by taking the weight(importance) of each species and selecting two parents with max fitness value.
Crossover has been done in different way. Instead of flipping parameter value one child with one parent, we are randomly deciding which the parent to be flipped.
Mutation/flipping has been achieved by changing the gene of children by changing the epoch(adding some integer to existing epoch number). This differentiates the two consecutive children.
Process--->

Instead of using the code snippet for downloading dataset, we have downloaded from keras and did standard train(60000) and test(10000) split.
The classification accuracy is calculated on test set.
The whole process take place in 3 generation having 4 step each. The initialised parameters are passed to CNN network and classification accuracy is calculated which is followed finding parents ->crossover ->mutation.
This whole process repeats for three generations. Moreover in each generation, we have removed 2 species having lowest fitness value. This is dome to ensure only fittest species is selected as parents.
The convergence criteria is selected when the accuracy is greater than 95% or when 3 generations are done. While running the code we found that 3 generations are sufficient for getting 75-85%.

#Accuracy and Parameters trade off

For minimising parameters we have restricted our search space of filter size in the range of (16,32,64). We have not taken other higher filters as it will increase model complexity and thus parameters.Also we have checked the condition, number of parameters less than 60000(below 60000 searching time exceeds 2.5 hrs). Since our search algorithm should not stop at 75% so we took the cutoff of 95%. Randomness and change in crossover improved accuracy on test set and reducing search space and setting threshold minimised parameters.
