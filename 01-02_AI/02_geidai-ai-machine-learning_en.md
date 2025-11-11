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

# Artificial Intelligence and Creation<br>Artificial Intelligence, Machine Learning, Deep Learning, Generative AI<br>Experience Machine Learning with Teachable Machine

Tokyo University of the Arts Arts and Media Center (AMC)
Atsushi Tadokoro

---

In today's lecture, we will first define and explain the characteristics of Artificial Intelligence (AI), Machine Learning (ML), Deep Learning (DL), and Generative AI (GenAI). Then, we will gain basic hands-on experience in machine learning using Teachable Machine—training a model and experiencing the image classification flow. We will also touch on how transfer learning works and why high accuracy can be achieved with only a small number of samples. Finally, we will highlight the Transformer model—the essence of modern generative AI—and connect to the next session.

---

## Today's topics

1. Explanation of last week's assignment
    - AI, ML, DL, Generative AI: definitions and meanings
    - What is GPT?
2. Understanding machine learning
    - Experience machine learning with Teachable Machine!
3. Approaching the core of generative AI: Transformer
    - 30-year history from neural computing to GPT

---

## Understanding basic generative AI terminology

- Definitions of four terms
  - Artificial Intelligence (**AI**)
  - Machine Learning (**ML**)
  - Deep Learning (**DL**)
  - Generative AI (**GenAI**)
- About GPT
  - What is **GPT**?
  - Meaning of the letters "G", "T", "P"

---

### Definitions and meanings of "Artificial Intelligence," "Machine Learning," "Deep Learning," and "Generative AI"

Watch the video
 [Introduction to Generative AI](https://youtu.be/u3FQgoKEnZk?si=1ieVJ3BkRkKk38_d)

![height:480](https://cdn.qwiklabs.com/HyEv3IhvJjUIzSRJd%2Fzb3H0ub26FvSfo4M7EFDiEaEc%3D)

---

Key points:

- Definitions of AI, ML, DL, Gen AI
- About learning (supervised vs unsupervised)
- Deep learning and deep neural networks
- Generative AI is part of deep learning
- Generative vs discriminative models
- Large Language Models: PaLM, LaMDA, etc.
- Importance of Transformer models
- Text-to-Text, Text-to-Image, Text-to-Video and other generative model types

---

### Reference material

- [Homo Codens YCAM workshop materials](https://drive.google.com/file/d/12pEk1u70nlxPRBtK-X122PnznMlCOc7K/view)

---

## Light and dark sides of generative AI – Problems inherent in datasets

We will watch two video resources.

---

### How This Guy Uses A.I. to Create Art | Obsessed | WIRED

[https://www.youtube.com/watch?v=I-EIVlHvHRM](https://www.youtube.com/watch?v=I-EIVlHvHRM)

![height:480](https://i.ytimg.com/vi/I-EIVlHvHRM/maxresdefault.jpg)

---

### AI Art: How artists are using and confronting machine learning | HOW TO SEE LIKE A MACHINE

[https://youtu.be/G2XdZIC3AM8](https://youtu.be/G2XdZIC3AM8)

![height:480](https://i.ytimg.com/vi/G2XdZIC3AM8/maxresdefault.jpg)

---

## References

---

[Refik Anadol, Unsupervised — Machine Hallucinations — MoMA (2023)](https://refikanadol.com/works/unsupervised/)

![height:480](https://idsb.tmgrup.com.tr/ly/uploads/images/2023/10/11/296134.jpg)

---

[KATE Crawford, Trevor Paglen, Training Humans](https://paglen.studio/2020/04/09/kate-crawford-trevor-paglen-training-humans/)

[https://youtu.be/P4JpD1PWBDI](https://youtu.be/P4JpD1PWBDI)

![height:480](https://paglen.studio/wp-content/uploads/2020/05/PaglenCrawford-Training_Humans-2019_02.jpg)

---

[Trevor Paglen, Behold these Glorious Times! (2020)](https://paglen.studio/2020/04/09/behold-these-glorious-times/)

![height:480](https://paglen.studio/wp-content/uploads/2020/05/Paglen-Behold_2017.jpg)

---

[Kate Crawford, Vladan Joler, Anatomy of an AI System (2018)](https://anatomyof.ai/)

![height:480](https://framemark.vam.ac.uk/collections/2019MK0472/full/735,/0/default.jpg)

---

[Kate Crawford, Vladan Joler, Calculating Empires: A Genealogy of Power and Technology, 1500-2025](https://calculatingempires.net/)

![height:480](https://www.azuremagazine.com/wp-content/uploads/2023/11/Calculating_empires_1.jpg)

---

### Key points so far

- Generative AI technology is extremely powerful and full of potential for new expression
- However, various issues exist behind it
  - Data bias
  - Monopoly by large corporations
  - Massive energy consumption
  - Privacy concerns
  - Risk of copyright infringement
  - Fake news
  - AI black-boxing
  …etc.

---

- We do not completely reject generative AI
- Nor do we uncritically accept everything
- We want to enjoy its convenience while thinking critically about its problems and structure
- To do so, we need an accurate mental model of the technology (!= magic)

---

## Experience machine learning with Teachable Machine

![height:460](https://teachablemachine.withgoogle.com/assets/img/contentpage/home/2017-version.jpg)
[Teachable Machine](https://teachablemachine.withgoogle.com/)

---

- Before tackling full-fledged generative AI, learn the basics of machine learning
- Experience the basic flow of supervised learning (transfer learning)
- Load images → Label them → Train → Classify (discriminate)
- Try various images and feel how it works!

---

### Practical: Machine learning with Teachable Machine

First, try training

- Create a new Image project in Teachable Machine
- Capture image sets for several classes with a webcam
- Press "Train Model" to start training
- Check in Preview; if poor, redo image capture

Start with "Image Project"—it's easiest. Try various ideas for what sets of images to train!

---

### Exporting the trained model

Teachable Machine allows exporting trained models for use in programs. It easily generates sample source code for multiple environments.

Supported environments

- Tensorflow
- Tensorflow Lite
- Tensorflow.js
- p5.js + ml5.js ← We'll use this

---

### Steps to export the trained model

- Create a new Image project in Teachable Machine
- Capture image sets for several classes with a webcam
- Press "Train Model" to start training
- Check in Preview; if poor, redo image capture
- If okay, press "Export Model"
- Choose Tensorflow.js > Upload (shareable link) > p5.js and click "Upload my model"

---

Export settings

![height:500](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-20-175918.png?ssl=1)

---

### Loading the trained model in p5.js

- Log in to [p5.js Editor](https://editor.p5js.org/にログイン)
- Open the [p5.js sample project](https://editor.p5js.org/tadokoro/sketches/q6-kSu1XI)
- Duplicate the file into your own project
- Replace the model URL with your own trained model

---

Apply your uploaded model URL

```javascript
... (omitted earlier) ...

// URL of your trained & uploaded model
// !! Paste your model URL here !!
let imageModelURL = 'https://teachablemachine.withgoogle.com/models/8dyZwOgL4/';

... (omitted later)...
```

---

Result

![height:500](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-21-143806.png?ssl=1)

---

Key point! Understand where classification happens in the sample code

Important functions:

```javascript
// Classify the current video frame
function classifyVideo() {
  classifier.classify(flippedVideo, gotResult);
}

// When result is obtained
function gotResult(results) {
  // Results are in an array ordered by confidence
  // console.log(results[0]);
  label = results[0].label;
}
```

---

Important: the ``results[]`` array

- Analyzed image results are stored in order of descending confidence (probability of being that class)
- You can retrieve label (label) and confidence (confidence)
- For example, to get the label and confidence of the top result:

```javascript
let label = result[0].label; // label
let confidence = result[0].confidence; // confidence
```
---

### Display list of classification labels (strings) and confidences (0.0 – 1.0)

Sample displaying labels and confidence values

- Open in [p5.js editor](https://editor.p5js.org/tadokoro/sketches/48A-8X9Sj)
- [sketch.js](https://github.com/tado/TeachableMachineExample/blob/main/01_ShowResults/sketch.js)

---

Result

![height:500](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-21-143535.png?ssl=1)

---
### Emoji Cam

Add a small idea. A sample that shows emojis depending on facial expressions. In this example: normal face, smile, sad (3 classes).

- Open in [p5.js Editor](https://editor.p5js.org/tadokoro/sketches/eITOgMhp7)
- [sketch.js](https://github.com/tado/TeachableMachineExample/blob/main/02_EmojiCam/sketch.js)

---

Result

![height:400](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-21-141527.png?ssl=1) ![height:400](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-21-141552.png?ssl=1)

---

### Why can classification work with few images?

- Image classification
- Normally requires enormous training data
- Image + label pairs

---

### Example of large image database: ImageNet

[ImageNet](https://www.image-net.org/)

![height:400](https://miro.medium.com/v2/resize:fit:1009/0*S4LF1ObkVh2ke-I-.jpeg)

- Large-scale image database designed for object recognition research
- As of Oct 2024, trained on 14,197,122 images

---

### Transfer Learning

- Principle allowing Teachable Machine to learn from few images
- Reusing a model trained on one task for a related new task
- Faster and simpler than training from scratch
- Shortens training time
- Mitigates lack of sample data

---

How transfer learning works

![height:480](https://www.techtarget.com/rms/onlineimages/how_transfer_learning_works-f.png)

---

### Practice: Play with Image Project

- Experiment with Teachable Machine Image Project
- What kinds of classifications could be interesting?
  - Train with various images
  - Draw illustrations and classify them
  - Learn gestures
  ..etc.

---

## Transfer Learning and Large Language Models (LLMs)

---

### What is a Large Language Model (LLM)?

- Language model pre-trained on massive text data (GPT, Gemini, etc.)
- An extraordinary quantity of data is pre-trained

![height:400](https://felloai.com/wp-content/uploads/2025/02/Expected-size-of-GPT-5-model-compared-to-GPT-4-and-GPT-3-1-1024x515.png)

---

### LLM: Far beyond a human lifetime of reading

- GPT-5 (estimate): about 114 trillion tokens
  - 1 token ≈ 4 characters → approx. 456 trillion characters
- Human: estimated to read 2,000 books in a lifetime
  - Assume 300 pages per book, 500 characters per page
  - 150,000 characters per book
  - Lifetime reading = 2,000 × 150,000 = 300 million characters
- 456 trillion ÷ 300 million = about 1,520,000 times!!




---

### Transfer Learning and Fine-Tuning

- Why can LLMs respond precisely with few prompts?
- Massive pre-trained base model
- The giant pre-trained model is adapted to specific tasks
- Application of transfer learning → Fine-tuning

---

### Transfer Learning (left) vs Fine-Tuning (right)

![](https://vitalflux.com/wp-content/uploads/2023/08/transfer-learning-vs-fine-tuning.png)

---  

### Pre-training vs Fine-tuning

- Pre-training: learn general language patterns from large text corpora
- Fine-tuning: adjust model for a specific task or domain
- Transfer learning
  - Apply knowledge gained during pre-training to new tasks
  - Enables high-accuracy responses from few prompts

---

## Next time preview - Approaching the essence of generative AI

---

### What is GPT? History leading to GPT

Next time we will finally dive into GPT! If you want to prepare in advance, watch the video below.

[ChatGPT: 30 Year History | How AI Learned to Talk](https://youtu.be/OFS90-FX6pg?si=ju7SE-nF-FNRnB9s)

![height:400](https://i.ytimg.com/vi/Nzi2TjbsDls/maxresdefault.jpg)
