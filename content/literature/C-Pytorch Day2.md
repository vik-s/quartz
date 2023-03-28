---
status: #literature
---

### Review
- A fully connected network does "non-deep" learning. It is only by connecting them to create multilayer perceptrons, or deep neural networks, that are capable of "deep" learning.

### Convolution Neural Networks (CNN)

- Instead of using Linear layers, they use ==Conv2D== layers. Linear layers tend to flatten the image being process and weight them. Conv2D layer looks at in as a 2D plane.
- The process takes an array of pixels, and outputs a single number.. So by scanning conv2D layers, you construct a new 2D map. This process is called builing a "Feature Map".
- AlexNet is a famous neural net that improved computer vision that came out in 2013.

*you need to construct these notes with images from the originial slide set*

- This convolution process is trying to identify some "feature" in the picture.
- You usually train a bunch of convolutions for the different features you want to extract. Each of them will generate a new array of information. Each feature you are looking for requires a different "kernel" used for convolution. For say 10 features, will give you 10 "channels" that tells you about the "feature" you were looking for in that image. This blows up the problem size!
- How to get around this?  Use a Max pooling layer.
	- you take a grid of numbers and just choose the max value in the grid. this down samples the image. Higher number means that its a greater presence of the feature you are looking for. So it makes intuitive sense that that it is enough to take max values.

- checking out the "Deep Dream" paper from Google. Check out the OpenAI papers too

### My Idea

- Run a simulation for a given 