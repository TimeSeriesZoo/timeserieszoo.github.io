---
layout: default
---

# Overview of Signal Processing for M/EEG Research

First, let’s set the scene in term and re-introduce some terms from signal processing that we will be using for this section.

## Time & Frequency Domains

To start with, let’s introduce the two ‘domains’ that we often work in:
- time domain: representing a signal in terms of values over time
- frequency domain: representing a signal in terms of activity over frequency

Anytime you record or analyze a signal as some quality over time, you are collecting a time series (a sequence of data points over time), which can be said to be in the time domain. This could be, for example, temperature recordings per day, height of an aircraft per minute, blood sugar levels per hour, etc. Notably, neuro-electrophysiological recordings, such as EEG and MEG, as we will be discussing here, are collected as times series, reflecting electrical (or magnetic) activity per time sample (one recorded value, per electrode, per millisecond, for an example sampling rate of 1000 Hz). For simplicity, throughout this lesson we will consider the case of a single electrode of data, which can be represented in the time domain as  microvolts over times.

## Transforms

Notably, while we collect neuro-electrophysiological recordings as time series, we typically don’t analyze the raw recordings, but rather apply a series of transformations of the signals first. For our purposes, a “transform” is a mathematical process we can apply to a signal representation to get out a different signal representation. This output representation may be changed in terms of the information it carries (for example, we may apply a transform to remove some activity from the data) and/or may move the signal representation between different domains (turn a time domain representation into a frequency domain representation, or vice versa).

To make this a bit more concrete, the following are some example ’transforms’ within the time domain:
- Downsampling (time domain -> time domain): downsampling is transformation whereby we take a time series, and apply an update procedure to change how often we have a sample of data
- Filtering (time domain -> time domain): filtering is a data transformation in which we apply a filter kernel to a time series to extract and/or remove specified frequencies from the data

We can also consider transforms that move between domains:
- Fourier Transform (time domain -> frequency domain): a mathematical operation that transforms a time-domain signal into it’s equivalent frequency domain representation
- Inverse Fourier Transform (time domain -> frequency domain): a mathematical operation that transforms a frequency domain representation into the equivalent time domain representation

When we use the frequency domain in EEG & MEG work, we often refer to a ‘power spectrum’, which is a kind of frequency domain representation in which we have frequency values on the x-axis and power values (how much activity per frequency) on the y-axis. To create this representation of the data, we can use the Fourier transform.

In the above, the general principles (of sampling, filtering, computing frequency domain representations) are hopefully familiar from previous work and discussions. So far, we are just reintroducing these ideas to position them within a general framework of considering how we record time series, and apply a series of transformations to arrive at a representation that we then wish to interpret in terms of what this tells us about the brain, including how it may relate to cognitive and/or clinical measurements of interest.

## Feature Extraction

For this last step, we can consider this to be feature extraction. By feature, we just mean an element of the data that we deem to be a pattern of interest, which could be a neural oscillation, or a particular event such as an ERP or particular waveform shape. The goal of applying our data transforms is then typically to isolate and extract these features in order for us to measure and interpret them. In doing so, what we want to be able to do is to extract features which are appropriate descriptions of the data and which are meaningful and informative reflections of neural activity. For example, neural oscillations are a commonly discussed feature of interest in neural recordings. If we employ a robust analysis plan to isolate oscillatory activity, and accurately relate these measures to correlates of interest, then we can productively do research.

By ‘appropriate descriptions’ of the data, we mean that if we say we measured a particular feature from the data, the process we employed is technically appropriate to isolate and measure that feature — meaning the data transforms and the way we interpret the resulting representation of the data are well defined & motivated. Note the emphasis in the above on both the transforms themselves and our interpretations of the outputs — this is a deliberate framing that we will use throughout whereby we will emphasize both the technical aspects of employing transforms (for example, making sure to choose appropriate transforms and robust implementations), but also discuss how that could be true while our interpretations of the outputs of these transforms (and therefore our claims about the data) could be unsupported or incorrect if we do not interrogate how

(for example, our choice of filter or frequency estimate could be reasonable and properly implemented, but our interpretations of the outputs )

data transforms and ultimate representation of the data appropriately reflects the mathematical processes that got us there and what this reflects about the data.
appropriately reflects the mathematical processes that got us there and what this reflects about the data.

Alternately stated, we could say that a feature representation is an appropriate description of the data if our interpretation of

## Interim Conclusions

**To recap so far: in electrophysiological recordings such as EEG & MEG, we record time series of data that we then apply transformations to, in order to process the data in desired ways, to give outputs from which we extract features of interest. In order for this work (in the sense of providing well-defined and interpretable features), we need to understand the properties of the transforms and representations that we employ.**

## Sources

XX
