---
marp: true
paginate: true
---
<style>
:root {
  font-family: 'Noto Sans JP';    
  color: #444;
}
:root ol {
  list-style-type: decimal;
}
:root h1, h2, h3, h4, h5, h6{
  font-family: 'Noto Sans JP Black';
  color: #2277cc;
}
pre, code {
  font-family: 'Roboto mono', 'Noto Sans JP';
  line-height: 1.5;
}
</style>

# Workshop 07:<br>TOP Basics and Image Processing

---

## Review of Last Time

Last time, we created a simple program to "rotate a banana". Let's review by actually patching.

![height:360](https://i.ytimg.com/vi/1gxN1-dUfyw/maxresdefault.jpg)

- [【Introduction to TouchDesigner】Let's rotate Banana in 10min ! #00](https://youtu.be/1gxN1-dUfyw?si=BTAGPEDhAIexO7zQ)

---

## Completed Example

![height:480](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-163741.png)

- [Download](https://github.com/tado/tdexamples/blob/main/01-01_rotateBanana01.toe)

---

## Further Development!

![height:360](https://i.ytimg.com/vi/lWGknmeueMA/maxresdefault.jpg)

- [【 TouchDesigner Beginner Course 】Basic Operations and Basic TOPs #01](https://youtu.be/lWGknmeueMA?si=T3v4-pCUgCAS07jG)

---

### Final Image

![height:480](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/04/image-7.png?resize=1536%2C1034&ssl=1)

- [Download](https://github.com/tado/tdexamples/blob/main/01-02_rotateBanana02.toe)

---   

## Image Processing with TOPs

Learn the basic operations of image processing and switching using TOPs.

---

### TOPs for Image Processing

There are many operators available for image processing based on the input of TOPs.

- Edge TOP: Edge detection
- Blur TOP: Blur
- Bloom TOP: Glowing effect
- Level TOP: Level correction
- Emboss TOP: Embossed effect

...and so on. Let's actually try them.

---

### Switching TOPs

Let's try using an operator for switching TOPs so that we can switch and see the results of various image processing.

- Switch TOP: Switches between multiple TOPs

---

### Feedback Effect

- Feedback TOP: A TOP for creating a feedback effect

The connection is a bit difficult, but this is a TOP for creating a feedback effect. I will explain while actually creating it.

### Tiling

- Tile TOP: A TOP for tiling

This is a TOP that can arrange TOPs in a tile shape. I will explain while actually creating it.

---

### Program Example Using Basic TOPs

![height:480](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-164929.png)

- [Download](https://github.com/tado/tdexamples/blob/main/01-03_imageProcessing.toe)

---

### Program Example Using Basic TOPs 02

I tried to make it change more drastically!

![height:400](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-165130.png)

- [Download](https://github.com/tado/tdexamples/blob/main/01-04_imageProcessing02.toe)

---

## Today's Assignment

---

### Assignment: Let's play with noise!

---

Using the Noise TOP, which can easily generate noise from two to four dimensions, try to create your own "work" through trial and error. You can download the prototype program from the link below.

![height:400px](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-052805-scaled.png)
- [Noise Basic Sample](https://github.com/tado/tdexamples/blob/main/02-01_noiseBasic.toe)

---

Although you have just learned the basics of operation, let's first get a feel for the basic operations through trial and error. Then, try to make the following improvements.

---

**References**

- [Perlin noise (wikipedia)](https://en.wikipedia.org/wiki/Perlin_noise)
- [The Book of Shaders by Patricio Gonzalez Vivo & Jen Lowe](https://thebookofshaders.com/11/)

---

#### Basic: Try changing the parameters of the used operators

- [Noise TOP](https://docs.derivative.ca/index.php?title=Noise_TOP) (noise1)
  - Fineness of the noise
  - Complexity of the noise
  - Type of noise
  - ...etc.
- [LFO CHOP](https://docs.derivative.ca/index.php?title=LFO_CHOP) (lfo1)
  - Speed of change
  - Type of waveform for the change
  - ...etc.

---

- [HSV Adjust TOP](https://docs.derivative.ca/index.php?title=HSV_Adjust_TOP) (hsvadj1)
  - Try changing the hue
  - Try changing the saturation
  - Try changing the brightness
  - ...etc.

---  

#### Advanced: Try adding operators

- What happens if you connect a Noise TOP to a Noise TOP?
- Try adding another TOP before or after the HSV Adjust TOP.
- Try adding an LFO CHOP and referencing it to other parameters.
- ...etc.

---

### Noise Work Example 1

- Noise + Noise, added Bloom effect

![height:420](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-060944-scaled.jpg)
- [Download](https://github.com/tado/tdexamples/blob/main/02-02_noiseAdvanced01.toe)

---

### Noise Work Example 2

- Generate a kaleidoscope-like pattern

![height:420](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-055046-scaled.jpg)
- [Download](https://github.com/tado/tdexamples/blob/main/02-03_noiseAdvanced02.toe)

---

## Practice!

- Let's create a work using noise!
- We will have a presentation of the works in the last 40 minutes of the lecture.

---

## Survey

- [https://forms.gle/f7LSBuvns7p2TeXXA](https://forms.gle/f7LSBuvns7p2TeXXA)

![height:480](https://qr.quel.jp/tmp/87b643f543239276bb00924507648d657f9bdb17.png)
