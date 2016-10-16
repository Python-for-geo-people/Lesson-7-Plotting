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
