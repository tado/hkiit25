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

# Workshop 06:<br>Introduction and Installation of TouchDesigner

---

![bg](https://lh3.googleusercontent.com/pw/AP1GczMDtZp2IQdMwkwQu4VGm6OSxWe1OjlKD4X90FOuBLZQfS_ozciaP_rlCI_T51VQ0cckdRrg2cDJfnM5cHX-iIUcyqJ2cgXWDVkERvrTu2zI1MRKcDeksPbjqT6GfE4fVnrs4FXwF_JmecxeE2nVIPYjXw=w1486-h989-s-no-gm?authuser=0)

---

## About TouchDesigner

---

![bg](https://i.ytimg.com/vi/wmM1lCWtn6o/maxresdefault.jpg)

---

### TouchDesigner

- [https://derivative.ca/](https://derivative.ca/)
- A visual programming environment developed by the Canadian company Derivative.
- It allows for the easy construction of systems for various video, music, and digital art applications, such as installation art, projection mapping, and media art.
- Details: [https://derivative.ca/feature/application-building](https://derivative.ca/feature/application-building)

---  

### Examples of Works Using TouchDesigner

---

![bg left](https://derivative.ca/sites/default/files/styles/content_colorbox/public/field/body-images/Astro02.1_sm.jpeg)[Astro Immersive AV Performance - Weidi Zhang](https://www.zhangweidi.com/astro)

---

![bg left](https://d1zjbsz5boin5y.cloudfront.net/images/2020/08/31172807/DSC01837.jpg)[Tokorozawa Sakura Town KADOKAWA Tokorozawa Campus](https://thinkandsense.com/works/tokorozawa-sakuratown/)

---

![bg left](https://www.sonycsl.co.jp/wp-content/uploads/2019/06/1_image_preview.jpeg)[Fragment Shadow
Generating Fragmented Shadows
with Multi-Projectors Geometry and Color Calibration](https://www.sonycsl.co.jp/projects/fragment-shadow/)

---

![bg left](https://derivative.ca/sites/default/files/field/body-images/Infratonal_XSP_586_28m.jpg)[Natural Encounters
an emotional link between human and algorithm](https://infratonal.com/portfolio_page/encounters/)


---

![bg left](https://derivative.ca/sites/default/files/field/body-images/2DEW9472_01.jpg)[404.zero live at Diage Festival, Bangkok, 2023.](https://youtu.be/44kW5Gp15s0?si=6OrvY12799C2fhCh)

---

![bg left](https://derivative.ca/sites/default/files/field/body-images/BABYMETL_METALIZM_sm_0.jpg)[Interactive live visual system with venue simulator and chart output for BABYMETAL "METALIZM" - Kezzardrix](https://youtu.be/NzWxAE7C2Os?feature=shared&t=94)

--- 	

![bg left](https://i.ytimg.com/vi/Tbaft6u2Roo/maxresdefault.jpg)[NONOTAK - SHIRO (TEASER)](https://youtu.be/Tbaft6u2Roo?si=NTA8ACZWeDK4oL37)

--- 	

![bg left](https://i.ytimg.com/vi/r7S1PvfDb2E/hq720.jpg?sqp=-oaymwE7CK4FEIIDSFryq4qpAy0IARUAAAAAGAElAADIQj0AgKJD8AEB-AH-CYAC0AWKAgwIABABGE0gWihlMA8=&rs=AOn4CLDHykmoyEF-QWBV9KE3mJyJJ-r43w)[NONOTAK - DUAL](https://youtu.be/r7S1PvfDb2E?si=X6aAJXKfE0DOtTrN)

---

Many other works are regularly published on Derivative's [Showcase](https://derivative.ca/showcase). Please take a look for reference.

---

## TouchDesigner Installation and Key Registration

---

### TouchDesigner Licenses

TouchDesigner is not an open-source development environment like Processing or openFrameworks, but a product sold by Derivative (proprietary software). However, it is available for free for non-commercial use.

---

License Details

![height:540px](https://yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-02-172445.png)

---

In this workshop, we will use the NON-COMMERCIAL version. It has the following limitations:

- Resolution is limited to 1280x1280 pixels.
- Can only be used for personal or learning purposes.
- All accounts are granted 10 non-commercial keys.
- Cannot be used for paid projects.

---

It's a good idea to start with the NON-COMMERCIAL version, and if you want to use it more seriously, you can purchase the EDUCATIONAL version.

---

### Installation and Key Registration Steps

After installing the TouchDesigner application, you need to register a key assigned to your account. Let's follow these steps.

---

**User Registration: Register as a user on the Derivative site**

- From the "SIGN UP FOR AN ACCOUNT" page on the Derivative website: [https://derivative.ca/user/register](https://derivative.ca/user/register)
- Fill in the required information and submit.
- A confirmation email will be sent to your registered email address. Click the link to complete the registration.

---

**Download TouchDesigner**

- Download the installer for your OS from the [download page](https://derivative.ca/download).
- Launch the installer and install (no need to change any settings).

---

**Launch TouchDesigner and Register the Key**

- Launch the installed TouchDesigner application.
- From the top menu, select "Dialogs > Key Manager".
- The following screen will appear. Log in with your registered information.
- Select a key and activate it.

---

![](https://docs.derivative.ca/images/4/4f/KeyManagerCreate.png)

---

**Restart the Application**

- Restart the application, and the NON-COMMERCIAL version should launch.

---

### Note on Using TouchDesigner Installed on AMC Macs

TouchDesigner is installed on all iMacs in the AMC lab. However, since files saved on the AMC Macs are erased and reset to their original state upon restart, you need to register and remove your key each time you use it by following these steps.

---

**Create a User Account**

- You will use the personal key assigned to your Derivative account.
- Register for an account in advance from "[SIGN UP FOR AN ACCOUNT](https://derivative.ca/user/register)".

---

**Launch and Activate the Key**

- Start the computer and launch the TouchDesigner application.
- From the top menu, select "Dialogs > Key Manager".
- The following screen will appear. Log in with your registered information.<br/>![](https://yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-02-174203.png)

---

- Select a key and activate it.<br/>![](https://docs.derivative.ca/images/4/4f/KeyManagerCreate.png)

---

**Use the TouchDesigner Application**

- You can now use TouchDesigner just like someone using it on their personal laptop.

---

**Remove the Key and Exit**

- Before closing the application, you must remove the key from the app.
- From the top menu, select "Dialogs > Key Manager".
- Select the Disable tab and press the Disable Key button.

  ![height:400px](https://yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-03-054538.jpg)

---

**Shut Down the System**

- Close the application and shut down the system.

*Be careful! If you don't do this, the number of available keys will decrease each time.

---

## First Steps in TouchDesigner

Today, as a first step in TouchDesigner, we will try the "Rotate a Banana" challenge. This is based on the following video tutorial.

![height:360](https://i.ytimg.com/vi/1gxN1-dUfyw/maxresdefault.jpg)

- [【Introduction to TouchDesigner】Let's rotate Banana in 10min ! #00](https://youtu.be/1gxN1-dUfyw?si=BTAGPEDhAIexO7zQ)

---

And one more!

![height:360](https://i.ytimg.com/vi/lWGknmeueMA/maxresdefault.jpg)

- [【 TouchDesigner Beginner Course 】Basic Operations and Basic TOPs #01](https://youtu.be/lWGknmeueMA?si=T3v4-pCUgCAS07jG)

---

### Final Image

![height:480](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/04/image-7.png?resize=1536%2C1034&ssl=1)

---   

## For Those Who Want to Learn More Thoroughly and Carefully...

---

![height:360](https://yoppa.org/wp-content/uploads/2025/04/101_00-cover.png)

We will use the online teaching material "The 100 Series: TouchDesigner Fundamentals" provided by Derivative to learn from the introduction to the basics. Enthusiastic students are encouraged to study ahead.

---

### 101 – Navigating the Environment

**The Grammar of TouchDesigner**

A large part of learning any new tool or environment is figuring out where all the knobs and buttons are. This first lesson focuses on getting you comfortable moving around TouchDesigner, learning the essential interface elements and controls, and the basic principles of each operator family.

---

#### 101-1. The User Interface

- [Course Page](https://learn.derivative.ca/courses/100-fundamentals/lessons/101-navigating-the-environment/topic/user-interface/)
- [Tutorial Video (YouTube)](https://youtu.be/d5n4QbJ2N_Q?feature=shared)
- [Download Sample File](https://github.com/TouchDesigner/CurriculumExamples/raw/main/toxExamples/TouchDesignerFundamentals/100/101/TDFundamentals-101-userInterface.tox)

---

#### 101-2. Using the OP Create Dialog

- [Course Page](https://learn.derivative.ca/courses/100-fundamentals/lessons/101-navigating-the-environment/topic/using-the-op-create-dialog/)
- [Tutorial Video](https://youtu.be/5AaXWvdQrbI?feature=shared)
- [Download Sample File](https://github.com/TouchDesigner/CurriculumExamples/raw/main/toxExamples/TouchDesignerFundamentals/100/101/TDFundamentals-101-OPCreateDialog.tox)

---

#### 101-3. Reading Network Anatomy

- [Course Page](https://learn.derivative.ca/courses/100-fundamentals/lessons/101-navigating-the-environment/topic/reading-network-anatomy/)
- [Tutorial Video](https://youtu.be/0h01Nwj-lAg?feature=shared)
- [Download Sample File](https://github.com/TouchDesigner/CurriculumExamples/raw/main/toxExamples/TouchDesignerFundamentals/100/101/TDFundamentals-101-networkAnatomy.tox)

---

#### 101-4. Reading Operator Anatomy

- [Course Page](https://learn.derivative.ca/courses/100-fundamentals/lessons/101-navigating-the-environment/topic/reading-operator-anatomy/)
- [Tutorial Video](https://youtu.be/wKBtfHTjsNM?feature=shared)
- [Download Sample File](https://github.com/TouchDesigner/CurriculumExamples/raw/main/toxExamples/TouchDesignerFundamentals/100/101/TDFundamentals-101-operatorAnatomy.tox)

---

#### 101-5. Operator Wires, References & Links

- [Course Page](https://learn.derivative.ca/courses/100-fundamentals/lessons/101-navigating-the-environment/topic/manipulating-operator-wires/)
- [Tutorial Video](https://youtu.be/wb51mj-HNiQ?feature=shared)
- [Download Sample File](https://github.com/TouchDesigner/CurriculumExamples/raw/main/toxExamples/TouchDesignerFundamentals/100/101/TDFundamentals-101-opWiresReferencesAndLinks.tox)

---

## Today's Assignment

---

### Assignment: Let's play with noise!

---

![height:360px](https://yoppa.org/wp-content/uploads/2024/04/Screenshot-2024-04-04-103723.png)

Using the Noise TOP, which can easily generate noise from two to four dimensions, try to create your own "work" through trial and error. You can download the prototype program from the link below.

- [Noise Sample](https://github.com/tado/td-workshop/blob/main/geidai-mediaart/toe/01-01SimpleNoise.toe)

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
