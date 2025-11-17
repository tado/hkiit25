# TouchDesigner Practice 3 – Audiovisual, Sound Visualization

June 5, 2025

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-175824.jpg?resize=1024%2C576&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-175824-scaled.jpg?ssl=1)

Audiovisual refers to a general term for media and technology that combines sound (Audio) and visuals (Visual).

In the context of media art, it signifies an art form that doesn't merely handle sound and visuals simultaneously, but rather creates a unified perceptual experience by tightly linking the two. Its roots lie in attempts to explore the relationship between abstract art with movement, such as kinetic abstract art, and the temporal and structural elements of music and sound.

It encompasses a wide range of forms, including art installations experienced throughout a space, real-time performances, and meticulously designed video works. The interaction between sound and visuals, where the rhythm of sound controls visual movement or visual changes generate new sounds, deeply engages the viewer's senses.

This time, we aim to realize such audiovisual expressions using TouchDesigner.

## Audiovisual Reference Works

- [Synchromy Norman McLaren (1971)](https://www.youtube.com/embed/_UA40sL06sU?feature=oembed)
- [ALVA NOTO - UNIE-QAV #10 UNI EDIT](https://www.youtube.com/embed/27hiBK_c3Oc?feature=oembed)
- [Ryoji Ikeda - Live in London, 2023.11.8](https://www.youtube.com/embed/RK6WnfWWnec?feature=oembed)
- [New Rituals 2022 at Barbican Centre feat Ryoichi Kurokawa and Nkisi (Trailer)](https://www.youtube.com/embed/h99HUWoVyWE?feature=oembed)

## What is a Sound Wave?

What exactly is a sound wave, or sound itself?

[Understanding Sound Waves | MED-EL](https://www.youtube.com/embed/XLfQpv2ZRPU?feature=oembed)

## Waveform Analysis – Basics 1: Playing Sound Files and Displaying Waveforms

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-151821.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-151821.jpg?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-01_SoundWave.toe)

Key points:

- In TouchDesigner, sound is treated as a series of numerical values, so CHOPs are used for sound data.
- Use the Audio File In CHOP to load sound files.
- Sound will not play just by loading; connect it to an Audio Device Out CHOP to play.
- Connecting a CHOP containing sound wave data to a CHOP to TOP allows for visual representation of the sound.

## Waveform Analysis – Basics 2: Visualizing Sound Volume

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-121402.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-121402.jpg?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-02_WaveCircles.toe)

Key points:

- Sound obtained with Audio File In CHOP stores sound within a certain range (buffering).
- To use the sound data stored in a CHOP as a numerical value, it needs to be converted into a single numerical value using an Analyze CHOP.
- Analyze CHOP offers various analysis methods:
  - Value of First Peak: The first value in the buffer.
  - Average: The average of all values in the buffer.
  - Maximum: The maximum value.
  - Minimum: The minimum value.
  - Sum: The sum of all values.
  - RMS Power: Root Mean Square.
- RMS Power is suitable for visualization.
- Once numerical, it can be applied to various parameters of shapes, etc.
- Lag CHOP: Smoothly interpolates numerical changes, suppressing sudden peak changes.
- Filter CHOP: Smooths overall changes further (low-pass filter).

## Waveform Analysis – Basics 3: Utilizing Filters, Visualizing by Frequency Band

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-124458.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-124458.jpg?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-03_AudioFilters.toe)

Key points:

- By using audio filters, components of the waveform can be extracted by frequency band.
- Various types of filters exist:
  - Low-pass filter (LPF): Passes low frequencies, cuts high frequencies.
  - High-pass filter (HPF): Passes high frequencies, cuts low frequencies.
  - Band-pass filter (BPF): Passes a specific frequency range.
- Using filters, the original sound is decomposed into low, mid, and high frequencies.
- Each is analyzed with Analyze CHOP's RMS Power and visualized.
- Changes in musical components (bass drum, hi-hat, etc.) can be observed.

<img width="640" alt="img" src="https://i0.wp.com/www.allaboutcircuits.com/uploads/articles/Types_of_Filters.jpg?ssl=1">Various filter types: Low-pass (LPF), High-pass (HPF), Band-pass (BPF), Band-stop

## Waveform Analysis – Basics 4: Using the Audio Analysis COMP

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041639.jpg?resize=1024%2C499&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041639.jpg?ssl=1)

- To use the function that analyzes sound waveforms by frequency and smoothly adjusts the values more conveniently and easily.
- A dedicated COMP is available → Audio Analysis COMP.
- Drag & drop from Palette > Tools > AudioAnalysis.
- Very high performance and easy to use!
- The same functionality as previous programs can be implemented cleanly and simply.

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-043259.jpg?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-043259.jpg?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-04_AudioAnalysis.toe)

Key points:

- The part that was manually analyzed is replaced with the Audio Analysis COMP.
- Adjust parameters as needed to refine the values.

## Waveform Analysis – Application 1: Visualizing Frequency Bands in 3D

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041716.png?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041716.png?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-05_AudioFilters3D.toe)

- The 2D circles (Circle TOP) previously used for visualization are now in 3D.
- In this example, a sphere (Sphere SOP) deformed by noise is colored with translucent colors and transformed.
- Various visualizations are possible with different ideas!
- Let's apply what we've learned in previous lectures!

## From Waveform Analysis to Frequency Analysis

Why is frequency analysis necessary?

- FFT (Fast Fourier Transform): Decomposes sound into frequency components → Why is this operation necessary in the first place?
- Consider how the ear hears sound.

[Sound Stimulates the Cochlea | MED-EL](https://www.youtube.com/embed/wkHPXHB3OxQ?feature=oembed)

[Hearing, Ear Anatomy & Auditory Transduction](https://www.youtube.com/embed/sSgZXrdlIlM?feature=oembed)

In other words, we hear sound by decomposing it into frequency components!

<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/cochlea.png?resize=688%2C484&ssl=1">Citation: [Hearing, the cochlea, the frequency domain and Fourier’s series](https://uncommondescent.com/video/hearing-the-cochlea-the-frequency-domain-and-fouriers-series/)

### FFT and IFFT

- FFT (Fast Fourier Transform): Waveform to frequency components.
- IFFT (Inverse Fast Fourier Transform): Frequency components to waveform.

<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Convolution_FFT_and_IFFT.jpg?resize=1251%2C412&ssl=1">

### STFT (Short-Time Fourier Transform)

In actual analysis, the signal is cut into fixed time segments and analyzed.

- Time to cut the signal → FFT Length (number of samples, power of 2)
- Windowing function

A plot of this FFT analysis result is a Spectrogram.

<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Spectrogram-19thC.png?resize=644%2C335&ssl=1">

Reference: [【視覚的に理解する】フーリエ変換](https://www.youtube.com/embed/fGos3wrKeHY?feature=oembed) (Visually Understanding Fourier Transform)

## FFT Visualization Basics 1: Visualizing Spectrum with TOP

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-060137.png?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-060137.png?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-06_FFTBasic.toe)

Key points:

- Connect the signal obtained from Audio File In CHOP to Audio Spectrum CHOP.
- FFT analysis is performed.
- Various analysis parameters can be set:
  - FFT Size (number of samples for STFT division)
  - Scale setting (linear scale to log scale)
  - High-frequency emphasis
- The analysis result is converted to a texture with CHOP to TOP.
- Frequency components appear as stripe patterns.

## FFT Visualization Basics 2: Coloring Symmetrically

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-173929.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-173929.jpg?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-07_FFTVisStripe.toe)

- Gradient coloring based on frequency components (multiplying with Ramp TOP).
- Left and right channels are arranged symmetrically.
- Low frequencies are at the center, high frequencies are at the left and right edges.

## FFT Visualization Basics 3: Converting to a Circle

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-062212.jpg?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-062212.jpg?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-08_FFTVisCircle.toe)

Key points:

- Cartesian To Polar COMP: A COMP that transforms from Cartesian coordinates to polar coordinates.
- It is possible to convert the stripe-like spectrum pattern into a circular shape.
- The left and right sounds are represented as a circular pattern.

## Various Assortments

I've put together a set of various assortments!

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2024/06/Screenshot-2024-06-07-055236.png?resize=1024%2C563&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/06/Screenshot-2024-06-07-055236.png?ssl=1)

[Download](https://github.com/tado/tdexamples/blob/main/08-09_audioVisualFFT.toe)

## Questionnaire

Today's questionnaire:

- [Questionnaire](https://forms.gle/He9o6Q76SrJRZPDD8)
