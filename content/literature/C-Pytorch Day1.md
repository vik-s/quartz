---
status: #literature
---
Instructor: Ben Sherman from Weights and Biases

### What are AI ML and DL?

- Deep learning is a specific form of machine learning. Machine learning is a specific for of Artificial Intelligence.
- Machine learning:
	- dont define rule based conditional frameworks that AI should respond to
	- ML takes data and learns to respond to scenarios based on it
	- Goal is to imitate human behavior
- Systems that learn intelligently from data

> Within a generation, the problem of creating artificial intelligence will be substantially solved\- Marvin Minsky, 1967

> Overwhelming majority of what we call intelligence is developed bu the endo f the first year of life. Marvin minsky, 1977

- Don't program actions, but learn what the best program action is

- Other class of models: Tree based models
	- dont program symbolic rules, but learn the symbolic rules
	- what kind of symbols are you looking for? (green pixel?)
	- What is the threshold number of occurances to make decision (no of green pixes)
	- Decide if stop light or tree
- Other class: Linear Models
	- Harness the power of linear algebra, vectors, planes, projections, etc. xkcd.com/1838
- Deep learning: put simple pieces together to make something complex (deep)

### Why deep learning?
- DL obeys the LEGO principle
	- make complex things by combining simple pieces
	- make interoperable simple things and then build worlds
	- LEGO API:
		- Studs on top of brick
		- Holes on bottom
	- The lego analogy is so good that things being matched are called "shapes"
		- Matrix multiplication function
		- Activation function
	- Matrix + activation func = fully connected layer
	- fully connected layer + fully connected layer = multilayer perceptron
	- Lego principle in action = Inception V1 Szegedy et all 2014
		- Used initially for image classification
- DL scales well with data --> more data = more accurate.
	- this does not happen with tree-models, or older methods
		- cannot program infinitely many if statements
	- DL can learn from more data, and get better
	- Older models dont get better with more data
	- Imagine how well DL can train with internet data
		- powers openAI and text-to-image AI
	- We are only limited by amount of data available, and how we can fit into a computer
- Linear algebra is all you need for graphics, and GPUs are excellent accelerators. They are very valuable for DL acceleration too!
	- Python allows for accelerated DL
	- High performance and full flexibility can all be done in python
	- Have bindings to C++ using CUDA on nVidia GPUs
- Pytorch
	- came from Meta
	- Pytorch lightning is a nice framework for python
	- CuDNN is low level operations for array operations in DL
	- CUDA (c/c++) is low level operations
- Two major frameworks:
	- Tensorflow / Keras -- Google
	- Jax -- Google
	- Pytorch / Lightning -- Facebook
- Pytorch is more popular among researchers and is more DIY than Keras
	- used more and more these days
- Pytorch lightning tends to make it more like Keras
- Tensorflow has more mature tooling for edge cases really, but Pytorch is catching up

### ML as an API

- API tells us it does something without telling us how

- 3 methods / functions
	- Loss
		- inspect model predictions, and says how good the model is doing in predictions
		- measure of prediction quality
		- You have a predetermined cat dataset; how well does AI predict that.
	- Model.forward
		- A forward pass through the large computational graph that constitutes the learning system
	- Model.fit
		- takes examples in, makes model better
		- use a known dataset to train the model

- 3 types of API
	- Model -- the AI of the system
	- Inputs -- kind of data model takes in (images, 3d scans)
	- Targets -- kind of data you predict with Model, or Model output

- Training and deployment --  think of it as development and production

- First do model.fit to teach the DL system
- loss is like a testing/CI that tells you how well you are doing
- model.forward is to use it in production

- Inputs and targets are both kinds of data
	- inputs: data model sees and uses to make decisions
		- determined by what data you have
	- targets: data model is trying to produce, only seen during training
		- determined by the problem (cats or not cats)
	- Need both during training phase
	- But in production, you will not have targets, only inputs

- Example: feed grams vs chicken weight
	- Linear regression is enough. Still a type of ML!
	- Use loss to "score" the model. Lower is better.
	- Prediction comes from model.forward
	- compare that to the known correct value
	- Calculate loss (rms error is one kind)

- One hot vector -- vectorized representation of the correct answer.

```python
trained_model = Model.fit(training_inputs, known_outputs)
```

Using fit to make a model better
```python
untrained_model = Model()
untrained_outputs = untrained_model.forward(training_inputs)
untrained_loss = loss(untrained_outputs, training_targets)

trained_model = untrained_model.fit(training_inputs, training_targets)
```

When is a model good?
- Make sure that loss in production is better than a certain number.

### Perceptrons

Digit recognition problem is the helloworld of ML!
- Could you identify handwritten digits using Python?
- Rules based methods based on conditions will not work for something like this

Frank Rosenblatt invented the perceptron 1960 to solve such problems. How did his machine work?
- uses variable resistors whose value can be set by knobs, and a light that turns on
- Imagine you have a knob for each pixel in image of 5
- Set the knobs so that light turns on when the number is 5
- You just trained the perceptron

Mathematical model of a perceptron
- Multiply each input by a weight (like the knobs)
- Sum all the weighted inputs
- Pass the sum through an activation function (like the lightbulb)

First two steps is the dot product of the input vector and weight vector. You can add a constant to it if needed. This simple linalg solves super fast on GPU

In pytorch, this is called a `Linear` block.

- Break the input dataset into batches (like 32 out the 1000)
	- this is needed because datasets can be really really big
- Dataloaders do this, the behave like lists
- One pass through of entire dataset while adjusting weights in reponse to the inputs is called an ==epoch==
- 

Use `Trainer.fit` in pytorch lightning to do the fit.
- Iterates over Dataloader
- calls ==Optimizer== to set the weights
- minimizes loss

Sigmoid (S-shaped) functions work much better than linear activation functions

Recognizing structures and patterns in data is known as ==feature detection==. Example, the strokes involved in creating the number 5. horizontal line on top, vertical line on left, and backwards C shape.

So train a model for each of the three features. A fully connected layer (perceptron + act func) to detect horizontal line, vertical line and backwards C. Connect all the 3 fully connected layers, to create a multilayer perceptron to detect a 5. In Pytorch this is done using `Sequential`

But how do we modify this to increase dimensionality of the outputs? Dont just identify the digit (5 or not) but tell me the digit it is. This is where we need probablity calculation. This is done using `softmax` function. Take the multidimensional output and run it through softmax.

Softmax gives you an array of probabilities. But we want an array of zeros and ones. to finally identify the digit. RMS error is a bad way to compare this and has high error. People mostly use the ==cross entropy== function.

https://ml-cheatsheet.readthedocs.io

How does the .fit work?

- All neural network fitting schemes uses local optimization. Descend the surface of the loss function. Uses calculus to descend the loss function surface. Compute gradient of loss function wrt any given point on the surface. Then follow that till gradient is zero. Gradient descent algorithm. 
- Downside to local optimization can always give false minima

- Gradient descent algorithm possibly with "Momentum" is usually the first choice for optimizers. Sometimes ADAM or RMSProp works better.
- Recommendation: better to try different optimizers, than mess with config of optimizer you are using.
- Look into Backpropagation algorithm too, its really beautiful mathematically. OpenAI blog post has a great article. This blog is also very good for ML. Also mentioned 3blue1brown videos -> Look at his deep learning videos.
- Batchnorm -- normalize the inputs to be within some some range of numbers, so that activation functions dont become unresponsive

2 minute courses -- research topics
fastAI - courses on YT and notebooks
full stack deep learning course YT
weights and biases YT






