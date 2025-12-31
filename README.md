# You Are An Idiot! ☺ ☺ ☺

A Kotlin recreation of the classic early 2000s internet prank "You are an idiot" - bouncing, flashing windows with looping audio that multiply when you try to close them.

## ⚠️ WARNING

**This is a prank program that creates intentionally annoying behavior:**
- Spawns bouncing windows that flash black and white images
- Plays looping audio continuously
- **Spawns 4 additional windows every time you try to close one**
- Windows cannot be closed normally and will multiply rapidly
- Can create dozens of windows quickly, potentially freezing your system

**Only run this on your own computer where you accept the consequences. Do not use this to prank others without their consent.**

## What It Does

This program recreates the infamous "You are an idiot" browser trojan as a desktop application:

1. **Audio**: Continuously loops the "You are an idiot" song
2. **Visual**: Opens windows displaying alternating black and white smiley face images
3. **Movement**: Windows bounce around the screen at random speeds
4. **Multiplication**: Attempting to close a window spawns 4 more windows
5. **Random spawning**: Windows occasionally spawn new copies when bouncing off screen edges

## Requirements

- Java Runtime Environment (JRE) 8 or higher
- Kotlin runtime
- Required resources in `res/` folder:
  - `idiot.wav` - Audio file
  - `1.jpg` - Black image
  - `2.jpg` - White image

## Building

Build the project to a JAR artifact:
- Artifact name: `Idiot.jar`
- Output path: `out/artifacts/URN_Idiot/`

**Important**: Do not rename `Idiot.jar` as the code references this filename for resource path resolution.

## Running

On Windows, double click Idiot.jar.

On Linux:
```bash
java -jar Idiot.jar
```
or:
```bash
execjar Idiot.jar
```

**To stop the program:**
- Use Task Manager (Windows) / Activity Monitor (Mac) / System Monitor (Linux)
- Force quit Java processes
- **Closing windows normally will only make it worse!**

## 🛑 How to Stop It

1. **Windows**: Ctrl+Alt+Delete → Task Manager → End all Java processes
2. **Mac**: Cmd+Option+Esc → Force Quit Java
3. **Linux**: `killall java` in terminal

## Technical Details

### Components

**`SimpleAudioPlayer`**
- Loads and plays `idiot.wav` on continuous loop
- Based on Java Sound API
- Includes pause/resume/restart functionality (though not accessible during normal execution)

**`DisplayImage`**
- Creates JFrame windows with flashing images
- Each window has random speed (16-48 pixels per movement)
- Bounces off screen edges
- Uses timers for animation (333ms for color flip, 26ms for movement)

**Window Behavior**
- `defaultCloseOperation = DO_NOTHING_ON_CLOSE`
- `WindowListener` spawns 4 new windows on close attempt
- Random spawning chance when hitting screen edges

### Known Issues

- Exception handling in `SimpleAudioPlayer` has redundant code
- File paths are Windows-specific (`\\` separators)
- Running via Gradle IDE vs compiled JAR requires different path handling

## Educational Value

This project demonstrates:
- Kotlin/Java Swing GUI programming
- Audio playback with Java Sound API
- Timer-based animation
- Event handling (WindowListener)
- Resource path resolution in JAR files
- Classic internet culture/history

## Legal & Ethical Notice

This is a **recreation for educational/nostalgic purposes only**. 

- Do not deploy this as malware
- Do not use without informed consent of the computer owner
- Running this on others' computers without permission may violate computer fraud laws
- Intended for personal experimentation and learning only

## Historical Context

The original "You are an idiot" was a Flash-based browser trojan from the early 2000s that became infamous for its annoying behavior and difficulty to close. This Kotlin version recreates that experience as a standalone desktop application.

---

**Remember**: This is a PRANK program. Use responsibly and only on your own systems! ☺ ☺ ☺

---


Like what you see? Consider supporting me!

<a href="https://www.buymeacoffee.com/zytronium" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-blue.png" alt="Buy Me A Coffee" height="41" width="174"></a>
