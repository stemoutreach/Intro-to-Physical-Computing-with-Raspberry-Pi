# 🧭 Session 1: Getting Started with Raspberry Pi 3 & Physical Computing

**Theme:** _“Code meets the real world!”_

## 🧠 Objectives
- Understand Raspberry Pi 3 as a full computer
- Write and run your first Python program
- Learn what GPIO pins are and what they do
- Understand how breadboards help connect circuits
- Use GPIOZero to blink an LED

---

## 🧩 Session Flow

### 1. Welcome & Icebreaker (5–10 min)
Prompt: “If your robot could do anything, what would it do?”

### 2. What Is the Raspberry Pi 3? (10 min)
- Overview of ports (USB, HDMI, GPIO, SD card)
- Differences from a regular laptop
- Introduce concept of general-purpose computing and sensors

    <img src="https://github.com/stemoutreach/Intro-to-Physical-Computing-with-Raspberry-Pi-3/blob/main/images/Introduction-of-Raspberry-Pi-3-Model-B.jpg" width="400" > 

### 3. Hello Python! Your First Program (10 min)
- Open Thonny (or IDLE)
- Type and run:
```python
print("Hello, world!")
```

### 4. Intro to GPIO & Breadboarding (10–15 min)
- What are GPIO pins?
- Why and how to use a breadboard
- Show how a Pi pin can power or control an LED

### 5. Blink an LED Using GPIOZero (30 min)
- Wire LED + resistor to GPIO pin using a breadboard
- Use the gpiozero library for easy code

**Example Code:**
```python
from gpiozero import LED
from time import sleep

led = LED(17)

while True:
    led.on()
    sleep(1)
    led.off()
    sleep(1)
```

### 6. Wrap-Up & Experimentation (10 min)
- Change blink speed
- Try other GPIO pins
- Add second LED (bonus)

---

### ✅ Materials Needed
- Raspberry Pi 3 with power supply
- Monitor, keyboard, mouse
- Breadboard + jumper wires
- LED + resistor (220Ω–330Ω)
