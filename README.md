"Believe in your voice, for it can paint the world in any color you imagine! 🎨✨"

---

## Introduction
Hello, amigos! Today, we’re going to build a **Voice Controlled RGB Light** project. That means we’ll use our **voices** to change the color of a light—just like magic! This activity will help you learn how to connect your app to a **Bluetooth** device and use **speech recognition** to control **RGB** (Red, Green, Blue) lights.

Let’s have some fun while learning important technology skills!

---

## What You’ll Need
1. A **ListPicker** component named **Connect** (for choosing a Bluetooth device).
2. A **Label** that says “Press Button to Speak” (just to guide you).
3. A **Button** named **Speak** (to start the Speech Recognizer).
4. A **Label** named **Command Given** (to display the phrase “Command Given:”).
5. A **Label** named **Displays the command** (this will show exactly what you spoke).
6. Non-visible components:
   - **BluetoothClient1**  
   - **Notifier1**  
   - **RGB1** (this is the module that controls the light’s color)  
   - **SpeechRecognizer1**

---

## Step-by-Step Guide

### 1. Connect to Bluetooth
1. **ListPicker (Connect).BeforePicking**  
   - **Block**: `set Connect.Elements to BluetoothClient1.AddressesAndNames`  
     - This fills the list with all available Bluetooth devices so you can pick the right one.

2. **ListPicker (Connect).AfterPicking**  
   - **Block**: `if BluetoothClient1.Connect(Selection) = true then ... else ...`  
     - **If True**: Show a **Notifier** message that says **"Connected"**.  
     - **If False**: Show a **Notifier** message that says **"Not Connected"**.

### 2. Speak to Control the Lights
1. **Button (Speak).Click**  
   - **Block**: `call SpeechRecognizer1.GetText`  
     - This opens the microphone so you can say a color (like “Red”, “Blue”, “Green”, or “Off”).

2. **SpeechRecognizer1.AfterGettingText**  
   - **Block**: 
     - Set `Displays the command`.Text to the **result** (what you just said).  
     - Then, check if the **result** contains specific color words:
       - If **result** contains "red" → Set **RGB1** to **Red** (for example, `RGB1` = (255, 0, 0)).  
       - If **result** contains "blue" → Set **RGB1** to **Blue** (e.g., (0, 0, 255)).  
       - If **result** contains "green" → Set **RGB1** to **Green** (e.g., (0, 255, 0)).  
       - If **result** contains "off" → Turn **RGB1** off (e.g., (0, 0, 0)).

### 3. Exiting the App
- **Screen1.BackPressed**  
  - **Block**: `close application`  
    - This will close the app when you press the back button.

---

## Real-Time Examples for Students
- **Home Lighting**: Imagine coming home and saying “Blue” to set a calm mood in your bedroom.  
- **Classroom Fun**: During a presentation, say “Red” to highlight an important point.  
- **DIY Projects**: Create a voice-activated light show for a science fair or school event!

---

## Where Else Can We Use It?
1. **Robotics**: Give a robot the power to change its LED eyes based on voice commands.  
2. **Party Decorations**: Want disco lights? Just say the color you want and watch them change!  
3. **Accessibility**: For people who can’t use their hands easily, voice control can be a big help.

---

## Encourage Creativity
- Feel free to add more colors (like “yellow”, “purple”, or “orange”)—just update the **if** checks with new RGB values.  
- You can also add a **Notifier** to say “Light turned Red!” or “Light turned Blue!” after each color change.  
- Use fun emojis like **🔴**, **🟢**, **🔵** to indicate the light color!

---

## Conclusion
Great job, everyone! You’ve just learned how to:
- Connect to a Bluetooth device.
- Use speech recognition to listen to commands.
- Change an RGB light’s color with your voice.

> **Remember**: “Your ideas, just like your voice, have the power to light up the world!”  

Now, let’s get creative and explore even more possibilities with our newly acquired coding superpowers. Have fun and keep experimenting!
