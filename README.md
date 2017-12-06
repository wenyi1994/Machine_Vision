# Machine-Vision `2017/12/06`
Matlab (perhaps also other) codes for realization of assignments of course Machine Vision in KIT

## Assignment 4: Color and Segmentation
> **update 2017/12/06**  
> Add [README.md](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/GUI/README.md) to [GUI](https://github.com/wenyi1994/Machine-Vision/tree/master/Assignment4/GUI) directory. This is an introduction to GUI-tool.

> **update 2017/12/04**  
> \>>[`GUI-Tool`](https://github.com/wenyi1994/Machine-Vision/tree/master/Assignment4/GUI)  
> This is a GUI-Tool of image operations. It can divide the image into several segments with CCL or K-means algorithm. Further more, it can execute some morphological operations on original/segmented image. 
> ![image](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/GUI/pics/main_GUI_171206.png)

> **update 2017/12/03**  
> \>>[`morphoim.m`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/morphoim.m)  
> If the type of `morphological operations` is not detected, title string can be correctly output now.
1. Load the image file [`stack.png`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/stack.png) and transform it into HSV and L\*a\*b\* color space. Show 3 channels of HSV and only luminance channel of L\*a\*b\*.
2. Apply CCL (connected components labeling) algorithm to image [`stack.png`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/stack.png). Vary the threshold to achieve different results.  
> \>>[`coloring.m`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/coloring.m)  
> This is a function that can fill a image generated by [`CCL.m`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/ccl.m), legal input of used colors can be numbers(like `3` `5` or any positive integer), colormaps(like `[1,0,0; 0,1,0; 0,0,1]`) or image(by MATLAB loaded image varible like `I = imread(stack.png)`)
3. Use k-means clustering ([`color_kmeans.m`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/color_kmeans.m)) for color segmentation. Vary color space by using RGB, L\*a\*b\* or its different channels.
4. Apply morphological operations on image to fill the holes in the segments.  
> \>>[`morphoim.m`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/morphoim.m)  
> With this function MATLAB can execute continuously morphological operations on given image. The result and used binary matrix will be plotted. Following is an example of erasion, dilation, and again erasion and dilation.
> ![image](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/morpho_result.jpg)

*Further description refers to [`morphoim.m`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/morphoim.m) and [`bimat2im`](https://github.com/wenyi1994/Machine-Vision/blob/master/Assignment4/bimat2im.m)*

## Assignment 3: Line Estimation
> **update 2017/11/27**  
> The direction of line now can be correctly calculated. (Remove `if(...) c=-c`)  
> Upload template solution of it in directory [`~/Assignment3/Loesung`](https://github.com/wenyi1994/Machine-Vision/tree/master/Assignment3/Loesung).
1. Use total-least-square methode to estimate the line parameters (theta, c) from a list of pixel coordinates;
2. Determine start and end point for the line by projecting all the edge-pixel points on the line;
3. Remove some distance-outmost points;
4. Use RANSAC (random sample consesus) methode to re-estimate the line parameters (theta, c) and plot these lines.

## Assignment 2: Edge Detection and Hough Transformation
1. Use Sobel Filter to calculate the grey value gradient of the image 'postit2g.png', display and compare the results;
2. Generate edge image with Canny- and the LoG-approach, both of them are MATLAB built-in function;
3. Perform the Hough Transformation on egde image and plot the respective lines into the image.

## Assignment 1: Getting start with MATLAB
1. Read in a image and display it;
2. Calculate some properties of image;
3. Create a Gaussian filter mask and convolute it with the image;
4. Use Wiener deconvolution to restore the image from blurred one;
5. Edit the image after fading out.
