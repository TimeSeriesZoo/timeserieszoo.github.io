---
layout: default
---

# Overview of Signal Processing for M/EEG Research

Lets start by (re-)introducing some terms from signal processing that we will be using across this tutorial, including regarding the time & frequency domains, and signal transforms.

## Time & Frequency Domains

To start with, let’s introduce the two ‘domains’ that we often work in:
- time domain: representing a signal as values over time
- frequency domain: representing a signal as activity per frequency

Anytime you record or analyze a signal as some quality over time, you are collecting a time series (a sequence of data points over time), which can be said to be in the time domain. This could be, for example, temperature recordings per day, height of an aircraft per minute, blood sugar levels per hour, etc. Notably, neuro-electrophysiological recordings, such as EEG and MEG, are recorded as times series of data that reflect electrical (or magnetic) activity per time sample. For example, an EEG electrode recording microvolt readings at a sampling rate of 1000 Hz collects a measure of electrical activity per millisecond, creating a time series of microvolts over time.

Note that for simplicity, throughout this tutorial we will consider the case of a single electrode of data.

## Transforms

While we collect neuro-electrophysiological recordings as time series, we typically don’t analyze these raw recordings. Instead, we have to apply a series of transformations to the signals first, in order to process them such as to extract the information we want from the recording.

For our purposes, a “transform” is a mathematical process we can apply to a signal representation that returns a different signal representation. This output representation may be changed in terms of the information it carries (for example, we may apply a transform to remove some activity from the data) and/or may move the signal representation between different domains (for example, turn a time domain representation into a frequency domain representation, or vice versa).

To make this a bit more concrete, the following are some example ’transforms’ within the time domain:
- Downsampling (time domain -> time domain): downsampling is transformation whereby we take a time series, and apply an update procedure to change how often we have a sample of data
- Filtering (time domain -> time domain): filtering is a data transformation in which we apply a filter kernel to a time series to extract and/or remove specified frequencies from the data

We can also consider transforms that move between domains:
- Fourier Transform (time domain -> frequency domain): a mathematical operation that transforms a time-domain signal into its equivalent frequency domain representation
- Inverse Fourier Transform (time domain -> frequency domain): a mathematical operation that transforms a frequency domain representation into the equivalent time domain representation

When we use the frequency domain in EEG & MEG work, we often refer to a ‘power spectrum’, which is a kind of frequency domain representation in which we have frequency values on the x-axis and power values (how much activity there is per frequency) on the y-axis. To create this kind of representation of the data, we can use the Fourier transform.

These general principles (of sampling, filtering, computing frequency domain representations, etc) are hopefully at least somewhat familiar from previous work and discussions. Here, we are reintroducing these concepts to be able to talk about signal representations (time & frequency domains) and signal transformations as they relate to recording and analyzing M/EEG data. In particular, we will discuss the processes through which we apply a series of transformations to recorded data, including changing representations, to arrive at estimates that we interpret, in order to try and interpret what these measurements may tell us about the brain, for example, how they relate to cognitive and/or clinical measurements of interest.

## Feature Extraction

For this last step - of taking an estimate of neural activity and interpreting what it reflects about the brain - we can consider this to be a form of feature extraction. By feature, we just mean an element of the data that we deem to be a pattern of interest, which could be a neural oscillation, or a particular event such as an ERP. For a specified feature of interest, we can apply a set of transforms designed to measure this feature.

The goal of applying our data transforms is to isolate and extract these features in order to measure and interpret them. In doing so, we want to extract features which are appropriate descriptions of the data and which are meaningful and informative reflections of neural activity. For example, neural oscillations are a commonly discussed feature of interest in neural recordings. If we employ a robust analysis plan to isolate oscillatory activity, and accurately relate these measures to correlates of interest, then we can productively make claims about how neural activity relates to our research question(s).

By ‘appropriate descriptions’ of the data, we mean that if we say we measured a particular feature from the data, the process we employed is technically appropriate to isolate and measure that feature — meaning the data transforms and the way we interpret the resulting representation of the data are well defined & motivated.

Note that in the above there is an emphasis on both the transforms themselves and our interpretations of the outputs. This combination serves to emphasize both the technical aspects of employing transforms (for example, making sure to choose appropriate transforms and robust implementations) while also acknowledging that the outputs of correctly applied transformations still require us to interpret their outputs, and these interpretations can be unsupported or incorrect if we do not consider how these transforms relate to the properties of the data.

## Interim Conclusions

To recap so far: in electrophysiological recordings such as EEG & MEG, we record time series of data that we then apply transformations to, in order to process the data in desired ways, to give outputs from which we extract features of interest. In order for this work (in the sense of providing well-defined and interpretable features), we need to understand the properties of the transforms and representations that we employ, in order to make appropriate interpretations of our data.
