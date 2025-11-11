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

# Artificial Intelligence and Creation<br>The 30-year history leading to ChatGPT<br>Introduction to image generation AI

---

![height:600](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/10/Image_fx-1-1.png?w=1408&ssl=1)

---

### Today's topics

Before systems like ChatGPT, there were about 30 years of progress in neural computing. Today, we'll watch a video reviewing that history and deepen our understanding of Transformers, the foundational technology of modern generative AI. For those who want to learn more, we will introduce additional resources explaining Transformer mechanisms. In the latter half, we'll try several image-generation AI services firsthand and learn their features and usage. Finally, as homework, you'll attempt to create a self-portrait using an image generation AI.

---

## The 30-year history leading to ChatGPT

[ChatGPT: 30 Year History | How AI Learned to Talk](https://youtu.be/OFS90-FX6pg?si=ju7SE-nF-FNRnB9s)

![height:420](https://i.ytimg.com/vi/Nzi2TjbsDls/maxresdefault.jpg)

---

### Summary of the video

- The emergence of ChatGPT: ChatGPT is the first program that ordinary people could converse with, breaking the Turing Test.
- Complexity of language: Many linguists once thought computers could never understand human language, but many have since changed their minds.
- Supervised learning: Past neural network research learned one task against a fixed goal, with no clear path to a general-purpose system.
- Early sequence learning: In 1986, Jordan ran experiments with RNNs predicting symbol sequences, introducing the notion of memory to networks.

---

- Elman's research: Jeffrey Elman discovered that neural networks can automatically learn word boundaries in language.
- Transformer introduction: In 2017, the Transformer architecture was developed to address translation tasks, becoming the foundation of today's LLMs.
- Evolution of the GPT series:
  - GPT-1: Used Transformer for next-word prediction.
  - GPT-2: Trained on web-scale data; larger network achieved superior generation.
  - GPT-3: 175B parameters; demonstrated new capabilities like zero-shot learning.
- Philosophical debate: Do AIs truly "think" or merely simulate thinking? The debate continues among researchers.

---

## LLMs and how Transformers work

---

**[How LLMs Work (simple version)](https://www.youtube.com/watch?v=y7NQiNER6r4)**

Clear explanation of LLMs and Transformers

![height:400](https://img.youtube.com/vi/LPZh9BOjkQs/maxresdefault.jpg)


---

### Key points from the video

- Essence of LLMs
  - An LLM is a mathematical function predicting the next word
  - It doesn't choose one word, but assigns probabilities
- How responses are generated
  - Based on user input, the AI emits words one by one
  - Choosing some low-probability words can produce more natural text
- Training data and scale
  - It would take humans 2,600+ years to read GPT-3's training data
  - Current models are trained on even more data

---

- Parameter tuning
  - Hundreds of billions of parameters govern behavior
  - Initially random, refined through training
- Learning process (pre-training)
  - Compare predictions with targets, update parameters by backpropagation
  - Repetition enables generalization to new inputs
- Massive compute
  - Even at 1 billion ops/sec, total would take over 100 million years

---

- RLHF
  - After pre-training, align with human preferences via feedback
  - Fine-tune to prefer helpful responses
- Transformers
  - Earlier models processed word-by-word; Transformers process in parallel
  - Convert text to numbers and update meaning in context
- Attention mechanism
  - Words exchange information to adapt meanings to context
  - E.g., "bank" becomes "river bank"

---
  
-  Feed-forward structure
  - Auxiliary mechanism to learn more language patterns
  - Encodes richer sentence semantics via complex operations
- Prediction and uncertainty
  - Output is a probability distribution
  - Behavior is framed by design but determined by training

---

## For those who want to go deeper into Transformer internals…

--- 

**[TRANSFORMER EXPLAINER](https://poloclub.github.io/transformer-explainer/)**

![height:460](https://poloclub.github.io/transformer-explainer/preview/summary.png)

Interactive visualization of Transformers!

---

**[The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)**

![height:400](https://jalammar.github.io/images/t/transformer_resideual_layer_norm_3.png)

Illustrated explanation of Transformer architecture and attention

---

**[What is GPT? Visualizing Transformers | Chapter 5, Deep Learning
](https://youtu.be/KlZ-QmPteqM?si=NleCQHluO8pf3DDp)**

![height:420](https://i.ytimg.com/vi/KlZ-QmPteqM/maxresdefault.jpg)

Detailed video explanation

---

### Tip: Use ChatGPT to summarize web pages and YouTube videos

![height:400](https://lh3.googleusercontent.com/mRqnE0XmbAJcwWSXWSczGn66hsSdzwm2PXDLOeY6WAjwQzxDYYvuJWIN003JcbdWIxSGD9Hl4t0DX3d3gZKn6celUCM=s1280-w1280-h800)

[ChatGPT Summarize](https://chromewebstore.google.com/detail/chatgpt-summarize/cbgecfllfhmmnknmamkejadjmnmpfjmp)
Very handy Chrome extension!!

---

## Try image generation AI!


Multiple image generation AIs are now available. Let's try the following services.

---

### Nano Banana (Gemini 2.5 Flash Image)

![height:420](https://substackcdn.com/image/fetch/$s_!j2VC!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbe1b6f38-41a2-4e18-8d8f-c321bfaf675c_1920x1080.jpeg)

---

  - **URL:** [gemini.google.com](https://gemini.google.com), [aistudio.google.com](https://aistudio.google.com)
  - **Features:** Deep integration with Google Search, Lens, and ecosystem. Advanced capabilities such as multi-image fusion, conversational editing via natural language, and "visual reasoning" powered by the Gemini LLM
  - **Pros:** Integrated into familiar Google tools; easy to use without expertise; intuitive natural-language editing and generation
  - **Cons:** Default output resolution can be low; may require upscaling for pro quality. Watermarks on generated images can constrain commercial use
  - **Pricing:**
      - Limited free access
      - Google AI Pro (¥2,900/mo or $19.99)
      - Developer API (about $0.039 per image)

---

### Google ImageFX

![height:420](https://imagefx.me/blog/introducing-imagefx/imagefx-cover.png)

---
- **URL:** [https://labs.google/fx/tools/image-fx](https://labs.google/fx/tools/image-fx)
- **Features:** Uses Google's latest image model "Imagen 3" to generate high-quality images. Offers "expression chips" suggesting prompt options and partial image editing for intuitive control.
- **Pros:** Completely free with a Google account. Especially strong at photorealistic, high-quality imagery; beginner-friendly.
- **Cons:** Strict content policy; some prompts are refused. Being new, may have limited features or minor issues.
- **Pricing:**
  - Free (Google account required)

---

### DALL-E 3

![height:420](https://i.ytimg.com/vi/gfy-OmYVuu4/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLAcdrptBylqrj26CVwO6Wnv5pWjfg)

---

  - **URL:** [chatgpt.com](https://chatgpt.com)
  - **Features:** Integrated into ChatGPT for conversational generation/editing; clarifies ambiguous instructions; auto-creates effective prompts.
  - **Pros:** Very intuitive for beginners through chat; highly faithful to instructions; excels at rendering clean text in images.
  - **Cons:** Relatively weaker at highly artistic or stylistically unique imagery; often biased toward a CG-like look.
  - **Pricing:**
      - Available on free ChatGPT plan (with limits)
      - ChatGPT Plus ($20/mo) for more generations
      - Developer API ($0.04–$0.12 per image)

---      

### Midjourney

![height:420](https://assets.eweek.com/uploads/2024/09/ew_20240925-midjourney-review.png?w=1024)

---

  - **URL:** [www.midjourney.com](https://www.midjourney.com)
  - **Features:** Highly artistic and extremely photorealistic generation. Main interface is Discord with an active community. Rich parameters like `--cref` and `--sref` for character/style consistency.
  - **Pros:** Industry-leading artistic quality and photorealism; powerful consistency controls.
  - **Cons:** Requires familiarity with Discord; steeper learning curve; no free plan.
  - **Pricing:**
      - Basic ($10/mo)
      - Standard ($30/mo)
      - Pro ($60/mo)
      - Mega ($120/mo)

---      

### Stable Diffusion

![height:420](https://miro.medium.com/1*Rbq9cDCJpGq7HKeNAeIitg.jpeg)

---

  - **URL:** [stability.ai/stable-image](https://stability.ai/stable-image)
  - **Features:** Open source; can run locally for free. Rich ecosystem of custom models, ControlNet, LoRA, etc., offering extreme customizability.
  - **Pros:** Completely free and unlimited locally; high customization freedom; privacy via offline use.
  - **Cons:** Local use requires a powerful PC (especially GPU); environment setup can be demanding for beginners.
  - **Pricing:**
      - Local use on your PC is free
      - Web/API pricing varies by provider (free credits, subscriptions, etc.)

---      

### Adobe Firefly

![height:420](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS8Adj_1oKqf4tBNGDx6b7kqcF9E_kQQXZ1nheSHtJlyijXrHnieFFE-v-EGkUn5w6a0nQ&usqp=CAU)

---

  - **URL:** [firefly.adobe.com](https://www.google.com/search?q=https://firefly.adobe.com)
  - **Features:** Trained on commercially safe data like Adobe Stock; low copyright risk. Deep integration with Adobe CC like Photoshop's "Generative Fill".
  - **Pros:** Very low legal risk for commercial use; integrated into pro-familiar tools; boosts workflow productivity.
  - **Cons:** Sometimes weaker photorealism than top peers; no negative prompts.
  - **Pricing:**
      - Free (25 credits/month)
      - Standard (¥1,580/mo for 2,000 credits)
      - Pro (¥3,180/mo for 4,000 credits)
      - Credits also included with Creative Cloud plans

---

### First, try various ones!

- Try different image generation AIs!
- Each service/model has its own personality
- Personal recommendations
  - [Imagen 3 in ImageFX](https://labs.google/fx/tools/image-fx) (if you have a Google account)
  - [OpenAI's DALL-E 3](https://openai.com/index/dall-e-3/)

---

### Practice, assignment for next time

Assignment: **"Create a self-portrait with an image generation AI"**

- Try several image generation AIs
- Try multiple approaches (text-to-image, uploading an illustration, etc.)
- Choose one preferred service
- Generate your self-portrait
  - Style is free: photorealistic, illustrative, oil painting, etc.
  - What prompts help it resemble you?
- Next time: contest for "who looks the most like themselves?"
