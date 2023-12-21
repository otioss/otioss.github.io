---
title: "AccentCoach: Transfrom Your Accent into American Accent"
date: '2023-12-13'
---

Accent reduction is a goal that many non-native English speakers persue. A big obstacle is that they often listen to native speakers’ speech, but they have never heard **their own voice with a native accent**. If learners could listen to their own voice speaking with a native accent, they can notice the differences and improve how they sound. Think of it like a personal AI accent coach but with your own voice.

Now how can we change the accent of a non-native English speaker to sound like a native American speaker? Well, It turns out by carefully adjusting the *prosody* and *timbre* in a TTS model such as [StyleTTS2](https://github.com/yl4579/StyleTTS2), we can achieve this accent transformation with ease. 


I created a demo on HuggingFace called **[AccentCoach](https://huggingface.co/spaces/otioss/AccentCoach)** that can transform any accent into an American accent. It is technically a STTS: Speech-to-Text (Whisper) and then Text-to-Speech (StyleTTS2). The output sounds a bit robotic, but it is good enough to assist English language learners. Let's hear two examples first.


**Einstein's distinct accent**:

<audio controls="controls" preload="auto" src="/assets/audio/Albert-Einstein.wav">
<p>Your browser does not support the audio element.</p>
</audio>

<br/>
Here is **Eintein's American accent** produced by AccentCoach: 


<audio controls="controls" preload="auto" src="/assets/audio/Albert-Einstein-Native-American-Accent.wav">
<p>Your browser does not support the audio element.</p>
</audio>

<br/>
**Arnold Schwarzenegger's accent**:
<audio controls="controls" preload="auto" src="/assets/audio/Arnold-Schwarzenegger.wav">
<p>Your browser does not support the audio element.</p>
</audio>

<br/>
Here is **Arnold Schwarzenegger's American accent** produced by AccentCoach:
<audio controls="controls" preload="auto" src="/assets/audio/Arnold-Schwarzenegger-Native-American-Accent.wav">
<p>Your browser does not support the audio element.</p>
</audio>
<br/>
 

Curious about how you'd sound with an American accent? Give the demo a try! 

**Attention**: It's highly recommended to clone the space and run it either locally or on a powerful GPU on HuggingFace. The model might take more than 10 seconds to do inference on HF's free vCPUs. On the other hand, it takes less than a second to make inference on an Nvidia 3090. 


## 🐷 [AccentCoach on HuggingFace](https://huggingface.co/spaces/otioss/AccentCoach) 🐷


[![Accent-Coach-AI-Accent-Cloning-Reduction.jpg](https://i.postimg.cc/wvYtD7Dd/Accent-Coach-AI-Accent-Cloning-Reduction.jpg)](https://huggingface.co/spaces/otioss/AccentCoach)


## Run AccentCoach locally
I tested this on Arch Linux, but the steps should be applicable to Mac and Windows as well, with minor modification.

1. git lfs install
2. git clone https://huggingface.co/spaces/otioss/AccentCoach
3. cd AccentCoach
4. python -m venv ac_env
5. source ac_env/bin/activate
6. pip install -r requirements.txt
7. sudo pacman -S espeak-ng
Now run the app:
8. python accent_gradio.py
9. Open the URL http://127.0.0.1:7860 in your browser.
