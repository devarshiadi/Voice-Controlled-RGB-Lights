"With your voice, you can paint the world in any color you imagine! 🎨✨"

## Introduction
In this fun project, we’ll create a **Voice Controlled RGB Light** system. By simply speaking a color, your RGB lights will change to that color! This tutorial is designed to spark creativity in kids (and adults, too!) and show how easy it is to connect **Bluetooth** and **Speech Recognition** to control **RGB** lights in real time.

---

## Step-by-Step Guidance

### 1. **Set Up Your Components**
1. **ListPicker**: Name it **Connect** (this will handle the Bluetooth device selection).
2. **Label**: Text = "Press Button to Speak" (just for design and guidance).
3. **Button**: Name it **Speak** (to trigger the Speech Recognizer).
4. **Label**: Name it **Command Given** (to display "Command Given:" or something similar).
5. **Label**: Name it **Displays the command** (this will show the exact text spoken by the user).
6. **Non-visible components**:
   - **BluetoothClient1**
   - **Notifier1**
   - **RGB1** (the module or extension that actually sets your RGB light color)
   - **SpeechRecognizer1**

### 2. **Connect to Bluetooth**
1. **ListPicker (Connect).BeforePicking**  
   - **Blocks**:  
     - Set `Connect.Elements` to `BluetoothClient1.AddressesAndNames`.  
       This populates the list of available Bluetooth devices.

2. **ListPicker (Connect).AfterPicking**  
   - **Blocks**:  
     - Use an `if` statement to check whether `BluetoothClient1.Connect(Selection)` is **true**.  
       - If **true** → `Notifier1.ShowAlert("Connected")`  
       - Else → `Notifier1.ShowAlert("Not Connected")`

### 3. **Speaking & Capturing Voice Command**
1. **Button (Speak).Click**  
   - **Blocks**:  
     - Call `SpeechRecognizer1.GetText`  
       This will open the device’s speech interface so you can speak a command (e.g., "Red", "Blue", "Green", "Off").

2. **SpeechRecognizer1.AfterGettingText**  
   - **Blocks**:
     - Set `Displays the command`.Text to `get result` (the recognized speech).
     - Use `if/else if` blocks to check if `get result` **contains** a color keyword:
       - If `result` **contains** "red"  
         - Call `RGB1` (value = 255 for Red; or set the correct RGB values if your module requires different parameters)  
         - (Optional) Set another label to say `"RGB1 = Red"` or simply confirm "Red light turned on!"
       - Else if `result` **contains** "blue"  
         - Call `RGB1` (value for Blue, for instance 255 in the blue channel)  
         - Label: `"RGB1 = Blue"`
       - Else if `result` **contains** "green"  
         - Call `RGB1` (value for Green)  
         - Label: `"RGB1 = Green"`
       - Else if `result` **contains** "off"  
         - Call `RGB1` (value = 0 or off command)  
         - Label: `"RGB1 = Off"`

### 4. **Screen Navigation**
- **Screen1.BackPressed**  
  - **Blocks**: `close application`  
    This ensures your app closes gracefully when the back button is pressed.

---

## Where Can We Use This?
1. **Home Automation**: Control your smart bulbs or LED strips in your bedroom or living room with voice commands.
2. **DIY Robot Projects**: Make a robot’s LED change color based on voice instructions, giving it an interactive feel.
3. **Classroom Projects**: Teach kids about **speech recognition**, **Bluetooth communication**, and **basic coding** all at once.
4. **Art Installations**: Voice-controlled light shows for a gallery or an event.

---

## Real-Time Examples
- **“Say ‘Red’ to turn your LED strip red”** – Perfect for setting a mood or theme lighting at home.  
- **“Say ‘Blue’ to show you’re feeling calm”** – Use color therapy in a fun, interactive way.  
- **“Say ‘Off’”** – Instantly turn off the lights when you’re done.

---

## Emojis to Spice Up Your Project
- **🎨** for color changes  
- **🔴** **🔵** **🟢** to represent red, blue, green lights  
- **🔊** for voice commands  
- **🤖** for that futuristic vibe  

---

## Conclusion
This simple **Voice Controlled RGB Light** project shows how powerful and creative block-based coding can be. You’ve combined **Bluetooth** connectivity, **Speech Recognition**, and an **RGB controller** to make something interactive and fun. Let your imagination run wild—maybe next time, you’ll add more voice commands, different color patterns, or even animations!

> **Remember**: “Your voice can brighten someone’s day—why not your room too?” 🌟  

Happy coding and have fun experimenting with your new voice-controlled color palette!  
