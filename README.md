<h1 align="center">Adaptive Level Manager</h1>

<p align="center">
  <img src="https://github.com/kandelucky/Adaptive-Level-Manager-wiki/blob/main/Images/Logo_text.jpg" alt="Adaptive Level Manager">
</p>

## Overview

**Adaptive Level Manager** allows you to easily manage the level system in your Unity project. This system lets you define when, where, and how levels are unlocked or locked, what criteria players must meet, and how their progress is evaluated. You can also add unique parameters to extend level data with custom settings.

### 🎥 Video Tutorial:
[**Watch here**](https://github.com/kandelucky/Adaptive-Level-Manager-wiki/wiki/Home/google.com)

---

## ⭐ Key Features of Adaptive Level Manager:

- **Flexible level unlock system** – Unlock levels based on stars, scores, or no criteria at all.  
- **Customizable level-specific settings** – Customize individual levels by overriding the default parameters.  
- **Extendable parameters** – Add unique data points specific to each level.  
- **Player progress control** – Manage stars, scores, mistakes, and time limits.  
- **Multiple level statuses** – Locked, Unlocked, Win, Lose, Done.  
- **Notifications** – Get notified when a new level is unlocked or locked.  
- **ScriptableObject architecture** – Simplifies data initialization and sharing across scenes.  
- **Clearly commented code** – The code is written with clear documentation.  

---

## 🎮 Ready-to-Use Demo Versions:

<p align="center">
  <img src="https://github.com/kandelucky/Adaptive-Level-Manager-wiki/blob/main/Images/Social%202.jpg" alt="Demos">
</p>

Adaptive Level Manager includes **ready-made demo versions**, such as level lists and a **scrollable level map**, which can be customized to fit your needs. These demos also include game scenes that demonstrate how the system works in practice. This ensures a **quick start** for your project and helps elevate your game.

### 🔹 **Demo 1: Shared Scene for All Levels**
- A single scene (Menu + one shared game scene for all levels).  
- Uses **LevelData ScriptableObject** to pass different information to the same game scene.

### 🔹 **Demo 2: Unique Scenes for Each Level**
- Each level has its own unique scene (Menu + 10 distinct game scenes).  
- Uses **LevelData ScriptableObject** to pass level-specific information for **individual** game scenes.

### 🎮 **Demo Game Scene**
Both demo projects include a **demo game scene**, where you can see all the core functionalities of the **Level Manager** in action. This allows you to test unlocking mechanisms, scoring systems, mistakes handling, and other essential features in real-time.

---

## 🛠️ Default Configurations

Demo projects include **five predefined** `ScriptableObject`-based configurations (`AdaptiveLevelSettingsData`):

1. **Stars** – Levels unlock **only** based on the number of stars.  
2. **Score** – Levels unlock **only** based on score progress.  
3. **All Open** – All levels are open, **no restrictions**.  
4. **Stars - All Open** – All levels are open and **display stars**.  
5. **Score - All Open** – All levels are open and **display scores**.  

Additionally, the demo projects include **custom level unlocking configurations** using `AdaptiveLevelSettingsData`. These configurations allow you to **override the Level Manager's default settings** for specific levels based on:

- **Stars** 🌟  
- **Scores** 🏆  
- **No restrictions** (open level) 🔓  

This flexibility enables you to test how **default or custom rules** affect level progression.

---

## ⚙️ Requirements

✅ **This project requires** `TextMesh Pro (TMPro)`.  
📌 **Make sure to install it via the Unity Package Manager** before using this system.

✅ **This project includes UI sprites from** [**Kenney.nl**](https://kenney.nl/) **which are licensed under CC0 (public domain).**

---

## ❤️ A Note from the Developer

**Adaptive Level Manager** was made with love by someone who enjoys coding and creating for **Unity**.

💡 **I am open to any feedback or suggestions** you may have and would greatly appreciate your input to make it even better!  

📩 Feel free to contact me at **kandelucky.dev@gmail.com**.

---
## TODO: Future Improvements

- **Modularize Code** – Separate UI updates, unlocking logic, and notifications.  
- **Refactor & Clean Up** – Use helper methods, constants, and remove magic numbers.  
- **Improve Error Handling** – Implement a structured logging system. 
