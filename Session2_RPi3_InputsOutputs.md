# 🔌 Session 2: Inputs, Outputs, and Movement with GPIOZero

**Theme:** _“Talk to your circuit—and make it move!”_

## 🧠 Objectives
- Understand buttons as input devices
- Combine button input and LED output
- Learn about PWM (Pulse Width Modulation) for LED brightness
- Introduce motors (servo and DC)
- Encourage exploration and experimentation

---

## 🧩 Session Flow

### 1. Quick Recap & Warm-Up (5–10 min)
- What did you build last time?
- What did the LED do and how did Python control it?

---

### 2. Add a Button – GPIO Input (15 min)
- Wire a button using a pull-down resistor or `gpiozero.Button()`
- Control an LED based on button press

**Sample Code:**
```python
from gpiozero import LED, Button
from signal import pause

led = LED(17)
button = Button(18)

button.when_pressed = led.on
button.when_released = led.off

pause()
```

---

### 3. Explore PWM – LED Brightness (10–15 min)
- Introduce PWM as variable power
- Show how to fade or dim an LED using `PWMLED`

**Sample Code:**
```python
from gpiozero import PWMLED
from time import sleep

led = PWMLED(17)

while True:
    for brightness in range(0, 101, 5):
        led.value = brightness / 100
        sleep(0.05)
```

---

### 4. Motor Introduction – Servo & DC (20+ min)

#### Option A: Servo Motor
- Explain rotation in degrees
- Connect servo (3 wires: GND, power, signal)

**Sample Code:**
```python
from gpiozero import Servo
from time import sleep

servo = Servo(17)

while True:
    servo.min()
    sleep(1)
    servo.max()
    sleep(1)
```

#### Option B: DC Motor
- If motor driver available (like L298N or motor HAT)
- Show on/off or directional movement if possible

---

### 5. Explore & Build (15 min)
- Encourage combinations: button + PWM, button-controlled servo, etc.
- Let students pick what they want to try
- Help troubleshoot and spark ideas

---

## ✅ Materials Checklist
- Raspberry Pi 3 with monitor, keyboard, mouse
- Breadboards, jumper wires
- LEDs, resistors
- Buttons
- Servo motors and/or DC motors
- External power (if using DC motors)
- Optional: potentiometers, extra LEDs, buzzers
