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

# Artificial Intelligence and Creation<br>Coding and AI

Tokyo University of the Arts Arts and Media Center (AMC)
Atsushi Tadokoro

---

## Today's topics

- Coding subject: a brief intro to p5.js
- AI-assisted coding 1: Ask ChatGPT
- AI-assisted coding 2: Use an editor with AI features
- AI-assisted coding 3: Integrate with more advanced AI

---

## Coding subject: brief intro to p5.js

---

### What is p5.js

![height:480](https://pbs.twimg.com/card_img/1855859087315251200/LYDj0bsK?format=jpg&name=medium)

---
[https://p5js.org/](https://p5js.org/)

- p5.js is a JavaScript port of "Processing," a programming language for visual arts.
- Runs directly in the web browser
- Suitable for art, design, and interactive media works
- Beginner-friendly, simple syntax; great for learning programming
- Extensive tutorials and references on the official site
- Supported by an active community

---

### What can you do with p5.js – OpenProcessing

![height:480](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/11/image-5.png?resize=1024%2C527&ssl=1)

---

[https://openprocessing.org/](https://openprocessing.org/)

- Online service to create and share p5.js sketches
- You can view works from creators around the world, including source code!

---

### Simple program example

```javascript
function setup() {
  // Create a canvas filling the entire screen
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  // Gray background
  background(220);
  // Draw a circle
  circle(width / 2, height / 2, 400);
}
```

※ It's totally fine if it makes no sense yet!

---

Result 

![height:400](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-103359.png)

Let's try generating such programs with the help of AI!

---

## AI-assisted coding 1: Ask ChatGPT

- Probably the easiest way to start
- Just ask ChatGPT coding questions

---

Example:

I want to draw a circle at the center of the browser window. How should I do it?

Please make it fullscreen. Use p5.js as the environment.

---

I asked ChatGPT 4o.

- [https://chatgpt.com/c/673d4173-1fe8-800e-a6ed-79a1ad77dc05](https://chatgpt.com/c/673d4173-1fe8-800e-a6ed-79a1ad77dc05)


---

To draw a circle at the center of the browser using p5.js, write code like this. p5.js makes it easy to create a canvas and draw graphics.

Here's simple code for a fullscreen canvas drawing a circle.

---

### Example program

```javascript
function setup() {
  // Create a fullscreen canvas
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  background(220); // light gray background

  // Circle style
  fill(100, 150, 255); // blue fill
  noStroke(); // no border

  // Draw circle at the center
  let centerX = width / 2;
  let centerY = height / 2;
  let diameter = 100; // diameter

  ellipse(centerX, centerY, diameter, diameter);
}

function windowResized() {
  // Adjust canvas on window resize
  resizeCanvas(windowWidth, windowHeight);
}
```

---

### Code explanation
1. **`setup` function:**
   - `createCanvas(windowWidth, windowHeight)` makes the whole window the canvas.
2. **`draw` function:**
   - `background(220)` clears the background each frame.
   - `ellipse(centerX, centerY, diameter, diameter)` draws a 100px circle at center.
3. **`windowResized` function:**
   - Resizes the canvas when the window changes.

---

### How to run
1. Open the [p5.js Web Editor](https://editor.p5js.org/).
2. Paste the code above.
3. Click "Play" and a circle appears fullscreen.

Feel free to tweak color and size!

---

### Result (perfect!!)

![height:480](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-110352.png)


---

### Practice: Try code generation with ChatGPT

- Ask ChatGPT to generate p5.js code you want
- Specify the environment up front, e.g., “in p5.js”
- Copy/paste generated code into the p5.js Web Editor
- Run the code

----

## AI-assisted coding 2: Use an editor with AI features

---

### Want more advanced features?

- Get interactive support from AI while seeing results
- Have AI help when errors occur
- Ask AI to improve your existing code

---

### Try p5.CodingWithAI

![height:480](https://kyabe.net/static/fdec8457230ed05b1fea8500a5215ef2/a9c34/thumbnail.webp)

---

- [https://app.kyabe.net/p5-coding-with-ai/](https://app.kyabe.net/p5-coding-with-ai/)
- A custom p5.js web editor integrated with ChatGPT
- By Kyabe / Masaya Kurahashi
- Users can send natural-language requests; AI proposes code with explanations
- Through iterating on proposals, users craft works—exploring human-AI co-creation

We'll walk through usage live in a demo!

---

By the way, I sent the same question to p5.CodingWithAI
→ Perfect!

![height:480](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-115424.png)

---

### Practice: Code generation with p5.CodingWithAI

- First, generate basic code from a prompt
- Iterate with questions to get closer to your preferred result
- Evaluate which AI proposals to accept at each step
- What code will you end up with!?

---

## AI-assisted coding 3: Integrate with more advanced AI

---

### Try GitHub Copilot

![height:480](https://www.logicalcube.com/wp-content/uploads/2023/07/github-copilot-logo.jpeg)

---

GitHub Copilot is an AI pair-programming tool based on OpenAI Codex. It supports programmers by proposing code in real time in the editor. It offers code completion, function generation, and code generation from comments. It integrates with major IDEs/editors (e.g., Visual Studio Code) and supports multiple languages—helpful for both beginners and advanced users.

[https://github.com/features/copilot](https://github.com/features/copilot)

---

#### Main features of GitHub Copilot

- **Code completion:** Predicts and suggests the next lines
- **Function generation:** Generates function bodies from names and comments
- **Code from comments:** Generates code from natural language comments
- **Multi-language:** Python, JavaScript, TypeScript, Ruby, etc.
- **IDE integration:** Visual Studio Code, Visual Studio, Neovim, JetBrains, etc.

---

- **Test generation:** Creates tests for existing code
- **Refactoring suggestions:** Proposes more efficient patterns
- **PR summaries:** Summarizes changes automatically
- **Chat:** Ask in natural language; get code and info
- **Multi-model:** Choose models from Anthropic, Google, OpenAI, etc.

---

### Prerequisites for using GitHub Copilot

Steps

1. Register a GitHub account
1. Start GitHub Copilot trial
1. Install Visual Studio Code
1. Configure Visual Studio Code

- See details here
- https://yoppa.org/ycam24/16644.html

---

Once configured, VS Code + GitHub Copilot becomes a powerful coding environment!

![height:480](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-121622.png)

---

Generated a "cute character"!

![height:480](https://yoppa.org/wp-content/uploads/2024/11/Screenshot-2024-11-20-121932-1.png)

---

### Code generation with GitHub Copilot

See: [Hands-on: Code generation with AI (YCAM Workshop 2024)](https://yoppa.org/ycam24/16647.html)

![height:400](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/10/image.jpeg?w=1280&ssl=1)
