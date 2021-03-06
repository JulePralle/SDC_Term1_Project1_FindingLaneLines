# Finding Lane Lines 
Self-Driving Car Engineer Nanodegree Program

---
[//]: # (Image References)

[image1]: ./approach.JPG "Image summarizing the approach"



## Introduction
In this project highway lane lines were detected on a video stream using Python and OpenCV image analysis techniques. 

The following videos show the result:

![yellow](./yellow.gif) 
![white](./white.gif)

## Files and Code

My project includes the following files:
* P1-JP.ipynb: notebook containing the code 
* yellow.mp4/gif: a video showing the lane line detection on the yellow line example 
* white.mp4/gif: a video showing the lane line detection on the white line example 
* README.md: this writeup summarizing the results


## Reflection

### My Approach
The pipeline consists of 5 steps. First, I converted the image to Grayscale, then I used the Gaussfilter to extract interferences out of the image, afterwards I used the Canny function to create an image of edges, then I created the region of interest using three points for a triangle. In the end I created the Hough lines, which are shown as red lines in the image marking the lanes.
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first calculating the slope and center point of all lines and adding them to lists separating by right and left lanes. The next step was to average the data of center and slope to get a single value to create a single line for left and right. At the end I extrapolated the lines to the bottom of the image and a specific height using geometric relationships. 
The code can be found in this notebook <A HREF="P1-JP.ipynb" target="_blank">P1-JP.ipynb</A>.


The image shows the steps of my approach:

![alt text][image1]

### Potential Shortcomings
* curvy roads
* bumpy roads, so that the region of interest maybe doesn’t fit for this situation

### Suggested improvements
* extract more lines which are mistaken i.e. too vertical or horizontal.
* use more than one line to better detect curves
* use more or more advanced computer vision techniques


---
## Udacity Part 

The Project
---

## If you have already installed the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) you should be good to go!   If not, you can install the starter kit or follow the install instructions below to get started on this project. ##

**Step 1:** Getting setup with Python

To do this project, you will need Python 3 along with the numpy, matplotlib, and OpenCV libraries, as well as Jupyter Notebook installed. 

We recommend downloading and installing the Anaconda Python 3 distribution from Continuum Analytics because it comes prepackaged with many of the Python dependencies you will need for this and future projects, makes it easy to install OpenCV, and includes Jupyter Notebook.  Beyond that, it is one of the most common Python distributions used in data analytics and machine learning, so a great choice if you're getting started in the field.

Choose the appropriate Python 3 Anaconda install package for your operating system <A HREF="https://www.continuum.io/downloads" target="_blank">here</A>.   Download and install the package.

If you already have Anaconda for Python 2 installed, you can create a separate environment for Python 3 and all the appropriate dependencies with the following command:

`>  conda create --name=yourNewEnvironment python=3 anaconda`

`>  source activate yourNewEnvironment`

**Step 2:** Installing OpenCV

Once you have Anaconda installed, first double check you are in your Python 3 environment:

`>python`    
`Python 3.5.2 |Anaconda 4.1.1 (x86_64)| (default, Jul  2 2016, 17:52:12)`  
`[GCC 4.2.1 Compatible Apple LLVM 4.2 (clang-425.0.28)] on darwin`  
`Type "help", "copyright", "credits" or "license" for more information.`  
`>>>`   
(Ctrl-d to exit Python)

run the following commands at the terminal prompt to get OpenCV:

`> pip install pillow`  
`> conda install -c menpo opencv3=3.1.0`

then to test if OpenCV is installed correctly:

`> python`  
`>>> import cv2`  
`>>>`  (i.e. did not get an ImportError)

(Ctrl-d to exit Python)

**Step 3:** Installing moviepy  

We recommend the "moviepy" package for processing video in this project (though you're welcome to use other packages if you prefer).  

To install moviepy run:

`>pip install moviepy`  

and check that the install worked:

`>python`  
`>>>import moviepy`  
`>>>`  (i.e. did not get an ImportError)

(Ctrl-d to exit Python)

**Step 4:** Opening the code in a Jupyter Notebook

You will complete this project in a Jupyter notebook.  If you are unfamiliar with Jupyter Notebooks, check out <A HREF="https://www.packtpub.com/books/content/basics-jupyter-notebook-and-python" target="_blank">Cyrille Rossant's Basics of Jupyter Notebook and Python</A> to get started.

Jupyter is an ipython notebook where you can run blocks of code and see results interactively.  All the code for this project is contained in a Jupyter notebook. To start Jupyter in your browser, run the following command at the terminal prompt (be sure you're in your Python 3 environment!):

`> jupyter notebook`

A browser window will appear showing the contents of the current directory.  Click on the file called "P1.ipynb".  Another browser window will appear displaying the notebook.  Follow the instructions in the notebook to complete the project.  

**Step 5:** Complete the project and submit both the Ipython notebook and the project writeup

