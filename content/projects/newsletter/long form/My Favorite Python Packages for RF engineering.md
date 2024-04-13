---
title: My Favorite Python Packages for RF engineering
tags:
  - coding
project: substack
date_published: 
status: 🚧
final title:
---
Learning to code has paid itself back 100x for the time I have spent learning it.

It has helped me automate hours of my routine work. Instead, I focus on learning and new ideas. It is also what helps me write this newsletter with a 9-5 job.

I strongly recommend that every RF engineer learns to code well. 
### Which language is best?

It doesn't matter. I personally find Python quite convenient. If you have access to a Matlab license, then use that. Otherwise, Octave is an alternative that is largely compatible with Matlab syntax. R is another popular package for data analysis, especially if your work involves a lot of statistics. If you're up for a challenge, I'd recommend learning Julia because it is blazing fast for engineering work. 

For the ultimate bragging rights, go learn Fortran. Yes, Fortran. Laugh all you want, but as it turns out it is the most computationally efficient language for engineering work. It is used to benchmark supercomputers and is used for a lot of numerical tools that involve applied math, finance and computational fluid dynamics. From the Fortran website:

> If you’re writing a program or a library to perform fast arithmetic computation over large numeric arrays, Fortran is the optimal tool for the job.

Today we will stick to Python. Only because I think it is easy to get going quickly, sufficient for most RF work, and there is lots of infrastructure that you can readily use to get your work done.
### Python Environment

If you're wondering where to start, just install the Anaconda distribution of Python. It contains most of the packages you'll ever need, especially if you install the complete version (not the basic miniconda version.) It is cross platform and supported on Windows, Linux and Mac. If you are unfamiliar with python syntax, there are plenty of tutorials on YouTube and online learning courses to get you coding quickly.

With the Anaconda package, you get an integrated development environment (IDE) called Spyder that is quite easy to use. I personally use VScode as IDE, but I've found PyCharm to be quite convenient on many occasions too. It's a matter of personal preference. If you are using it for commercial work, be sure you understand the licensing requirements.

If you are doing scripting for data analysis, I recommend using Jupyter notebooks. They run in your browser and allows you to create code blocks. A program does not have to be its own block or even run sequentially. You can put one command per block, or several logical groups depending on your preference. It supports a mixture of code and text annotation using markdown syntax. This makes it very useful to create reports along with text explanations and code blocks to process results. 

### Virtual Environments
Another concept you should understand when just starting out, is the use of virtual environments. They are isolated sandboxes where you keep compatible versions of the packages you use. They will not change if you update your main Anaconda installation. They are especially useful if you need your code to work in other computer environments. A colleague can replicate your virtual environment and have all your code run on their computer.

### Version Control with Git
Finally, I'd recommend you learn how Git works. Git is a distributed version control system that you can use to control code revisions. This is helpful if you ever need to revert to a previous version of the code, or have multiple people working on a codebase. You can install Git locally and use it to version control your code. If you want to do it on a company-wide basis, you might have to talk to IT.

Git is common among software engineers, but I see few RF engineers use it effectively. If you want to learn how to get started, read this. Ohmygit gamifies the git learning process.

Let's dive into some useful applications of python in RF engineering work.
### Scikit-RF

This is the absolute workhorse python package to do RF engineering work. As an RF engineer, your immediate needs are usually to parse a Touchstone s-parameter file and plot the results in a Smith Chart. Scikit-RF does this in three lines of code:
```python
import skrf as rf
ntwk = rf.Network('ring slot.s2p')
ntwk.plot_s_smith()
```

Apart from simply plotting, reading and writing Touchstone data, it is also capable of the following:
- Microwave Network Operations: Cascading and deembedding networks, frequency slicing, conversion to Y/Z/H/ABCD parameters, sets of networks.
- Calibration: SOLT, TRL (including multiline), 8/16 term error models.
- De-embedding: Open short, Thru only and IEEE P370 standard deembedding.
- Media: Models for simulating transmission lines and various lumped element networks.
- Vector fitting: Fit a set of rational model functions to an s-parameter response.

The documentation for scikit-rf has many examples you can start from, and build your own analyses. The developers are quite responsive and helpful if you contact them with your questions via google groups. When you're comfortable with this package, consider contributing your own expertise to the project.
### numpy, Xarray, Pandas

Numpy is the basic package for numerical work in python. You will most likely use it to manipulate S-parameter data matrices. If you want to step up your multi-dimensional array game in python, then see Xarray. It makes the handling of complex matrix data much more manageable and intuitive by allowing labels for dimensions. Compared to raw numpy arrays, xarray enables sophisticated tools for handling arrays while integrating nicely with both numpy and pandas.

Pandas is a powerful data manipulation tool that allows you to ingest data into *dataframes* and perform calculations on them. I like to think of a dataframe as a spreadsheet on steroids. It also makes the import and export of comma separated value (CSV) files and a wide variety of other file formats, a breeze.

Like it or not CSV is widely utilized in engineering work, and often simulation and measurement tools produce a lot of them. Here is one of my favorite ways to build a giant dataframe from many CSV files, using glob. 

```python
import glob
import pandas as pd

# read in all csv filenames
filenames = glob.glob('./data/*.csv')

df_list = [] # empty list of dataframes

# fill the dataframe list with dataframes from each csv
for fname in filenames:
	df = pd.read_csv(fname, index_col=0, header=0)
	li.append(df)

# join all the dataframes to make one big one
big_df = pd.concat(li, axis=0, ignore_index=True)

# now you have all your CSV data in one dataframe!
```

The nice thing about numpy and pandas is that virtually every plotting tool in the python universe accepts these data formats as inputs. This nicely leads into the topic of plotting.
### Plotting
While pandas itself supports plotting of dataframes natively, you might often need more control over the types of plots and details you want to control. There are so many python plotting tools that it is hard to cover them all. We will restrict ourselves to the following frameworks which should be sufficient for RF engineering work.
- **Matplotlib**
	- Matplotlib was developed by John D. Hunter to emulate the easy plotting methods in Matlab at the time, but has evolved to become the de-facto standard in creating python plots. Today matplotlib has many third party extensions (https://matplotlib.org/mpl-third-party/) that you can use to extend its functionality to many different applications. 
	- If you want to produce beautiful plots for science and engineering papers, take a look SciencePlots https://github.com/garrettj403/SciencePlots. Specifically it has the IEEE style that sets the figure width to one width column of an IEEE paper, and sets the resolution to 600 DPI. It also ensures that the figures will be readable in black and white.
- **Seaborn**
	- Seaborn is python visualization library built on top of Matplotlib with special emphasis on statistical plots. It is particularly useful when visualizing large datasets that are otherwise cumbersome to handle with Matplotlib alone. Check out the gallery of plots here for ideas on how you can represent your data better. https://seaborn.pydata.org/examples/index.html 
- **Plotly**
	- Plotly is another highly featured plotting package for python (and many other programming lanuguages.) It is also one of the few plotting packages that offers smith charts out of the box using the Scattersmith graph object https://plotly.com/python/smith-charts/. While scikit-rf supports smith chart plots using matplotlib, doing it with plotly gives a more interactive plot. If you want to build a interactive data dashboard using Plotly's Dash, then using Scattersmith is the right way to go.
### Measurement
Automating lab measurements gives the best return on time invested. Measurements can run overnight and on weekends, and give you repeatable data. Instruments communicate over an interface like LAN, USB or GPIB (General Purpose Interface Bus) to send/receive commands from a computer. 

Most instruments support the IEEE 488.2 standard which specifies a communication protocol between a computer and instrument. The standard sets rules for the structure and formatting of messages so that instruments know how to interpret commands and respond to them.

As a higher layer of abstraction, Standard Commands for Programmable Instruments (SCPI, pronounced "skippy") uses the IEEE 488.2 syntax and protocols to define a set of commands that are easily readable for controlling the measurement and instrument state.

Now SCPI commands can differ based on the actual hardware interface used. Virtual Instrument Software Architecture (VISA) standardizes the software interface regardless of the hardware interface used. It provides a unified programming interface that allows software to communicate with instruments via different types of hardware interfaces like GPIB, Serial, Ethernet, and USB.

If you want to understand the differences better, check out this article. http://www.hit.bme.hu/~papay/edu/Lab/SCPIandVISA.pdf

Programming instruments is easy with python packages that handle most of the low level communication for you, and provides you with direct access to the VISA software interface. With these, you can focus on defining your measurement sequences.

- **pyvisa**
	- If you have never written measurement automation, this is where you start. pyvisa provides easy commands like *query*, *write* and *read* to send commands to, and read from the instrument. It requires the installation of VISA drivers from National Instruments that is available for free.
	- To find the actual commands you need to control the instrument, you will need to download the SCPI programming guide specific to that instrument. Most major instrument manufacturers provide PDF files will all the necessary commands you will need. Here is an example for (some instrument).
	- You can write any custom driver for a given instrument in python by writing high level functions that performs major functions like initialization, setting up instrument states and measurement sequences.

- **pymeasure**
	- Pymeasure is a wrapper on top of pyvisa that makes it easy to write a driver for a measurement instrument. Since it is open source, people (including me for the Agilent 4155/4156) have written drivers for a whole variety of commonly used instruments that you can just start using and extend as you see fit.
	- It also provides easy methods to define your own instrument from scratch without writing all the repetitive boilerplate code you would use if you started with pyvisa.
	- In addition, it allows for live plotting of measurement data and queuing system for large number of measurements based on a graphical interface.

### Tool-Specific API
Automating software is just as important as hardware.  The ability to programmatically set up simulations that are often cumbersome to do manually due to complex setups is invaluable. In addition, it also helps to use code to extract simulation results and perform advanced calculations on them.

Major software vendors like Ansys and Keysight provide APIs for this. Here are some noteworthy ones:
- **pyaedt** https://aedt.docs.pyansys.com/version/stable/index.html
	- This is a python library to interact with Ansys Electronics Desktop. You can create end-to-end workflows to automate problem setup, simulation and plotting results. Check out the step-by-step examples provided to hit the ground running.
- **pwdatatools** https://docs.keysight.com/pwdt0x2x1
	-  Pathwave data tools is a python library that makes it easy to work with various Keysight proprietary and industry-standard data formats. You can easily interact with ADS datasets, generic MDIFs, Touchstone, CITIfile, SMatrixIO, HDF5 or MDM files, and convert them into pandas dataframes; which opens up a world of visualization options as we discussed earlier.



Short form post: [[projects/newsletter/long form/My Favorite Python Packages for RF engineering|My Favorite Python Packages for RF engineering]]