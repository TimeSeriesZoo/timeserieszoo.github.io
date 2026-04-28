---
layout: default
---

# Separating Periodic & Aperiodic Activity

Thus far we have explored some basic principles of signal processing and connected these ideas to the analysis of neuro-electrophysiological recordings. In doing so, we have highlighted potential issues and difficulties in applying signal processing techniques to this data, in particular in being confident about identifying and interpreting measures as reflective of oscillatory activity.

In this section, we will explore a strategy for analyzing neuro-electrophysiological recordings that seeks to address these difficulties, which is spectral parameterization - a method for parameterizing periodic and aperiodic components from neural power spectra.

## Spectral Parameterization

Spectral parameterization is a method for measuring both periodic and aperiodic components of neural power spectra. To do so, it fits a model to the power spectrum that seeks to embody the ideas that we have been exploring - that the data can be described as peaks of oscillatory power over and above an aperiodic component that contributes power across all frequencies.

The goal of the model is there to arrive at a description of the neural power spectrum as follows, wherein peaks of power are detected and measured wherever they occur, and measured relative to the aperiodic component, which is also itself measured:

![specparam-model](https://raw.githubusercontent.com/specparam-tools/specparam-tools.github.io/main/_images/sphx_glr_plot_01-ModelDescription_005.png)

In the above model, we can now extract estimates for the both the aperiodic and periodic components!

In order to fit this model, the spectral parameterization algorithm explicitly fits a combination of peaks and the aperiodic component, including an iterative peak search to detect putative oscillatory peaks. Notably, these peaks are detected wherever they occur, regardless of their center frequency, their heights are measured relative to the aperiodic component, and there is also a measure of the aperiodic activity to evaluate if this component of the data is also changing:

![specparam-algo](https://raw.githubusercontent.com/fooof-tools/Visualizers/main/gifs/specparam-algorithm.gif)

When using spectral parameterization, the output measures provide an estimate of the peak activity (controlling for aperiodic activity) as well as estimates of the aperiodic activity itself.

## Brief Aside on Aperiodic Neural Activity

Much of the discussion and motivation of this tutorial thus far has largely focused on considering oscillatory neural activity as a feature of interest and treating the aperiodic activity as a nuisance component (something in the way of this goal).

While this perspective is valid for situations in which oscillations are the feature of interest, it is worth emphasizing that a significant amount of work is now emerging regarding aperiodic neural activity which emphasizes that it is also an interesting feature of interest. Indeed the very elements that make aperiodic activity important to consider - including that it is ubiquitously present and dynamic - as well as some modeling work emphasizing its neural origins and potential interpretations, emphasize that it is also an feature of interest for possible investigation! As such, spectral parameterization can also be used in situations in which the goal is actually to measure the aperiodic activity of neural time series (while controlling for peak activity).

## Interim Conclusions

In this section, we explored how spectral parameterization can be used to analyze neural power spectra, providing estimates that separate and measure both periodic and aperiodic components of the data.

## Sources

This example draws from the [spectral parameterization (specparam)](https://specparam-tools.github.io/) project and tool.
