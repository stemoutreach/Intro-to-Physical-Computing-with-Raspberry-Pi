# 🧭 Session 1: Getting Started with Raspberry Pi 3 & Physical Computing

**Theme:** _“Code meets the real world!”_

## Objectives:
- Understand what the Raspberry Pi 3 is and how it works as a full computer
- Write your first Python program
- Learn what GPIO pins do
- Blink an LED using Python and GPIO

## Activities:
### 1. Welcome & Icebreaker (10 min)
Prompt: “If you could automate one thing in your life, what would it be?”

### 2. What is a Raspberry Pi? (10 min)
- Explain Pi 3 as a full mini computer
- Overview of USB ports, HDMI, GPIO, etc.

### 3. Python Hello World (15 min)
- Open Thonny (or IDLE)
- Run: `print("Hello, World!")`

### 4. Blink an LED (40 min)
- Wire an LED to GPIO pin using breadboard
- Control it using Python

## Sample Code:
```python
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BCM)
GPIO.setup(18, GPIO.OUT)

while True:
    GPIO.output(18, GPIO.HIGH)
    time.sleep(0.5)
    GPIO.output(18, GPIO.LOW)
    time.sleep(0.5)
```
