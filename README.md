# Scientific Projects
 
A collection of Python projects exploring scientific computing, mathematics, statistics, data analysis, signal processing, machine learning, and visualization. Each project pairs a core scientific or mathematical concept with a hands-on Python implementation using NumPy, Matplotlib, SciPy, scikit-learn, and other libraries from the scientific Python stack.
 
<p align="center">
  <img src="animations/MobiusTransformAnimation.gif" alt="Möbius transform animation" width="600">
</p>
## Contents
 
- [Animations](#animations)
- [Data Curve Fitting](#data-curve-fitting)
- [Awesome Math Stuff](#awesome-math-stuff)
- [Clustering](#clustering)
- [Colorful Rainbow of Noise](#colorful-rainbow-of-noise)
- [Cryptocurrency Investing](#cryptocurrency-investing)
- [Denoising Signals](#denoising-signals)
- [Descriptive Statistics Without NumPy](#descriptive-statistics-without-numpy)
- [Entropy of English](#entropy-of-english)
---
 
## Animations
📁 `animations/`
 
**Concept.** Animation turns a static equation into something you can watch evolve — useful for building intuition about oscillation, transformation, and emergent structure that's hard to grasp from a formula alone.
 
**What's inside.**
- A **complex Morlet wavelet** — a sine wave multiplied by a Gaussian envelope — is built from scratch and animated across phase shifts, first as a static Matplotlib plot of its real part, imaginary part, and magnitude, then as an interactive Plotly figure with play/frame controls.
- A **Möbius transformation** `(t-1 + (t+1)z) / (t+1 + (t-1)z)` is applied to a grid of complex numbers and animated over a range of `t` values using `matplotlib.animation.FuncAnimation`, rendering the real part, imaginary part, and magnitude side by side as the transformation warps the plane. This is the animation saved as the repo's GIF.
- A **bonus "wandering prime" walk**: the gaps between consecutive prime numbers (found via `sympy.isprime` up to 100,000) are used as step lengths in a turtle-graphics-style walk that turns 90° after each step, producing an emergent spiral/maze pattern purely from the distribution of primes.
---
 
## Data Curve Fitting
📁 `DataCurveFitting/`
 
**Concept.** Curve fitting is the process of finding the parameters of a mathematical model that best explain observed (and noisy) data — the foundation of regression, calibration, and much of experimental science.
 
**What's inside.**
- Uses the `lmfit` library to fit models to synthetic noisy data and inspect goodness-of-fit (R²).
- **Gaussian fitting**: generates noisy Gaussian-shaped data and recovers amplitude, center, and width.
- **Exponential decay fitting**: fits a 1/x²-type decay curve corrupted with Gaussian noise.
- **Custom sigmoid model**: defines a sigmoid function by hand (rather than using a built-in), then fits it — demonstrating how to wrap any user-defined function as an `lmfit.Model`.
- **Composite ("conjunctive") models**: combines a Gaussian model *and* a linear model (`Model(gaussian) + Model(linear)`) into a single fit, showing how component models can be added together.
- **Multivariate/2D fitting**: fits a parametric circle model `(r·cos θ, r·sin θ)` to noisy x/y coordinate data, extending curve fitting beyond single-variable functions.
- A bonus section draws a stylized "Eye of Sauron" using nested `matplotlib.patches.Ellipse` shapes — a lighthearted detour into geometric shape composition.
---
 
## Awesome Math Stuff
📁 `awesomeMathStuff/`
 
**Concept.** A grab-bag tour of mathematical ideas — combinatorics, complex numbers, probability distributions, relativity, and linear algebra — each rendered visually to make the underlying structure easier to see.
 
**What's inside.**
- **Pascal's Triangle**: built from scratch using a custom `n choose k` (binomial coefficient) function, then visualized as both a heatmap and printed as a triangle.
- **Euler's identity**: demonstrates that a complex number expressed in Euler notation (`m·e^(iθ)`) equals the same number in rectangular form (`m·(cos θ + i sin θ)`), plotted on both polar and Cartesian axes overlaid in the same figure.
- **Fully parameterized Gaussian function**: builds a Gaussian from amplitude, width, and offset parameters, then sweeps each parameter independently (as a heatmap over many curves) to show how each one shapes the curve.
- **Time dilation in special relativity**: computes the relativistic time-dilation factor `1/√(1−v²/c²)` for real-world speeds — a car, the Autobahn, a plane, a satellite, Earth's orbit, and the Solar System's orbit around the galaxy — and plots the (tiny but nonzero) differences as a bar chart.
- **Eigenvalues of random matrices**: generates many random matrices, computes their eigenvalues, and plots them in the complex plane — an intuitive, visual entry point into random matrix theory (the eigenvalues cluster inside a circle, a preview of the *circular law*).
- A bonus "I ❤ math" section plots a parametric heart-curve equation purely for fun.
---
 
## Clustering
📁 `clustering/`
 
**Concept.** Clustering finds natural groupings in unlabeled data. This project walks through the full pipeline: normalize → understand structure via covariance/PCA → reduce dimensionality → cluster.
 
**What's inside.**
- Downloads a real dataset — NASA/UCI's `cloud.data` — directly via `wget` and parses it manually into a NumPy array.
- **Z-normalization**: each feature is rescaled to zero mean and unit variance, with before/after plots.
- **Covariance analysis**: computes and visualizes covariance matrices for both raw and normalized features to show how normalization changes feature relationships.
- **PCA (Principal Component Analysis)**: reduces the cloud dataset to its principal components, plots a scree plot (variance explained per component), and projects the data into 2D PC space.
- **t-SNE + k-means**: runs t-SNE for nonlinear dimensionality reduction, then applies k-means (`k=2`) on the t-SNE output to separate the data into two clusters, plotted in different colors. Also explores how the `perplexity` parameter changes the t-SNE embedding.
- A bonus section builds a **2D likelihood density plot**: bins the t-SNE output into a grid, counts point density per bin, and smooths it with a Gaussian filter (`scipy.ndimage.gaussian_filter`) to produce a heatmap of where data concentrates.
---
 
## Colorful Rainbow of Noise
📁 `colorfulRainbowOfNoise/`
 
**Concept.** "Colors" of noise (white, brown, pink, blue, ...) are defined by how their power is distributed across frequencies — a core concept in signal processing, acoustics, and time-series analysis.
 
**What's inside.**
- **White noise**: generated directly from `np.random.randn` — flat power across all frequencies.
- **Brown(ian) noise**: the cumulative sum of white noise (a random walk), which concentrates power at low frequencies.
- **Pink noise**: constructed in the frequency domain by shaping a Fourier spectrum so amplitude falls off as ~1/frequency, then inverse-transformed back to the time domain (`scipy.fftpack.ifft`).
- **Blue noise**: built the same way as pink noise but with amplitude that *increases* with frequency.
- For each type, the code computes and plots the **power spectrum** via FFT to show how each noise "color" actually distributes its energy — directly connecting the visual time-domain signal to its frequency-domain fingerprint.
- A bonus section renders each noise type as **audio** using `IPython.display.Audio`, so you can literally hear the difference between white, brown, pink, and blue noise, with code to export `.wav` files.
---
 
## Cryptocurrency Investing
📁 `cryptoInvesting/`
 
**Concept.** Applies basic financial/statistical analysis and simulation to real historical cryptocurrency price data — including a practical comparison of dollar-cost-averaging (DCA) strategies.
 
**What's inside.**
- Uses the `Historic-Crypto` package to pull real daily price history (2020–2021) for multiple EUR-denominated coins (BTC, ETH, XLM, ALGO, LINK) from a live API.
- Averages OHLC (open/high/low/close) columns into a single representative price per day, and visualizes price trends (including log-scale) and pairwise relationships (`seaborn.pairplot`).
- **PCA on price time series**: examines how much shared variance exists across coins, both on raw and min-max-scaled price data, via scree plots.
- **DCA simulations** — three different strategies are coded and compared by simulating money invested day-by-day over the full period:
  1. Fixed €10/day regardless of price movement.
  2. Asymmetric investing — €7 on up days, €15 on down days (buy more when price drops).
  3. Proportional investing — invest more aggressively the larger the previous day's price *drop*.
- Each simulation prints total euros invested vs. final portfolio value, letting you directly compare strategy outcomes on the same historical data.
- A bonus section runs the same fixed-DCA simulation across **all five coins** to compare which one would have performed best.
---
 
## Denoising Signals
📁 `denoisingSignals/`
 
**Concept.** Real-world signals are rarely clean — denoising techniques recover the underlying signal from noisy measurements, a core skill in DSP, biomedical engineering, and instrumentation.
 
**What's inside.**
- **Running-mean (boxcar) filter**: smooths a synthetic multi-component cosine signal by averaging each point with its neighbors within a window `k`, then explores how filter performance (correlation with the true signal) changes across a range of window sizes.
- **Gaussian convolution smoothing**: builds a Gaussian kernel by hand and convolves it with a noisy signal (`np.convolve`), then systematically sweeps kernel width and standard deviation together, visualizing the resulting sum-of-squared-error surface as a heatmap to find the best combination.
- **Median filtering (despeckling)**: adds sharp spike noise to a signal, uses a histogram to find a sensible outlier threshold, then replaces only the points above threshold with a local median — demonstrating why median filters (versus mean filters) are the right tool for impulsive/spike noise.
- **Real biomedical data**: loads an actual EKG signal CSV (noisy vs. original), and applies both median and mean filters to see how each performs on real physiological data.
- A bonus section covers a practical Matplotlib technique: **highlighting regions on a plot** using `fill_between` and `Polygon` patches, including shading the area between two time series.
---
 
## Descriptive Statistics Without NumPy
📁 `descriptivesWithoutNumpy/`
 
**Concept.** Reimplements the standard descriptive statistics — mean, median, mode, standard deviation — using only core Python, to build a from-first-principles understanding of what these functions are actually computing under the hood (verified at each step against NumPy/SciPy's built-ins).
 
**What's inside.**
- **Mean**: implemented as `sum(data)/len(data)` and checked against `np.mean`.
- **Median**: implemented with manual sorting and even/odd-length handling, checked against `np.median`.
- **Frequency table**: builds a dictionary of unique values and their counts from scratch (a manual `Counter`), used as the basis for computing the mode.
- **Mode**: found two ways — a manual loop tracking the max count, and a one-line dictionary comprehension — then checked against `scipy.stats.mode`.
- **Standard deviation**: implemented from its definition (sum of squared deviations from the mean, divided by N−1, square-rooted), checked against `np.std`.
- A bonus section wraps each statistic into a reusable function and writes a **CSV report** of computed statistics to disk.
---
 
## Entropy of English
📁 `entropyEnglish/`
 
**Concept.** Applies Claude Shannon's information theory to natural language — measuring how "predictable" English text is at the level of individual letters and letter-to-letter transitions.
 
**What's inside.**
- **Live text scraping**: pulls a full book's text directly from Project Gutenberg via `requests`, then cleans it with regular expressions (removing line breaks, curly quotes, and other encoding artifacts).
- **Word length distribution**: computes and histograms the length of every word in the text.
- **Letter frequency analysis**: counts occurrences of each letter a–z across the entire text and visualizes the distribution as a bar chart, then normalizes it into a probability distribution.
- **Letter entropy**: computes Shannon entropy (`-Σ p·log₂(p)`) over the letter probability distribution — a single number (in bits) quantifying how uncertain/informative the letter distribution is.
- **Conditional (lag-1) entropy**: builds a full letter → next-letter transition probability matrix (visualized as a 26×26 heatmap) and computes the *conditional* entropy of each letter given the one before it — showing that English becomes far more predictable once you know the preceding letter (e.g. "q" is almost always followed by "u").
- A bonus section generates a **word cloud** from the same text using the `wordcloud` library.
---
 
Each folder is self-contained and can be explored independently.
 
https://github.com/jpstayfocus/scientific-projects-py
