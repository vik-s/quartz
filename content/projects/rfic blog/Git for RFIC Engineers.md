---
title: "Git for RFIC Engineers"
status: #blog
tags: 
---

---
I need to rethink this in the context of RF / IC engineering. It is much more applicable to rfic.io. It is too hard for me to address all  hardware engineers.
- Can I show how RF data analysis scripts with scikit-RF should be git controlled?
	- what kind of code snippets writtin in scikit-rf can be most reused across projects?
- Address matlab users and show that git is integrated into matlab. Link some articles showing how it should be used.
- SKILL scripts can be another area to be addressed.
- Apparently PCB files have been revision controlled using git- link some articles.
---

Git is so prevalent in the software engineering world yet so few hardware engineers know of it, or use it effectively in their work. But hardware engineers do write and use software code in their day to day work, to do data analysis with python, build various simulation systems with Matlab's Toolboxes, write SKILL code for Virtuoso or perform lab automation with Labview or C-sharp.

Revision controlled code can greatly benefit all these situations to maintain functioning and high quality code that can be reused in the future while making continuous improvements for efficieny, features and accuracy. This usually has payback in terms of getting work done more quickly and correctly in the future.

One fundamental pain point in a lot of these applications is that git is not built in to the development environments used by engineers. Another reason is the hesitation of hardware engineers to use the command line for doing anything. In such cases, I'd argue that a GUI based version control system is just as fine, as long as the benefits of version control are made available to hardware engineers. To this end, I would recommend getting started with Github desktop as a GUI tool.

< At some point you will have to explain what git and github actually is >

But what about propreitary information? We do not want to put that up on Github for all to see! That is a valid concern that should cross all our minds as we work on proprietary technologies in our companies. After trade secrets are what pays our bills! 

There are two solutions for this:
1. If you are not worried about collaboration, and want to version control just the code you develop, then running a git repository entirely local to your computer is the answer. This way, you will not have to sync anything to a central server and risk exposing important information.
2. If you do have the need to collaborate, then it is worthwhile checking if your organization has a github enterprise server setup for your use. If not, you can request your IT department to see if you can get one set up. This way, you will not have to use github.com as your remote repository server.

Let us look at a rather common use case of git for a hardware engineer. Assume you have a CSV data file that contains measurements of some hardware in the lab, and you are using MATLAB to process the data and perform some analysis.

< You need to work on some code examples  >

Here are the steps you need to do:

- Initialize a git repo with Git GUI for this codebase
- Check in some files and push to remote repository
- Make some code updates and commit-push again
- Show commit history
- Demonstrate branching and merging
- Demonstrate forking
- Making releases and tagging

Investigate other git flows - command line based, VScode plugin... does Matlab acutally integrate Git now?

< Put in some resources to go deeper into git / github. There are plenty of oneline resources I dont have to go into >

The main concent behind git is to check in code, and not acyutally check in data. Github has a 50MB file limit that is sufficient to hold about a million lines of code. While, it is possible to store data in Github, it is not intended for that. However, as long as the file size limitations are not a constraint, there is nothing acutally preventing you from version controlling data files. 

Anyone in the corporate environment would wonder if Git is useful for word and powerpoint documentation. I wouldn't really recommend using it for such an application since Microsoft's OneDrive integration does provide version control that works much better for something like this.

Also, if you are ever interested in participating in open source projects, git is something you should know. Here are several interesting projects that might pique your interest!

- Free and open source VNA: https://github.com/jankae/LibreVNA
- RF engineering in python: https://github.com/scikit-rf/scikit-rf
- Spice simulator written in python: https://github.com/giaccone/SpicePy
- Xyce - open source spice simulator: https://github.com/Xyce/Xyce
- Open Source ADS-like circuit simulator: https://github.com/Qucs/qucs/
- RF Microwave Engineering: https://github.com/DevMajed/RF-Microwave-Engineering

### References:

- https://www.allspice.io/post/git-for-hardware-commit-best-practices
- https://www.allspice.io/blog/categories/git-for-hardware
- https://content.allspice.io/en-us/git-for-hardware-guide
- https://www.cliosoft.com/2022/01/05/git-r-dont-for-hardware-design/ -- argues that Git is unsuitable for hardware design... of course, this is by Cliosoft- whose business is a centralized form of revision control.
- https://resources.altium.com/p/introduction-git-altium-designer
- https://git-scm.com/docs/user-manual

Matlab and Github
- https://www.mathworks.com/help/matlab/matlab_prog/use-git-in-matlab.html
- https://www.mathworks.com/help/simulink/slref/using-a-simulink-project-with-git.html
- https://marketplace.visualstudio.com/items?itemName=Gimly81.matlab
- https://github.com/mathworks/jupyter-matlab-proxy