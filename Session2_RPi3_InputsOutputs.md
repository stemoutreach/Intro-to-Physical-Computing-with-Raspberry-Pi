# 🔌 Session 2: Inputs & Outputs with Raspberry Pi 3

**Theme:** _“Make your Pi respond to YOU!”_

## Objectives:
- Learn about GPIO input vs output
- Wire a button and LED to interact with your circuit
- Understand pull-up/down resistors and digital logic

## Activities:
### 1. Recap & Warm-Up (10 min)

### 2. Review GPIO & Digital Signals (10 min)
- Quick diagram: ON vs OFF, HIGH vs LOW

### 3. Wire a Button and LED (15 min)

### 4. Write Python Code to Control LED with Button (30 min)

## Sample Code:
```python
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BCM)
GPIO.setup(18, GPIO.OUT)
GPIO.setup(17, GPIO.IN, pull_up_down=GPIO.PUD_DOWN)

try:
    while True:
        if GPIO.input(17) == GPIO.HIGH:
            GPIO.output(18, GPIO.HIGH)
        else:
            GPIO.output(18, GPIO.LOW)
        time.sleep(0.1)
except KeyboardInterrupt:
    GPIO.cleanup()
```
