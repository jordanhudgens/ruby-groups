# Practical Machine Learning with Ruby

## What is Machine Learning?

[TechTarget Definition](http://whatis.techtarget.com/definition/machine-learning)

> "Machine learning is a type of artificial intelligence (AI) that provides computers with the ability to learn without being explicitly programmed. Machine learning focuses on the development of computer programs that can teach themselves to grow and change when exposed to new data."

Dead simple definition:

> The data determines the output


## Practical Applications of Machine Learning

- Analyzing when a vehicle may need to be removed from a fleet based on historical trends.
- Checking to see if an email is spam.
- Verifying bank transactions.
- Verifying medical diagnosis.
- Product recommendations
- Google search engine
- Etc, etc, etc


## Why Ruby Isn't Typically Used for Machine Learning

- Misconceived notions about speed
- Lack of libraries
- Ease of passing responsibilities to other services


## Popular Algorithms

- [Decision Tree](https://github.com/igrigorik/decisiontree)
- [Naive Bayes](https://github.com/oasic/nbayes)
- K Means Clustering Algorithm
- Support Vector Machine Algorithm
- Apriori Algorithm
- Linear Regression
- Logistic Regression
- Artificial Neural Networks
- Random Forests
- Nearest Neighbours


### Supervised vs Unsupervised Learning

- **Supervised** - Teaching a child that an electrical outlet is dangerous, and the child learns not to touch other electrical hazards.
- **Unsupervised** - A child learns what's dangerous by trial and error, eventually learning not to touch electrical hazards.


## Ruby Machine Learning Example

### Continuous vs Discrete

- **Continuous** - Items that can be measured, e.g. height, weight, product reviews.
- **Discrete** - Items that have a set number of options: gender, dice roll.


## Basic Decision Tree

```ruby
require 'decisiontree'

attributes = ['Temp']

training = [
  [98.7, 'healthy'],
  [99.1, 'healthy'],
  [99.5, 'sick'],
  [100.5, 'sick'],
  [102.5, 'crazy sick'],
  [107.5, 'dead'],
]

dec_tree = DecisionTree::ID3Tree.new(attributes, training, 'sick', :continuous)
dec_tree.train

test = [98.5, 'healthy']

dec_tree.predict(test)
```


## More Advanced Decision Tree

```ruby
require 'decisiontree'

attributes = ['Age', 'Education', 'Income', 'Marital Status']
training = [
  ['36-55', 'Masters', 'High', 'Single', 1],
  ['18-35', 'High School', 'Low', 'Single', 0],
  ['36-55', 'Masters', 'High', 'Single', 1],
  ['18-35', 'PhD', 'Low', 'Married', 1],
  ['< 18', 'High School', 'Low', 'Single', 1],
  ['55+', 'High School', 'High', 'Married', 0],
  ['55+', 'High School', 'High', 'Married', 1],
  ['55+', 'High School', 'High', 'Married', 1],
  ['55+', 'High School', 'High', 'Married', 1],
  ['< 18', 'Masters', 'Low', 'Single', 0],
]

dec_tree = DecisionTree::ID3Tree.new(attributes, training, 1, :discrete)
dec_tree.train

test = ['18-35', 'PhD', 'High', 'Married']

dec_tree.predict(test)
```


## Resources

- [Decision Tree Gem](https://github.com/igrigorik/decisiontree)
- [Naive Bayes](https://github.com/oasic/nbayes)
- [Machine Learning Algorithm Overview](https://www.dezyre.com/article/top-10-machine-learning-algorithms/202)
