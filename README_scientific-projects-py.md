# Scientific Projects in Python

A portfolio of hands-on notebooks exploring scientific computing, applied mathematics, probability, statistics, machine learning, signal processing, computational neuroscience, and scientific visualization.

The notebooks emphasize learning through implementation: simulating data, deriving or coding algorithms, testing scientific ideas, and visualizing the results with Python.

<p align="center">
  <img src="animations/MobiusTransformAnimation.gif" alt="Animated Möbius transformation" width="600">
</p>

## Project Areas

- [Probability and Statistics](#probability-and-statistics)
- [Applied Mathematics and Optimization](#applied-mathematics-and-optimization)
- [Machine Learning and Data Analysis](#machine-learning-and-data-analysis)
- [Signal Processing](#signal-processing)
- [Dynamical Systems and Neuroscience](#dynamical-systems-and-neuroscience)
- [Scientific Visualization and Python Practice](#scientific-visualization-and-python-practice)

---

## Probability and Statistics

### [Law of Large Numbers](LawLargeNumbers/MasPy_LawLargeNumbers.ipynb)

Uses Monte Carlo sampling and cumulative averaging to demonstrate how sample estimates converge toward a population mean.

**Topics:** random populations, repeated sampling, Monte Carlo simulation, statistical convergence

### [Statistics](statistics/MasPy_statistics.ipynb)

Applies inferential and predictive statistics to the UCI red-wine-quality dataset.

**Topics:** exploratory analysis, independent-samples t-test, multiple regression, logistic regression, Gaussian transformations

### [Descriptive Statistics Without NumPy](descriptivesWithoutNumpy/MasPy_descriptivesWithoutNumpy.ipynb)

Implements core descriptive statistics manually and compares the results with established library functions.

**Topics:** mean, median, frequency tables, mode, standard deviation, CSV reporting

### [Entropy of Written English](entropyEnglish/MasPy_EntropyEnglish.ipynb)

Analyzes public-domain English text through word-length distributions, letter frequencies, Shannon entropy, and conditional sequence entropy.

**Topics:** information theory, probability distributions, Shannon entropy, conditional entropy, text analysis, word clouds

---

## Applied Mathematics and Optimization

### [Data Curve Fitting](DataCurveFitting/MasPy_DataCurveFitting.ipynb)

Fits mathematical models to noisy data with `lmfit`, including built-in and user-defined models.

**Topics:** Gaussian fitting, exponential decay, sigmoid fitting, composite models, multivariate fitting, goodness of fit

### [Interpolation and Extrapolation](interpolationExtrapolation/MasPy_InterpExtrap.ipynb)

Explores resampling, interpolation, extrapolation, and the reconstruction of missing image data.

**Topics:** downsampling, upsampling, one-dimensional interpolation, extrapolation, image repair, geometric visualization

### [Local Minimum via Gradient Descent](localMinGradDescent/MasPy_localMinGradientDescent.ipynb)

Builds and visualizes gradient descent in one and two dimensions, including symbolic derivatives and optimization trajectories.

**Topics:** derivatives, learning rates, stopping criteria, local minima, two-dimensional optimization, 3D visualization

### [Awesome Math Stuff](awesomeMathStuff/MasPy_awesomeMathStuff.ipynb)

A collection of computational mathematics experiments and visualizations.

**Topics:** Pascal's triangle, Euler's identity, parameterized Gaussian functions, special-relativity time dilation, complex eigenvalues, mathematical art

---

## Machine Learning and Data Analysis

### [Clustering](clustering/MasPy_clustering.ipynb)

Processes atmospheric cloud data and combines dimensionality reduction with unsupervised learning to reveal structure in a high-dimensional dataset.

**Topics:** normalization, covariance matrices, principal component analysis, t-SNE, k-means clustering, density estimation

### [Exploring Cryptocurrency Investments](cryptoInvesting/MasPy_cryptoInvesting.ipynb)

Retrieves historical cryptocurrency prices, examines shared market structure, and simulates dollar-cost-averaging strategies.

**Topics:** time-series data, feature aggregation, PCA, correlation, investment simulation, dollar-cost averaging

---

## Signal Processing

### [Denoising Noisy Signals](denoisingSignals/MasPy_denoising.ipynb)

Compares several approaches for smoothing and repairing noisy synthetic and biomedical signals.

**Topics:** running-mean filtering, Gaussian convolution, median filtering, spike removal, EKG denoising, highlighted plot regions

### [The Colorful Rainbow of Noise](colorfulRainbowOfNoise/MasPy_colorNoise.ipynb)

Generates different noise colors and compares their time-domain, frequency-domain, and audio characteristics.

**Topics:** white noise, Brownian noise, pink noise, blue noise, Fourier spectra, audio generation

### [Spectral Analysis](spectralAnalysis/MasPy_spectralAnalysis.ipynb)

Studies the frequency content of an autoregressive signal using both manual and library-based spectral methods.

**Topics:** autoregressive processes, discrete Fourier transform, FFT, zero-padding, Welch's method, spectrograms

### [Time-Series Filtering](timeSeriesFiltering/MasPy_TimeSeriesFiltering.ipynb)

Designs and evaluates filters for noisy time-series data in both the time and frequency domains.

**Topics:** notch filtering, line-noise removal, FIR high-pass filters, IIR low-pass filters, filter response, spectral inspection

### [Time-Frequency Analysis of EEG Data](timeFrequencyAnalysis/MasPy_timeFreqEEG.ipynb)

Constructs Morlet wavelets and applies wavelet convolution to EEG data to create a time-frequency power map.

**Topics:** real and complex Morlet wavelets, wavelet families, FFT convolution, EEG analysis, time-frequency decomposition

---

## Dynamical Systems and Neuroscience

### [Simulate a Brain Circuit](simulateBrainCircuit/MasPy_simulateBrainCircuit.ipynb)

Implements an Izhikevich-style spiking-neuron model and scales it from one neuron to a mixed excitatory-inhibitory network.

**Topics:** computational neuroscience, membrane dynamics, spiking neurons, neural populations, excitation and inhibition, raster plots

### [State-Space Trajectories via PCA](stateSpaceTrajectories/MasPy_stateSpaceTrajectory.ipynb)

Uses neural population recordings and PCA to represent changing brain activity as low-dimensional trajectories through state space.

**Topics:** neural data cleaning, covariance matrices, PCA, dimensionality reduction, state-space visualization, temporal trajectories

---

## Scientific Visualization and Python Practice

### [Animate Data](animations/MasPy_animations.ipynb)

Creates mathematical animations with Plotly and Matplotlib.

**Topics:** complex Morlet wavelets, animated phase changes, Möbius transformations, prime-number visualization

### [Text Search and Replace](textSearchReplace/MasPy_TextReplace.ipynb)

Processes caption text by removing formatting, searching and replacing word patterns, writing cleaned output, and testing the readability of scrambled words.

**Topics:** file handling, regular expressions, string processing, text cleaning, word transformation

### [Sierpiński Triangle](sierpinski_triangle.ipynb)

Generates a Sierpiński triangle with the chaos game and a compact iterative implementation.

**Topics:** fractals, stochastic iteration, geometric visualization

---

## Technology

The notebooks use tools from the scientific Python ecosystem, including:

- Python and Jupyter Notebook
- NumPy and pandas
- SciPy and statsmodels
- Matplotlib, Plotly, and seaborn
- scikit-learn
- SymPy
- lmfit

## Running the Notebooks

Clone the repository and open it in JupyterLab or VS Code:

```bash
git clone https://github.com/jpstayfocus/scientific-projects-py.git
cd scientific-projects-py
python -m venv .venv
```

Activate the environment and install the libraries required by the notebook you want to run. Some notebooks download public datasets or use external data files. A few retain Google Colab upload cells and may need a small path adjustment when run locally.

## Notes

These notebooks are learning-focused scientific explorations. They are intended to demonstrate concepts, implementations, experimentation, and visualization rather than provide production-ready packages or financial, medical, or scientific advice.
