# Custom Prompt Avatars

[![Image](https://img.youtube.com/vi/JnU5m6BGgow/mqdefault.jpg)](https://www.youtube.com/watch?v=JnU5m6BGgow)

Demo video: https://youtu.be/JnU5m6BGgow

This feature adds the ability to **select an avatar as a custom wake-word prompt**, allowing it to respond in _any language, voice, or TTS service_ with **personalized random TTS responses**.

Each avatar is represented through animated GIFs that appear on the screen when the wake word is detected.  
The included **blueprint** handles synchronization between the satellite microphone, the avatar animations, and the TTS greeting message.

---

## 🧠 How it works

When the wake word is detected:

1. The blueprint mutes the microphone for about **1.5–2 seconds**.
2. It plays a **custom random TTS greeting message**, such as:
   - “How can I help you?”
   - “Yes, I’m listening.”
   - “How can I assist you?”
3. The avatar’s **speech GIF** is shown during playback, then transitions to the **listening GIF**.
4. Once playback is finished, the blueprint **unmutes the microphone**, ready to capture your command.

This allows a natural and personalized interaction flow between the user and the assistant.

---

## ⚙️ Pre-requisites

- **Home Assistant 2025.11.1 or newer**
- A [configured voice assistant in Home Assistant](https://my.home-assistant.io/redirect/voice_assistants/)
- The [View Assist Integration](https://github.com/dinki/view_assist_integration)
- An audio streaming integration with microphone mute/unmute capability  
  For Android tablets, it’s recommended to use the [View Assist Companion App](https://github.com/msp1974/ViewAssist_Companion_App)

---

## 📦 Installation

### Step 1 — Copy overlay files

Copy the  
[custom_overlays](https://github.com/relust/View-Assist-ro-support/tree/main/Avatar_Prompt_Responses/view_assist/custom_overlays)  
folder into your Home Assistant configuration:

