# Workshop 07: TOP Basics and Image Processing

## Review of Last Time

Last time, we created a simple program to "rotate a banana". We loaded a banana image with the Movie File In TOP, set up a rotation animation with the Transform TOP, and combined it with a circle created with the Circle TOP using the Over TOP. Let's review the basic operations by actually patching (connecting operators).

<img src="https://i.ytimg.com/vi/1gxN1-dUfyw/maxresdefault.jpg" width="640" />

[【Introduction to TouchDesigner】Let's rotate Banana in 10min ! #00](https://youtu.be/1gxN1-dUfyw?si=BTAGPEDhAIexO7zQ)

Let's recall the previous operations while watching this video.

## Completed Example

This is a completed example that expands on the previous content. In addition to the basic rotation, backgrounds and other elements have been added.

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-163741.png" width="640" />

- [Download](https://github.com/tado/tdexamples/blob/main/01-01_rotateBanana01.toe)
  Download the completed example file (.toe) and open it in TouchDesigner. You can check the contents to see how it was made.

## Further Development!

Based on the "rotating banana" created in the previous review, we will further enrich the expression by adding image processing using TOPs. Let's try using various TOP operators with reference to the contents explained in the following video.

<img src="https://i.ytimg.com/vi/lWGknmeueMA/maxresdefault.jpg" width="640" />

[【 TouchDesigner Beginner Course 】Basic Operations and Basic TOPs #01](https://youtu.be/lWGknmeueMA?si=T3v4-pCUgCAS07jG)

This video explains the types of basic TOP operators, how to connect them, and how to adjust their parameters.

### Final Image

This is the final image of the developed version. You can see that various effects have been added.

<img src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/04/image-7.png?resize=1536%2C1034&ssl=1" width="640" />

[Download](https://github.com/tado/tdexamples/blob/main/01-02_rotateBanana02.toe)
  
Download this as well and check what kind of operators are connected and how.

## Image Processing with TOPs

From here, we will learn in detail about image processing using TOPs, which is the main theme of this lecture. TOP is an abbreviation for Texture Operators, and it is a group of operators for handling and processing images and videos in TouchDesigner.

### TOPs for Image Processing

TouchDesigner has a wealth of TOPs for adding various effects to input images. Here are some typical ones.

- Edge TOP: Detects the edges of an image. It is useful for creating illustration-like expressions and for extracting specific shapes.
- Blur TOP: Adds a blur effect to an image. You can adjust the strength and direction of the blur.
- Bloom TOP: Makes the bright parts of an image bleed, creating a glowing effect (bloom effect). It is suitable for fantastic expressions.
- Level TOP: Adjusts the brightness, contrast, gamma, etc. of an image. It is a basic operator for color correction.
- Emboss TOP: Adds an embossed, relief-like effect to an image.

These TOPs can be created from the TOP tab of the operator palette (displayed with the Tab key). Connect a TOP that has image data to the input (the connection point on the left) and adjust the effect in the parameter window. Let's actually try a few and see what kind of effects can be obtained.

### Switching TOPs

You may want to switch between multiple images or the results of different image processing depending on the situation. In such cases, use the Switch TOP.

- Switch TOP: Receives multiple TOP inputs and outputs only one specified input. You can switch which input to select by changing the "Index" parameter. For example, it is used when comparing the results of different effects or switching the video to be displayed according to the interaction.

### Feedback Effect

There is also a dedicated TOP for creating the "feedback" effect often used in video expression.

- Feedback TOP: By using the output result of the previous frame (a very short time ago) in the processing of the current frame, it creates effects such as afterimages and infinitely continuing images.
   Connection point: The connection of the Feedback TOP is a little special. Usually, you place the Feedback TOP at the end of the processing loop, and then drag and drop that Feedback TOP to the beginning of the loop (the input you want to feed back) to reference it. It is common to put a Level TOP or the like in the loop to adjust the strength of the feedback (such as transparency) or to combine it with the original image with an Add TOP or Over TOP.
   Let's experience this slightly complicated connection method and the unique expressions it creates while actually creating it.

### Tiling

If you want to create a pattern by arranging images in a tile shape, use the Tile TOP.

- Tile TOP: Lays out the input image in a tile shape. You can finely set the arrangement method (repeat, flip, rotate, etc.) and the number of tiles with parameters. It is useful for creating kaleidoscope-like expressions and texture patterns.

### Program Example Using Basic TOPs

This is a sample program created by combining the TOP operators introduced so far (Edge, Blur, Level, Switch, Feedback, Tile, etc.).

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-164929.png" width="640" />

[Download](https://github.com/tado/tdexamples/blob/main/01-03_imageProcessing.toe)
  
Download it and check how each operator works together to create the final video.

### Program Example Using Basic TOPs 02

This is an example with more complex and dynamic changes made by further adjusting the parameters and adding other TOPs.

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-165130.png" width="640" />

[Download](https://github.com/tado/tdexamples/blob/main/01-04_imageProcessing02.toe)

Experience how a small change can greatly change the expression.

## Today's Assignment

### Assignment: Let's play with noise!

In this assignment, you will freely experiment with expression using the Noise TOP. The Noise TOP is a very powerful operator that can generate various types of noise (random and organic patterns) by program. Just by adjusting the parameters, you can create a wide variety of textures and animations like clouds, water surfaces, flames, and terrain.

First, download the basic sample program below and try to create your own "noise work" by modifying it.

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-052805-scaled.png" width="640" />

[Noise Basic Sample](https://github.com/tado/tdexamples/blob/main/02-01_noiseBasic.toe)

To get used to operating TouchDesigner, it is important to try various things anyway. Don't think too hard, let's start by touching the parameters and observing the changes. Then, try to experiment with the following points in mind.

References

These materials will help you deepen your understanding of noise, especially the Perlin noise algorithm used in the Noise TOP.

- [Perlin noise (wikipedia)](https://en.wikipedia.org/wiki/Perlin_noise)
- [The Book of Shaders by Patricio Gonzalez Vivo & Jen Lowe](https://thebookofshaders.com/11/) (Chapter 11: Noise section is particularly helpful)

#### Basic: Try changing the parameters of the used operators

Let's try changing various parameters of the main operators used in the sample program.

- [Noise TOP](https://docs.derivative.ca/index.php?title=Noise_TOP) (noise1): This is the central operator of this network.
  - Period: Adjusts the fineness and scale of the noise. The smaller the value, the finer the noise.
  - Harmonics: Adjusts the complexity of the noise. A larger value results in a more detailed and complex pattern.
  - Type: Selects the algorithm for generating noise. The appearance changes greatly depending on the type, such as Perlin, Simplex, Random, etc. Let's try various things.
  - Transform tab's Translate/Rotate/Scale: You can move the noise over time (by putting an expression like `absTime.seconds` in Translate Z), rotate it, or scale it.
  - ...and there are many other parameters. Let's touch the ones that interest you.

- [LFO CHOP](https://docs.derivative.ca/index.php?title=LFO_CHOP) (lfo1): A CHOP (Channel Operator) that generates a periodic value (waveform) over time. This value is used to move the parameters of other operators.
  - Frequency: Adjusts the speed at which the value changes. The larger the value, the faster it changes.
  - Type: Selects the change pattern of the value, such as Sine, Triangle, Square, etc.
  - Amplitude: Adjusts the range (magnitude) of the value change.
  - ...etc. You can use this LFO CHOP's output by exporting (drag and drop) it to a Noise TOP parameter (e.g., Amplitude) to change the brightness of the noise over time.

- [HSV Adjust TOP](https://docs.derivative.ca/index.php?title=HSV_Adjust_TOP) (hsvadj1): A TOP that changes the color of an image by adjusting the Hue, Saturation, and Value/Brightness.
  - Hue Offset: Shifts the overall hue. Changing the value makes the colors cycle.
  - Saturation Multiplier: Adjusts the saturation. Setting it to 0 results in grayscale.
  - Value Multiplier: Adjusts the brightness.
  - ...etc. You can use it to add color to the monochrome noise generated by the Noise TOP, or to change the color over time.

#### Advanced: Try adding operators

Once you get used to the basic operations, let's try adding new operators to challenge more complex expressions.

- Connect a Noise TOP to a Noise TOP: Connecting the output of a Noise TOP to the second input (Noise Coordinate Map) of another Noise TOP can create a very interesting effect, such as distorting one noise pattern with another.
- Add another TOP before or after the HSV Adjust TOP: For example, try layering effects by inserting a Blur TOP between the Noise TOP and the HSV Adjust TOP to blur the noise, adding a Bloom TOP after the HSV Adjust TOP to make it glow, or extracting the edges with an Edge TOP before coloring.
- Add an LFO CHOP and reference it to other parameters: Create a new LFO CHOP and export its value to the rotation parameter of the Noise TOP or the hue parameter of the HSV Adjust TOP to create more complex animations.
- ...etc. Try connecting operators with a free mind. You might make an unexpected discovery.

### Noise Work Example 1

- Contents: An example where two Noise TOPs are layered (one for pattern generation, the other for distortion), and a glowing effect is added with a Bloom TOP.

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-060944-scaled.jpg" width="640" />

[Download](https://github.com/tado/tdexamples/blob/main/02-02_noiseAdvanced01.toe)

### Noise Work Example 2

- Contents: An example where a kaleidoscope-like repeating pattern is generated by combining a Noise TOP with a Tile TOP. Color changes are also added.

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-055046-scaled.jpg" width="640" />

[Download](https://github.com/tado/tdexamples/blob/main/02-03_noiseAdvanced02.toe)

## Practice!

Now, let's actually use the Noise TOP to create your own original work!
Start by modifying the basic sample, and once you get used to it, feel free to add and connect operators.

- Goal: To try to create interesting or beautiful visual expressions by combining the various TOPs (Blur, Level, Bloom, Feedback, Tile, HSV Adjust, etc.) and CHOPs (LFO, etc.) you have learned, centered on the Noise TOP.
- Time: The next XX minutes (time will be specified by the teacher) will be production time.
- Presentation: In the last 40 minutes or so of the lecture, everyone will present the work they have created. It doesn't have to be complete, so let's share what kind of trial and error you did and what you found interesting.

If you have any questions, please don't hesitate to ask. Enjoy the trial and error!
