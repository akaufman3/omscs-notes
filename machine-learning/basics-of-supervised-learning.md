# Supervised Learning

## Basics of Supervised Learning

- Relies on human input to train a model
- Supervised learning essentially works to create function approximation were it is given a number of pre defined input out put sets from a human that it uses to create a model that can predict or correctly label an never before-seen input with decent accuracy within an acceptable range
- Parts of supervised learning: techniques, classification, regression, computational learning theory, Bayesian learning
- There are two groups of algorithms used in supervised learning. Classification maps complex inputs to labels such as Tue or false or girl. Regression maps these inputs to often-numeric value that is continuous meaning can be mapped to fractions or decimals. Classification ends up dealing more with discrete values.
- Errors can come from a variety of places including hardware, human element, malicious intent, unmodeled influences
- You need to make sure known errors are present in the training data so that they ave factored in the model
- However if too many errors in the training data then your model won’t reflect the real world accurately
- There are various methods for reducing overfitting but one to combat errors in data is called cross-validation. Cross-validation takes some of the training data and creates a "fake" testing set. The goal here is to try to get the errors across both training data and cross- validation data are similar. 
- The first step of breaking down a classification problem is making sure you have all the elements required. You need a good collection of instances that correctly represent the input data by which to train the overall model. You then need a classification abstraction which is a fundamental concept supporting the existence of a database system. This is more of a general idea or principle used to categorize things were the de thing characteristics are not based on concrete, tangible features but rather on Moro conceptual or tangible qualities. This concept can hopefully be represented by a well formed function. A target concept will also be needed which is the "answer" which allows us to classify based on our concept.We then have our hypotheses which are all the possible functions used to describe the concept. We will also need some input samples that ave paired with connect outputs so that we can gauge the accuracy of our outputs. We then want to identify a candidate which is a potential target concept. Lastly, we pull a testing set from our instances that the candidate concept has not yet seen in order to evaluate how close it is to the ideal target concept.
- Decision trees are a representation of our features. An algorithm is used that the tree can apply to make a decision. Decision trees are a form of classification learning. Decision trees short start with questions that narrow down to decision making right away.
- Defining questions can be approached from a mathematical perspective. We can say that a "good" starting question divides the data into half. This is a concept normally used in binary search.
- A key issue with defining an algorithm however is that we want the algorithm to learn the tree not just use the tree to make decision.

## Classification
### ID3 Algorithm
- ID3 algorithm greedily approaches the feature ranking process with a top-down approach
- ID3 is an algorithm that iteratively and repeatedly divides features into 2 or more groups at each step of the tree
- It uses information gain to select the best feature.
- Information gain calculates the reduction in entropy and measures how well a given feature separates or classifies the target class. 
- Steps:
1) define A as the best attribute. An attribute is essentially a column in your data set that describe the properties of your instance. For example deciding whether someone will play tennis based on weather conditions the attributes may include outlook (sunny), temperature, humidity, wind.
2) attribute A then becomes the "question" we are asking for the note feature n we are working with. We then create a decision node in the tree for this attribute and to start it would be the root node.
3) for each value V create a branch from the node. Continue building as such for each data subset until all instances in the subset belong to the same class or there are no more attributes to split on. Continue to measure how much each a tribute can reduce the overall entropy. We are looking to work an information theory which is a measure of an much information an attribute gives us about a system

## Inductive Bias
- As we develop a classifier based onthe hypothesis we are testing, we need to be mindful of two forms of bias: restriction and preference bias
- It we label a identify her hypothesis set as H, we can define restriction biasas only considering functions that can be represented with a decision tree. A restriction bias ensures a decision tree is interpretable and does not grow excessively complex and it limits the hypothesis space. This however can lead to underrating in some cases which can cause the decision tree to fail to capture complex relationships in the data. What's more, the true model lies outside the restricted hypothesis space then the algorithm can't discover it.
- Preference bias tells us what type of hypothesis from our set we might prefer. This encapsulates the predefined assumptions or limitations about the hypothesis space (the set of all possible models) that guide the algorithm in constructing the decision tree. However this bias is needed to ensure that the decision tree is interpretable and does not grow excessively complex. This is at the heart of inductive bias.
- ID3 prefers: splits, correctness and depth (ID3 prefers shallower trees)
- Asking continuous questions can be problematic and infeasible as we cannot branch on every possible value of an attribute.
- It is acceptable to have repeating attributes or ask the same question later in the tree.
- The ID3 algorithm stops creating the decision tree when all of the training examples are classified correctly.it is impossible to classify every example correctly and you might get stuck in an infinite loop.
- You can implement generalization via pruning which can fix overfitting and make the tree smaller and more traverseable. However, you have to makes sure that the generalized tree does not increase our training error by too much
- Decision trees don't transfer directly to regression problems where the goal is to predict a continuous numerical value because they do not use information gain as their splitting criterion because the information gain is based an entropy which is a concept designed for categorical data net continuous data.

## Ensemble Learning
- An ensemble is a machine learning technique that combines the predictions of multiple models to improve performance, accuracy and robustness of a predictive system
- You combine learners into groups who will individually contribute to the hypothesis and collaborate an answer.
- The general approach to this of learning algorithm starts with using smaller subsets of training data by which the algorithms individually develop rules then combine all rules into a collective smarter decision-maker
- This learning approach has two major questions: how to pick subsets and how to combine learners. We turn to bagging and boosting to help answer these questions.
- Bagging, or bootstrap aggregation, chooses data uniformly randomly to form the subsets with replacement or combining the results with an average also works.
- Why is this approach good? If our biggest concern is overfitting the data set, then relying on the average of a set of weak learners is better than a single learner because overfitting a subset will not overbite overall dataset will " smooth out" the specifics of each individual learner