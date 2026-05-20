# 6: PWM Fade

This project makes one LED fade up and down instead of only being fully on or fully off.

This is your first “not just ON/OFF” output. The LED is still switching on and off, but PWM switches it so fast that your eyes see it as different brightness levels.

Coding ideas you will use:

- an **infinite loop** to keep the effect running
- a **counted loop** (`for duty in range(...)`) to sweep brightness up and down
- a **variable** (`duty_step`) to control how smooth the fade is

Learn more (optional):

- [PWM (Digital, analog, and PWM)](../programming-basics.md#pwm)
- [Loops (counted loop)](../programming-basics.md#counted-loop)

## Goal

Make an LED slowly brighten and dim.

## Parts you need

- 1 LED
- 1 resistor
- jumper wires
- breadboard
- RP2040-Zero

!!! warning "Important: choose the right resistor"
    Your kit has **150Ω** and **100Ω** resistors.
    
    - For a **red or yellow** LED, use **150Ω**
    - For a **green, blue, or white** LED, use **100Ω**
    
    Using the wrong resistor can damage an LED.

## Wiring idea

Build it first, then compare your setup to the picture. Did you connect each part to the pin you meant to use?

Use one GPIO pin to control the LED through a resistor.

!!! tip "Hint"
    The circuit is the same as what you built in `5: Blink with Code`.

Example path:

`GPIO -> resistor -> LED -> GND`

![Wiring diagram showing `GP7 (GPIO 7)` connected through a resistor to an LED, with the LED returning to `GND` for a PWM fading project](wiring.jpg){ .spoiler-img width="50%" }

## What PWM means

PWM stands for **Pulse Width Modulation**.

That sounds more complicated than it is. The board turns the pin on and off very quickly. By changing how long it stays on during each tiny cycle, the LED can look brighter or dimmer to your eyes.

You are not changing the LED into a different kind of part. You are changing how much power it seems to get over time.

## Code

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="int-mp">MicroPython</button>
    <button class="code-tab" data-tab="int-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="int-mp">

<div class="admonition note">
  <p class="admonition-title">Pin reminder</p>
  <p>Wired your LED to a different GPIO pin? Update <code>LED_GPIO</code> in the code below to match your wiring.</p>
</div>

```python
from machine import Pin, PWM
import time

LED_GPIO = 7

# Set up PWM on the chosen GPIO pin
pwm_led = PWM(Pin(LED_GPIO))
# Set the frequency (1000Hz is standard for LEDs)
pwm_led.freq(1000)

print("Starting PWM fade on GPIO", LED_GPIO, "...")
# Duty cycle ranges from 0 to 65535 (16-bit)
duty_step = 500

while True:
    # Fade Up
    for duty in range(0, 65536, duty_step):
        pwm_led.duty_u16(duty)
        time.sleep(0.01)
        
    # Fade Down
    for duty in range(65535, -1, -duty_step):
        pwm_led.duty_u16(duty)
        time.sleep(0.01)
```

  </div>
  <div class="code-panel" data-tab="int-arduino">

```cpp
Arduino Code Coming Soon
```

  </div>
</div>
## What to notice

- The LED is still blinking on and off very fast, but it looks smooth to us.
- A small duty cycle looks dim.
- A large duty cycle looks bright.
- PWM is useful when you want more than just ON or OFF.

## Try this

- Make the fade slower
- Make the fade faster
- What do different `duty_step` or `pwm_led.freq` values do?
- See if different LED colors look different at the same brightness level
