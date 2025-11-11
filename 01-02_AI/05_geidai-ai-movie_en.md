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

# Artificial Intelligence and Creation<br>Trying Video Generation AI

Tokyo University of the Arts Arts and Media Center
Atsushi Tadokoro

---

![height:600](https://i.ytimg.com/vi/HK6y8DAPN_0/maxresdefault.jpg)

---

## Today's topics

- Brief history of video generation by generative AI
- Challenge: generate video with generative AI
- Introduce various video generation AI services
- Try them hands-on
- Introduce free video editing applications

---

## Brief history of AI video generation

---

### Historical evolution of AI video generation

AI video generation technology has evolved through decades of accumulated research

- **Foundational era (1960s–2000s):** Rule-based creative algorithms emerged, laying AI research groundwork
- **GAN revolution (2014–2019):** Generative Adversarial Networks dramatically improved realistic media generation
- **New architectures (2015–present):**
    - **Diffusion models:** Generate high-quality images by learning to remove noise
    - **Transformer:** Acquired ability to deeply interpret context via self-attention
    - Fusion of these two drives today's explosive progress

---

### Dawn of AI-generated video

**Google Deep Dream**

Used convolutional neural networks (CNNs) in reverse. Finds patterns learned by AI in the original image and over-amplifies them. https://github.com/google/deepdream

---

[Journey on the Deep Dream](https://www.youtube.com/watch?v=SCE-QeDfXtA)

![height:480](https://i.ytimg.com/vi/SCE-QeDfXtA/maxresdefault.jpg)

---

[Journey through the layers of the mind (2015)](https://vimeo.com/132462576)

![height:480](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRVA2AwQFOzDnN1xy-GHb4o5tQy2Kw9D-_olg&s)

---

### Arrival of GANs (Generative Adversarial Networks)

[【6分で分かる】元祖画像生成系AIであるGANとは！？](https://www.youtube.com/watch?v=EukVsQ81rpI)

![height:480](https://i.ytimg.com/vi/EukVsQ81rpI/maxresdefault.jpg)

---

### Example works using GANs

[take your brain to another dimension](https://www.youtube.com/watch?v=sW6D34mckkk)

![height:480](https://i.vimeocdn.com/video/743168292-c914d91fc2802eab132e9daa82ef8a571f3c114cf0847963e5c1fd975d091d7a-d)

---

[Sarah Meyohas, Infinite Petals](https://vimeo.com/866470819)

![height:480](https://artlogic-res.cloudinary.com/w_2400,h_2400,c_limit,f_auto,fl_lossy,q_auto/artlogicstorage/boeskygallery/images/view/d7f99317cac564c0d432401c73aca1b5j/marianneboeskygallery-sarah-meyohas-infinite-petals-2023.jpg)

---

### Core technologies: Diffusion Models and Transformers

State-of-the-art models combine two powerful approaches

- **Diffusion Model:**
    - **Mechanism:** Add noise to an original image and learn to reverse (denoise) the process
    - **Generation:** "Carve" a new image out of random noise guided by a text prompt
- **Transformer:**
    - **Mechanism:** Self-attention to understand relationships and context
    - **Application:** Treat video as “spatiotemporal patches” (tokens) similar to language for structural understanding

---

### Diffusion model

![height:480](https://images.prismic.io/encord/f03ed99b-90d2-4441-8537-a8aa0af23246_image12.png?auto=compress,format)

---

[【5分で分かる】画像生成AIで頻出の拡散モデルについて分かりやすく解説！](https://www.youtube.com/watch?v=2DQoXLc720M)

![height:480](https://i.ytimg.com/vi/2DQoXLc720M/maxresdefault.jpg)

---

[DALL·E: Creating images from text (OpenAI)](https://openai.com/index/dall-e/)

![height:480](https://images.ctfassets.net/kftzwdyauwt9/ed21faee-ce44-4d91-f5cc39941d47/bdd3983530857e93d205304e219e2d95/dall-e.jpg)

---

## Examples of state-of-the-art models

Between 2024–2025, highly advanced models appeared

- **OpenAI Sora 2**:
    - **Feature:** As a “world simulator,” targets physically consistent videos up to 1 minute with synchronized audio
- **Google Veo 3.1**:
    - **Feature:** As a “cinematic storyteller,” excels at film-language interpretation and advanced editing (reference images, scene extension)
- **Kuaishou Kling 2.5**:
    - **Feature:** Generates up to 2 minutes of 1080p video; strong realistic physics
---

Creator-focused tools also continue to evolve

- **Luma AI Dream Machine**:
    - **Feature:** Speed and ease of use; great for rapid prototyping and social media content
- **Runway Gen-3 Alpha**:
    - **Feature:** Integrated pro tools; fine control over camera movement for filmmakers and VFX artists
- **Pika Labs (Pika Pro)**:
    - **Feature:** Tailored for social media creators with rich creative effects and simple operation for engaging short clips

---

## Challenge: Generate video with AI

---

### Current cautions with video generation AI

- Many services exist, like in image generation
- Some are free; serious use usually requires payment
- Rapid evolution means today's info may be outdated next year

---

### Shock of Sora AI!

[Introducing Sora — OpenAI’s text-to-video model](https://www.youtube.com/watch?v=HK6y8DAPN_0)

![height:480](https://i.ytimg.com/vi/HK6y8DAPN_0/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLBNwXTPBltAfdu2hH22-_83-hNOOw)

---

- [Sora AI](https://openai.com/index/sora/): OpenAI's text-to-video model, announced Feb 2024
- Generates high-quality videos from text prompts
- Uses diffusion plus temporal consistency for detailed visuals
- Sora 2 has since been released

---

[Introducing Sora 2](https://www.youtube.com/watch?v=gzneGhpXwjU)

![height:480](https://i.ytimg.com/vi/lEcg6AJ6DVY/hq720.jpg?sqp=-oaymwE7CK4FEIIDSFryq4qpAy0IARUAAAAAGAElAADIQj0AgKJD8AEB-AH-CYAC0AWKAgwIABABGGUgQShFMA8=&rs=AOn4CLAV1pQtAICF-zWqFjj_giKZ8tzpMw)

---

[Introducing: Sora 2 Character Cameos](https://www.youtube.com/watch?v=kb9suz-kkoM)

![height:480](https://s.yimg.com/ny/api/res/1.2/eDenmrvxeRJd9ogzLIgxGQ--/YXBwaWQ9aGlnaGxhbmRlcjt3PTY0MDtoPTM2NA--/https://media.zenfs.com/en/aol_business_insider_articles_308/e13ea1f076480f1ce432dc4c004d84f7)

---

Short film generated with Sora 2

[My Very First Sora 2 Short Film | 100% Text to Video | Sora 2 Pro
](https://www.youtube.com/watch?v=JhH3uxcdM1M)

![height:480](https://i.ytimg.com/vi/JhH3uxcdM1M/maxresdefault.jpg)

---

### Comparison of major AI video generation models

<style scoped>
  table {
    font-size: 0.7em;
  }
  
</style>

| Model | Core Tech | Max Length | Max Resolution | Distinct Feature |
| :--- | :--- | :--- | :--- | :--- |
| [**Sora 2**](https://sora.com/) (OpenAI) | Diffusion Transformer | 1 min | 1080p+ | Physics simulation, native audio |
| **[Veo 3.1](https://labs.google/flow)** (Google) | Latent Diffusion Transformer | 1 min+ | 1080p+ | Cinematic language, advanced editing |
| **[Kling 2.5](https://klingai.com)** (Kuaishou) | Diffusion Transformer + 3D VAE | 2 min | 1080p | Length & physical realism |
| **[Dream Machine](https://lumalabs.ai)** (Luma AI) | Ray Video Models | ~30 s | 1080p | Speed & usability |
| **[Gen-3 Alpha](https://runwayml.com)** (Runway) | Gen-3 family | 40 s | 720p+ | Integrated pro control suite |
| **[Pika Pro](pika.art)** (Pika Labs) | Pika series | 5 s+ | 1080p | Rich creative effects |

---

## Practice: Use video generation AI

---

### **2.1 OpenAI Sora**

* **URL:** https://sora.com
* **Overview:** OpenAI flagship text-to-video model. Sets benchmark for narrative consistency and physical simulation. Latest Sora 2 released late 2025.
* **Features:** Generates high-quality videos up to 1–2 minutes. Deeply understands complex prompts with multiple characters and defined motions. Offers powerful editing features like scene extension.
* **Pricing:** Bundled with existing OpenAI subscriptions (ChatGPT Plus $20/mo, Business $25/mo) at no extra cost—major competitive advantage.

---

### **2.2 Google Veo & Flow**

* **URL:** https://labs.google/flow
* **Overview:** Veo is Google’s main model countering Sora; Flow is a creator tool built on Veo for filmmaking workflows. Veo offers ultra-realistic quality and deep ecosystem integration; Flow provides an intuitive storytelling interface.

---

* **Features:**  
  * **Veo (model):** End-to-end generation from complex prompts; outstanding realism. Native audio generation and lip-sync that surpass competitors. Smooth camera work and subtle emotional nuance.
  * **Flow (tool):** Builds narrative with features like "Scene Builder" (assemble coherent sequences), "Camera Controls" (angle/motion), and "Asset Management (Ingredients)" for character/object consistency.

---

### **2.3 Runway**

* **URL:** https://runwayml.com
* **Overview:** Comprehensive "AI magic tool suite" for creative professionals. Extends far beyond text-to-video with broad generation and editing utilities. Latest models: Gen-4 and Aleph.
* **Features:** Keyframe camera path control, Motion Brush for animating specific regions, reference image-based identity/style consistency. Turbo mode for rapid iterations.

---

* **Pricing:** Credit-based subscription.
  * **Free:** 125 credits (first time), watermark
  * **Standard:** $12/mo annual, 625 credits, no watermark
  * **Pro:** $28/mo annual, 2,250 credits
  * **Unlimited:** $76/mo annual, 2,250 fast credits + unlimited relax rate (reports of throttling exist)
  * **Commercial use:** Allowed on all tiers including Free

---

* **Pricing:** Flow has 100 monthly free credits; serious use requires paid Google AI plan.  
  * **Google AI Pro:** $19.99/mo. Credits (e.g. 1,000/mo), Veo 3.1 Fast model. Watermark present.
  * **Google AI Ultra:** $249.99/mo. More credits (e.g. 25,000/mo), full access, no watermark.

---

### **Luma AI Dream Machine**

* **URL:** https://lumalabs.ai
* **Overview:** High-quality motion, smooth physics, and cinematic texture.
* **Features:** Converts stills to realistic moving video. Multiple models (Ray1.6, Ray2, Ray3) for purpose selection. 4K upscaling, HDR, reframing.

---

* **Pricing:** Credit-based.
  * **Free:** 8 draft vids/mo, watermark, non-commercial
  * **Lite:** $7.99/mo annual, 3,200 credits, watermark, non-commercial
  * **Plus:** $23.99/mo annual, 10,000 credits, no watermark, commercial
  * **Unlimited:** $75.99/mo annual, 10,000 fast + unlimited relax
  * Example: 10s 1080p Ray2 costs ~340 credits

---

### **Pika**

* **URL:** https://pika.art  
* **Overview:** High-quality yet stylized creativity—popular for social content; latest Pika 2.2.
* **Features:** Unique "Pikaffects" (inflate, dissolve, explode). Strong at object manipulation and style conversion (e.g. anime).

---

* **Pricing:** Credit-based.
  * **Free (Basic):** 80 credits/mo, watermark
  * **Standard:** $8/mo annual, 700 credits, no watermark, commercial
  * **Pro:** $28/mo annual, 2,300 credits
  * Example: Model 2.2, 10s 1080p video costs 45 credits (fast depletion reports)

---  

### **Kling**

* **URL:** https://klingai.com
* **Overview:** Developed by Kuaishou (short video platform). Strong output quality, physics realism, competitive pricing.
* **Features:** Up to 1080p (4K on higher tiers), extend up to 3 min. Professional mode consumes more credits for higher quality.

---

* **Pricing:** Credit-based.
  * **Free:** ~166 credits/mo (or 66/day), 720p, 10s max, watermark
  * **Standard:** ~$10/mo, 660 credits, 1080p, 30s, no watermark
  * **Pro:** ~$37/mo, 3,000 credits, 4K, 60s
  * Professional mode: 70 credits for 10s

---


### Reference: Runway video generation techniques

![height:460](https://i.ytimg.com/vi/UlFruPnlnQA/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLCYlLXSsxdhoPll7P_LcJ62Aa6Hlg)
[Masterclass: AI film Directing in Runway Gen 3 – Create Stunning Cinematic Shots!](https://youtu.be/UlFruPnlnQA?si=Wk3F8Q2zBISlM1Ko)

---

## Reference: Free video editing apps

After generating video material, how to edit?

- If you have Adobe CC → [Adobe Premiere Pro](https://www.adobe.com/jp/products/premiere.html)

But there are very powerful free editors too

- Blackmagic Design [DaVinci Resolve](https://www.blackmagicdesign.com/jp/products/davinciresolve/)
![height:300](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/DaVinci_Resolve_Studio.png/800px-DaVinci_Resolve_Studio.png)

---

### [DaVinci Resolve](https://www.blackmagicdesign.com/jp/products/davinciresolve/)

- Free video editor
- Supports up to Ultra HD 4K (3840x2160)
- Advanced color grading capability

![height:400](https://images.blackmagicdesign.com/images/products/davinciresolve/overview/onesolution/carousel/edit.jpg)

---

## Assignment for next time

### Production assignment: "Hallucination - Bad Trip"

![height:480](https://www.themanual.com/wp-content/uploads/sites/9/2023/06/fear-and-loathing-in-las-vegas.jpg?p=1)

---

**Assignment:**

Express the theme "Hallucination - Bad Trip" through video while exploring the possibilities of contemporary generative AI technology. Produce a piece conveying anxiety, confusion, and surreal experience. Incorporate visual distortion and sensory instability so that the boundary between reality and hallucination blurs.

- Length: 5 seconds – ~1 minute
- Must use AI-generated video as material
- May edit generated video in an editing app
- Submit & present next session!
