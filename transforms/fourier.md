# Fourier Transforms

In the following visualization, a time series (bottom left, black) is reconstructed (red), by a sum of many sinusoids (top left).
On the right, the phase (top) and amplitude (bottom) of each sine wave is plotted.

## Aperiodic Signal

In the following, the time series is an aperiodic, pink noise signal, decomposed by an FFT:

![fft-ap](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/02-fft/fft-aperiodic.gif)

Note that in the above, the signal is completely non-rhythmic.

Despite the signal not being rhythmic, it can still be
decomposed by a sum on sinusoids.

## Periodic Signal

In the next signal, there is both an aperiodic component (pink noise), as well as
a periodic component (a 10 Hz rhythm).

![fft-pe](https://raw.githubusercontent.com/TomDonoghue/SigViz/main/gifs/02-fft/fft-periodic.gif)

In the above signal, note how the prominent rhythm is fit by a sine wave which
stands out from the other frequencies, capturing the higher power in this frequency.
