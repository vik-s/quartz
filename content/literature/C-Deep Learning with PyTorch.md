---
Status: #literature/course 
Tags: #ai/deeplearning #inbox/to-process 
Title: Introduction to PyTorch
Instructor: Ben Sherman
Affiliation: Weights and Biases
URL:
Year: 2022
---

*This course was offered to Qualcomm employees as Engineering Development*

### Terminology

[[Artificial Intelligence]] : This is a field of study where machines mimic the intelligence of humans by learning and performing tasks based on the experience or data they are provided.

[[Machine Learning]]: This is a subset of Artificial Intelligence, where the emphasis is on computers learning from data that is provided to them, so that they can perform intelligent tasks such as classifications and predictions.

[[Deep Learning]]: This is a subset of machine learning where computers learn to perform specific tasks, but can perform much more complex (deep) tasks based on the rudimentary building blocks of learning.

Other machine learning approaches involve decision tree based models, and even linear models such as curve fits and regressions still count as [[AI/ML]].

### Principles of Deep Learning

Deep learning draws a very good analogue with Lego blocks. The idea to use pieces to make simple things and then use those simple things to create something more complex. The hierarchy of components one could hypothetically build can be quite "deep", and this is where the name comes from. 

When building a learning model from simpler learning models, the "pieces" have to "fit" together much like lego blocks do. A simple piece of a learning model can be built with two fundamental operations:
1. Matrix multiplication
2. Activation function

This simple piece constructed from the basic operations above is called a ==fully connected layer==.

To push the lego analogy further, you can connect several fully-connected layers to build what is called a ==multi-level perceptron-==.

One of the highly cited papers that shows this Lego action in practice is Szegedy et al 2014 (insert Zotero link). They describe the design of the Inception multilevel perceptron used to classify images.

One of the other important advantages of Deep Learning is that the learning model only gets better with more and more training data.  This is in contrast to other models like Tree-Based models that stop getting better after a certain amount of data. Also, for decision tree based ML, one cannot sufficiently cover all possible scenarios with "if" conditions. The model simply does not get better anymore. xkcd.com/1838



---
# References