---
layout: default
---

# Signals & Transforms

In this section, we will briefly explore some basics of time series signals and the kinds of transforms that we can apply to them.

## Signals

First, lets explore some signals, with some different characteristics.

In each of the following visualizations, a signal is representated in both time domain (left panel; time on the x-axis and signal value on the y-axis) and the frequency domain (right panel; with frequency on the x-axis and power on the y-axis).

First, lets look at an oscillatory (periodic) signal, generated as a pure sinusoid.

![ts-osc](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/01-timeseries/ts-osc.gif)

Note that as a pure rhythmic signal, we can see the systematic alternation in the time domain, and in the frequency domain we see a spike of activity in the characteristic frequency (the frequency of the rhythm), with very low power at all other frequencies. This is characteristic of a rhythmic signal.

Next up, lets examine a non-rhythmic (aperiodic) signal, here generated as pink noise. Pink noise is like white noise (which is random activity with equal power at all frequencies), except that pink noise has a pattern of decreasing power across increasing frequency. In the power spectrum we can see that there is power across all frequencies, which is a hallmark of what we will call 'aperiodic' signals (signals with no characteristic frequency).

![ts-pink](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/01-timeseries/ts-pink-noise.gif)

Finally, let's examine a combined signal, meaning a signal that is created as a combination of a periodic component and an aperiodic component. Note that the power spectrum shows characteristics of both components, with a peak of power at the characteristic frequency of the oscillation and a pattern of decreasing power across all frequencies from the aperiodic component.

![ts-comb](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/01-timeseries/ts-comb.gif)

## Fourier Transform

In the above we examined signals showing their representations in both the time and frequency domains. Now lets examine how we can move between these two domains, using the Fourier transform.

In brief, the Fourier transform is an algorithm to compute the frequency domain representation of a signal. In the frequency domain, the signal is represented as a sum of sinusoids. In the below visualizer, we can see a representation of applying the Fourier transform to a combined signal, showing how the sine waves are combined to represent the original signal.

![fft-pe](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/02-fft/fft-periodic.gif)

In the above we can see that even though sine waves are rhythmic, they are also a very flexible basis set, such that combinations of sine waves are able to capture all the variation of the signal. In fact, the Fourier transform, using sine waves as a basis set, is able to perfectly represent any time domain signal! This means that in terms of the information about the signal, the two different domains are mathematically equivalent and complete representations of the signal.

This property of Fourier transforms and frequency domain representations is very powerful, allowing us to move between time and frequency domain representations without information loss. However it also is something we have to keep in mind when interpretation frequency domain representations - notably, that power at a particular frequency value in a frequency domain representation does not necessarily mean there is anything _rhythmic_ in the signal at that specific frequency. Rather, it may be that the power at a given frequency is simply part of the 'ingredients' for how the Fourier transform represents non-rhythmic activity, without necessarily reflecting any frequency-specific activity.

To see this in action, we can again apply a Fourier transform to a purely aperiodic signal (pink noise):

![fft-ap](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/02-fft/fft-aperiodic.gif)

Note that the Fourier transform is not the only way to move between the time and frequency domain (for example, a wavelet transform accomplishes the same thing). Other kinds of transforms that map between domains are largely equivalent - so while we will here refer to and focus on Fourier transforms, the same general principles and topics discussed here apply when moving between the time & frequency domain using different transformations.

## Filters

'Filtering' refers to a transform in which a filter kernel is convolved with a signal in order to transform the data to include or exclude particular frequencies. By designing different filter kernels with different properties, we can use filters to select or reject frequency ranges of interest from time domain signals.

For example, in the following example a bandpass filter for a frequency range of interest (e.g. 8-12 Hz) is applied to a combined signal:

![filtconv-combined](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/04-filters/filtconv-combined.gif)

In the above we can see how the filter kernel, designed to extract rhythmic activity in a particular frequency range, is able to extract a filtered version of the signal, that reflects the frequency specific activity of the signal.

So what happens if we filter a signal without a rhythm in it? In the following example we apply the same frequency-specific bandpass filter to a purely aperiodic signal (pink noise):

![filtconv-aperiodic](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/04-filters/filtconv-aperiodic.gif)

Note that this filtering operation still extracts frequency specific activity!

Mathematically this is indeed an accurate representation of the activity at those frequencies in the signal - just as how the power spectrum of the signal has non-zero power at these frequencies we can extract this power in the time domain with a filter. This happens for effectively the same reasons, which is the flexibility of sine waves, as filters also leverage these signal properties. Here again we need to remember that this flexibility of sine waves comes with the corresponding caveat that being able to filter a signal and extract a rhythmic looking component doesn't by itself necessarily mean that original signal contains rhythmic activity!

## Interim Conclusions

In this section we covered some basic properties of signals in the time and frequency domain, including signals with periodic (frequency specific) and/or aperiodic (non-frequency specific) activity. We also explored some example transforms that demonstrate both the utility and complexity of the way that sine waves can represent any time domain signal. Notably, this establishes that non-zero power at a particular frequency in the power spectrum and/or as extracted by a filter is not by itself evidence for rhymicity of a signal, which we always need to consider when interpreting the outputs of these transforms.

## Sources

The filter visualizers in this section are based in part on the following paper:
- [Filters: When, Why, and How (Not) to Use Them](https://dx.doi.org/10.1016/j.neuron.2019.02.039)
