# 🔌 Session 2: Inputs, Outputs, Movement, and Python Fundamentals

**Theme:** _“Talk to your circuit—and understand the code that powers it!”_

## 🧠 Objectives
- Review Python fundamentals (variables, conditionals, loops, functions)
- Use buttons as inputs to control LEDs
- Explore PWM to fade LEDs
- Introduce servo and DC motors
- Build hands-on circuits while learning to code

---

## 🧩 Session Flow

### 1. Quick Recap & Warm-Up (5–10 min)
- What did we build in Session 1?
- What did the LED do, and how did Python control it?

---

### 2. Python Fundamentals (15 min)

#### 🔸 Variables & Print
```python
name = "Raspberry Pi"
print("Hello, " + name)
```

#### 🔸 If Statements
```python
light_on = True
if light_on:
    print("The light is on!")
```

#### 🔸 Loops & Functions with LED
```python
from gpiozero import LED
from time import sleep

led = LED(17)

def blink_led(times):
    for _ in range(times):
        led.on()
        sleep(0.5)
        led.off()
        sleep(0.5)

blink_led(3)
```

---

### 3. Add a Button – GPIO Input (15 min)
- Wire a button and LED
- Control LED with button using `gpiozero.Button`

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

### 4. Explore PWM – LED Brightness (10–15 min)
- Use `PWMLED` to fade LED in and out

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

### 5. Motor Introduction – Servo & DC (20+ min)

#### Servo Motor
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

#### DC Motor
- Use only if driver or motor HAT is available

---

### 6. Explore & Build (15 min)
- Mix & match: button + PWM, functions + motors, etc.
- Let students try ideas and share outcomes

---

## ✅ Materials Checklist
- Raspberry Pi 3 with monitor, keyboard, mouse
- Breadboards, jumper wires
- LEDs, resistors
- Buttons
- Servo motors and/or DC motors
- External power (if using DC motors)
- Optional: potentiometers, buzzers
