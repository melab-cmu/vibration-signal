# vibration-signal
Harmonic oscillator vibration datasets and signal digitization analysis for digital twins

## Data Access
All vibration datasets are stored as CSV files and accessed via public
GitHub RAW URLs to ensure environment-agnostic execution and full
reproducibility across local machines, Jupyter notebooks, and cloud
runtimes.

---> ## Requirements
        - Python 3.9+
        - pandas
        - numpy
        - scipy


## Analysis Notebook
The primary analysis is contained in:
<sub> `analysis/vibration-signal.ipynb` </sub>

Open `analysis/vibration-signal.ipynb` to view results. 
Data loads via public GitHub RAW URLs—no local setup required.

## Sampling Rate
<sub> _Derived from Module 2.3: Sampling as discretization of time Aliasing discussion (difference between signal frequency and sampling rate)_ </sub>

Sampling rate determines whether the digital signal can faithfully represent the physical oscillator. This follows directly from Nyquist logic: insufficient sampling introduces aliasing and false dynamics.

Sampling rate is computed as the inverse of the average time difference between consecutive samples.


## Frequency of Oscillator Response
<sub> _Derived from Module 2.1: Physical phenomenon → measurable signal and Module 2.3: Time-domain vs frequency-domain interpretation_ </sub>

The oscillator’s response frequency reveals the system’s dynamic behavior and resonance characteristics, which is fundamental to vibration analysis and digital twin calibration.

Estimate frequency using either:

- Peak-to-peak time spacing in the time domain, or
- Dominant frequency via FFT in the frequency domain.


## Amplitude of Oscillator Response
<sub> _Derived from Module 2.2: Sensor range and dynamic limits and Module 2.3: Quantization magnitude discretization_ </sub>

Amplitude reflects system energy and directly impacts ADC resolution, saturation risk, and signal-to-noise ratio.
Compute peak amplitude as:

A=max⁡(x)−min⁡(x) / 2


## ADC Input Range
<sub> _Derived from Module 2.2: Sensor conditioning and range matching and Module 2.3: ADC window vs signal amplitude analogy_ </sub>

The ADC must accommodate the full signal swing without clipping while maximizing resolution.
The required ADC input range is:

[min⁡(x),max⁡(x)]

Optionally expanded with a safety margin (e.g., ±10%).

