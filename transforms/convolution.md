# Convolution

Here, a signal (grey) is convolved with a gaussian kernel (red), meaning we "slide" the kernel across the signal, computing each output value (green) by multiplying the kernel with the underlying signal (blue).

## Long Kernel

In this first example, we will examine convolution using a long kernel.

![conv-long](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/03-convolution/convolution-long.gif)

## Short Kernel

Next, we can examine how things are different when we use a shorter kernel.

![conv-short](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/03-convolution/convolution-short.gif)

## Technical Notes

Some technical notes on the convolution:
- The "multiplication" applied between the kernel and the signal is the dot product
- Only the range where the kernel fully overlaps the signal is shown
- By definition, convolution applies the reverse of the kernel
    - In these examples, the kernel is symmetric, so it doesn't change anything
