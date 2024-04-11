---
title: My Favorite Python Packages for RF engineering
tags:
  - programming
project: substack
date_published: 
status: 🚧
final title:
---
As it seems that my last post on AI/ML has ruffled quite a few feathers in the industry, I figured I'll go easy this week and talk about some tools I use regularly.

If there's one skill that has paid itself back 100x for the time I have spent learning it, it is this: Programming.

The actual language doesn't matter, although I do find Python quite convenient. If you have access to a Matlab license, then use that. Otherwise, Octave is an alternative that is largely compatible with Matlab syntax. R is another popular package for data analysis, especially if your work involves a lot of statistics. If you're up for a challenge, I'd recommend learning Julia because it is blazing fast for engineering work. 

For the ultimate bragging rights, go learn Fortran. Yes, Fortran. Laugh all you want, but as it turns out it is the most computationally efficient language for engineering work. So much so, that it is used to benchmark supercomputers. It is still being actively developed, and is the basis for a lot of numerical tools that involve applied math, finance and computational fluid dynamics. From the Fortran website:

> If you’re writing a program or a library to perform fast arithmetic computation over large numeric arrays, Fortran is the optimal tool for the job.

Today we will stick to Python. Only because I think it is easy to get going quickly, and there is lots of infrastructure that you can readily use to get your work done.
### Getting Started

If you're wondering where to start, just install the Anaconda distribution of Python. It contains most of the packages you'll ever need, especially if you install the complete version (not miniconda.) It is cross platform and supported on Windows, Linux and Mac.

With the Anaconda package, you get an integrated development environment (IDE) called Spyder that is quite easy to use. I personally use VScode as IDE, but I've found PyCharm to be quite convenient on many occasions too. It's a matter of personal preference. If you are using it for commercial work, be sure you understand the licensing requirements. IDE-based programming is useful in many occasions, especially if you want to view variable values or want to work on multiple files at once.

If you are doing scripting for data analysis, I recommend using Jupyter notebooks. They run in your browser and allows you to create code blocks. A program does not have to be its own block or even run sequentially. It supports a mixture of code and text annotation using markdown syntax. This makes it very useful to create reports along with text explanations and code blocks to process results. 

Another concept you should understand when just starting out, is the use of virtual environments. They are isolated sandboxes where you keep compatible versions of the packages you use. They will not change if you update your main Anaconda installation. They are especially useful if you need to your code to work in other computer environments. A colleague can replicate your virtual environment and have all your code run on their computer.

Finally, I'd recommend you learn how Git works. Git is a distributed version control system that you can use to control code revisions. This is helpful if you ever need to revert to a previous version of the code, or have multiple people working on a code project. You can install Git locally and use it to version control your code. If you want to do it on a companywide basis, you might have to talk to IT.

This is super common among software engineers, but I see few RF engineers use it effectively. If you want to learn how to get started, read this.

Let's dive into some useful applications of python in RF engineering work.
### Scikit-RF



Here are the top python frameworks I use as an RF engineer and why: 👇

🔧 General-purpose:

↳Scikit-RF: https://scikit-rf.org
The workhorse. Parses touchstone files. Supports matplotlib plots and smith charts.

↳Pandas: https://pandas.pydata.org
Data processing using jupyter notebooks. CSV import/export.

↳Matplotlib: https://matplotlib.org
Basic plotting. Plenty of online examples for making good looking plots.

↳Seaborn: https://seaborn.pydata.org
Stats baby! Advanced plotting instantly makes my PPTs awesome.

↳Plotly: https://plotly.com
Easy to make data dashboards/apps. One of the few packages that natively support smith charts.

📏 Measurement:

↳pyvisa: https://pyvisa.readthedocs.io/en/latest/#
The comprehensive lab measurement package using GPIB, USB, etc. 

↳pymeasure: https://pymeasure.readthedocs.io/en/latest/
A high level wrapper for pyvisa that has a bunch of readily available instruments.

🤌 Tool specific:

↳Keysight python API:https://www.keysight.com/us/en/lib/resources/miscellaneous/eda-software/python-eda.html
ADS has a python interface, but I use the python interface to ICCAP a lot.
I'm a device modeling guy, what can i say.

↳pyAEDT: https://aedt.docs.pyansys.com/version/stable/
I don't do much EM stuff at work nowadays but this looks awesome.


Short form post: [[projects/newsletter/long form/My Favorite Python Packages for RF engineering|My Favorite Python Packages for RF engineering]]