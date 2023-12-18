---
title: "AccentCoach: Transfrom Your Accent into American Accent"
date: '2023-12-13'
---

Accent reduction is a goal that many non-native English speakers persue. A big obstacle is that they often listen to native speakers’ speech, but they have never heard their own voice with a native accent. If learners could listen to their own voice speaking with a native accent, they can notice the differences and improve how they sound. Think of it like a personal AI accent coach but with your own voice.

Now how can we change the accent of a non-native English speaker to sound like a native American speaker? Well, It turns out by carefully adjusting the prosody and timbre in a TTS model such as [StyleTTS2](https://github.com/yl4579/StyleTTS2), we can achieve this accent transformation with ease. 


I created a demo on HuggingFace called [AccentCoach](https://huggingface.co/spaces/otioss/AccentCoach) that can transform any accent into an American accent. It is technically a STTS: Speech-to-Text (Whisper) and then Text-to-Speech (StyleTTS2). The output sounds a bit robotic, but it is good enough to assist English language learners. Let's hear two examples first.


Einstein's distinct German accent:

<audio controls="controls" preload="auto" src="/assets/audio/Albert-Einstein.wav">
<p>Your browser does not support the audio element.</p>
</audio>

<br/>
Here is his American accent produced by AccentCoach: 


<audio controls="controls" preload="auto" src="/assets/audio/Albert-Einstein-Native-American-Accent.wav">
<p>Your browser does not support the audio element.</p>
</audio>

<br/>
Arnold Schwarzenegger's Austrian accent:
<audio controls="controls" preload="auto" src="/assets/audio/Arnold-Schwarzenegger.wav">
<p>Your browser does not support the audio element.</p>
</audio>

<br/>
Here is his American accent produced by AccentCoach:
<audio controls="controls" preload="auto" src="/assets/audio/Arnold-Schwarzenegger-Native-American-Accent.wav">
<p>Your browser does not support the audio element.</p>
</audio>
<br/>
 

Curious about how you'd sound with an American accent? Give the demo a try! 

**Attention**: It's highly recommended to clone the space and run it either locally or on a powerful GPU on HuggingFace. The model might take more than 20 seconds to do inference on HF's free vCPUs. On the other hand, it takes less than a second to make inference on an Nvidia 3090. 

##[AccentCoach on HuggingFace](https://huggingface.co/spaces/otioss/AccentCoach)


[![Accent-Coach-AI-Accent-Cloning-Reduction.jpg](https://i.postimg.cc/wvYtD7Dd/Accent-Coach-AI-Accent-Cloning-Reduction.jpg)](https://huggingface.co/spaces/otioss/AccentCoach)



