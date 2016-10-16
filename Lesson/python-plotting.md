# Plotting in Python

### Topics

1. [Overview of useful modules for plotting in Python](#overview-of-useful-modules-for-plotting-in-Python)
2. [Anatomy of a plot](anatomy-of-a-plot)
3. [Plotting in Python with Matplotlib](#plotting-in-python-with-matplotlib)

## Overview of useful modules for plotting in Python

Python has many nice and useful modules that can be used for plotting, such as:
  
  - [**Matplotlib**](http://matplotlib.org/)  - _"the grand old man of Python plotting"_
    - [**Matplotlib Basemap**](http://matplotlib.org/basemap/index.html) - Matplotlib plugin for visualizing maps in Python [(see gallery)](http://matplotlib.org/basemap/users/examples.html)
    - [**Seaborn**](https://seaborn.github.io/) - High-level interface for drawing attractive statistical graphics that is built on top of Matplotlib ([see gallery](https://seaborn.github.io/examples/index.html))
  - [**Bokeh**](http://bokeh.pydata.org/en/latest/) - Modern plotting library for static / interactive web-based plots such as graphs, maps, charts etc. ([see gallery](http://bokeh.pydata.org/en/latest/docs/gallery.html)) 
  - [**Plotly**](https://plot.ly/python/) - Modern plotting library for static / interactive web-based plots such as graphs, maps, charts etc. Some features are commercial. ([see gallery](https://plot.ly/python/#basic-charts))
  - [**ggplot**](https://github.com/yhat/ggplot) - Familiar with doing plots in R using ggplot2? You can use ggplot in Python too! [(see examples)](https://github.com/yhat/ggplot/blob/master/docs/Gallery.ipynb)
  - [**HoloViews**](http://holoviews.org/) and [**GeoViews**](http://geo.holoviews.org/) - New! Let the data visualize itself. (see this [introductory video](https://www.youtube.com/watch?v=hNsR2H7Lrg0)) 
     - Modern and powerful visualization libraries built on top of **Matplotlib** and **Bokeh** that makes exploring and visualizing your data quicker than ever before.
     - **HoloViews** is designed for basic plotting ([see tutorial](http://holoviews.org/Tutorials/index.html) and [examples](http://holoviews.org/Examples/index.html))
     - **GeoViews** is designed for creating nice and interactive maps ([see gallery](https://www.continuum.io/blog/developer-blog/introducing-geoviews)).

**Task**: _Explore the galleries and examples of different visualization libraries to learn what's possible to do in Python._

As you can see from the examples, the plotting possibilities in Python are numerous and rich. Do you need to know them all? Of course not. Not even us do. 
It is not even rational for trying to use them all, instead you should start by learning to use one of them that suits your needs and then later extend your
knowledge and skills to other visualizing libraries when necessary. In our courses, we will be start our plotting experiments with Matplotlib and Plotly that 
makes it possible to store and show our interactive plots in the web. 

*Later, in the Automating GIS processes -course, we will be learning a little bit of Bokeh as well.* 

**Pro -tip**: for doing interactive visualizations in Python, it can be extremely useful to use a specific software called 
**[Jupyter](https://jupyter.readthedocs.io/en/latest/index.html#)** that is extensively used nowadays for documenting, presenting and 
visualizing interactive plots in Python using specific [Notebooks](https://tmp58.tmpnb.org/user/JfCwgSeJpZUg/notebooks/Welcome%20to%20Python.ipynb). 
Jupyter Notebook is also installed in our computer instance. 

## Anatomy of a plot

Before starting to do plotting it is useful if we take a look and try to understand **what actually is a plot?** We won't go too deep into the details of 
different plots (as it is not the purpose of this lesson) but we rather give a short introduction to different plots that can be done with Python, and what
kind of (typical) elements a plot has. 

There are a variety of different kinds of plot (also known as graphs or charts or diagrams etc. - Our dear child has many names) available 
that have been designed to represent visually the characteristics of a dataset. 
Here is a list of few different types of plots that can be used to visualize different kinds of datasets:
    
  - [Bar chart](https://en.wikipedia.org/wiki/Bar_chart)
  - [Histogram](https://en.wikipedia.org/wiki/Histogram)
  - [Scatter plot](https://en.wikipedia.org/wiki/Scatter_plot)
  - [Line chart](https://en.wikipedia.org/wiki/Line_chart)
  - [Pie chart](https://en.wikipedia.org/wiki/Pie_chart)
  - [Box plot](https://en.wikipedia.org/wiki/Box_plot)
  - [Violin plot](https://en.wikipedia.org/wiki/Violin_plot)
  - [Dendrogram](https://en.wikipedia.org/wiki/Dendrogram)
  - [Chord diagram](https://en.wikipedia.org/wiki/Chord_diagram)
  - [Treemap](https://en.wikipedia.org/wiki/Treemap)
  - [Network chart](https://en.wikipedia.org/wiki/Network_chart)

There are certain elements that are common in most of the plots (not all). It is useful to know at least the basic terminology since it makes 
it easier to find help and information from the internet when you start doing or modifying your own plot. 

Following figure illustrates different elements of a basic line chart:

 <img src="https://github.com/Python-for-geo-people/Lesson-7-Plotting/blob/master/img/basic-elements-of-plot.png" width="800"/> 

### Common terms when doing plotting

Note: these terms may vary a little bit depending on the plotting library that you use. These are few typical terms used when doing plotting in Matplotlib. 

 - **axis** - Axis of the graph that are typically x, y and z (for 3D plots)
 - **title** - Title of the whole plot.
 - **label** - Name for to the whole axis.
 - **legend** - Legend for the plot.
 - **tick label** - Refers to the text or values that are represented on the axis.
 - **symbol** - Symbol for data point(s) (on a scatter plot) that can be presented with different symbols.
 - **size** - Size of e.g. a point on a scatter plot, also used for referring to the text sizes on a plot.
 - **linestyle** - The style how the line should be drawn. Can be e.g. solid or dashed.
 - **linewidth** - The width of a line in a plot.
 - **alpha** - Transparency level of a filled element in a plot (values between 0.0 (fully transparent) to 1.0 (no trasnparency)).
 - **tick(s)** - Refers to the tick marks on a plot.
 - **annotation** - Refers to the added text on a plot.
 - **padding** - The distance between a (axis/tick) label and the axis.

## Plotting in Python with Matplotlib
Python has a nice plotting library called Matplotlib, which is designed to provide MATLAB-like plotting in Python.

1. We can start by importing the Matplotlib plotting library.

    ```python
    import matplotlib.pyplot as plt
    ```
You may see a few messages, but don't worry about them. Note here that we have imported Matplotlib's Pyplot library as `plt`.

2. Let's start with a simple example using our old variables `x` and `y`.

    ```python
    >>> plt.plot(x, y)
    [<matplotlib.lines.Line2D at 0x109e25898>]
    >>> plt.show()
    ```
This should produce a plot like the one below.

    ![Sine curve from zero to two pi](Images/Sine-0-2pi.png)
A bit easier to visualize the array data rather than looking at the values themselves.
2. We can make our plots a bit nicer by using a few additional Matplotlib options.

    ```python
    >>> plt.plot(x, y, 'ro--')
    [<matplotlib.lines.Line2D at 0x10bd249e8>]
    >>> plt.title('Sine curve')
    <matplotlib.text.Text at 0x10b0af320>
    >>> plt.xlabel('x-axis'); plt.ylabel('y-axis')
    <matplotlib.text.Text at 0x10b08df98>
    >>> plt.show()
    ```
This should produce the plot below.

    ![Fancy sine curve ](Images/Sine-in-red.png)

Now we see our sine curve as a red dashed line with circles showing the points along the line. This comes from the additional `ro--` used with `plt.plot()`. In this case, `r` tells it to use red color, `o` tells it to show circles at the points and `--` says to use a dashed line. You can use `help(plt.plot)` to find out more about formatting plots. We have also added a title and axis labels.
3. Adding text to plots can be done using the `plt.text()` function.

    ```python
    >>> plt.text(2.0, 0.0, 'Here is some text')
    ```
This would add the text "Here is some text" at the location x=2.0, y=0.0 on the plot. You will need to do `plt.show()` again to update the plot.
4. Changing the plot axes can be done using the `plt.axis()` function.

    ```python
    >>> plt.axis([0.0, np.pi, 0.0, 1.0])
    ```
The format for `plt.axis()` is `[xmin, xmax, ymin, ymax]` enclosed in square brackets. Here, the x range would be changed to 0-pi and the y range would be 0-1.
