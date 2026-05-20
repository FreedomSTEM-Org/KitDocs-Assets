# 8: Smooth Chase with PWM

This project takes the basic LED chase and makes it look smoother by fading between the LEDs.

This combines two ideas: a chase pattern (turning different LEDs on at different times) and PWM (so brightness can change smoothly instead of jumping).

Coding ideas you will use:

- a **list** of LEDs so you can loop over them
- an **infinite loop** to keep the animation running
- a **counted loop** (`for i in range(...)`) to compute a brightness value for each LED

Learn more (optional):

- [PWM](../programming-basics.md#pwm)
- [List or array](../programming-basics.md#list-or-array)
- [Loops (counted loop)](../programming-basics.md#counted-loop)

## Goal

Create a moving light effect across three LEDs using PWM.

## Parts you need

- 3 LEDs
- 3 resistors
- jumper wires
- breadboard
- RP2040-Zero

!!! warning "Important: choose the right resistor"
    Your kit has **150Ω** and **100Ω** resistors.
    
    - For a **red or yellow** LED, use **150Ω**
    - For a **green, blue, or white** LED, use **100Ω**
    
    Using the wrong resistor can damage an LED.

## Wiring idea

Build it first, then compare your setup to the diagram. Did you connect each part to the pin you meant to use?

Use the same wiring as the three-LED chase project.
Each LED should have its own resistor and its own path back to `GND`.

!!! tip "Hint"
    The circuit is the same as what you built in `7: LED Chase`.

Example pins: `GP6 (GPIO 6)`, `GP7 (GPIO 7)`, and `GP8 (GPIO 8)`.

![Wiring diagram showing three LEDs connected to `GP6 (GPIO 6)`, `GP7 (GPIO 7)`, and `GP8 (GPIO 8)` through separate resistors, all returning to `GND` for a chase animation](wiring.jpg){ .spoiler-img width="50%" }

## Code


<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="int-mp">MicroPython</button>
    <button class="code-tab" data-tab="int-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="int-mp">

<div class="admonition note">
  <p class="admonition-title">Pin reminder</p>
  <p>Wired your LEDs to different GPIO pins? Update <code>LED_GPIOS</code> in the code below to match your wiring.</p>
</div>

```python
import machine
import time

# Choose the GPIO pins your LEDs are connected to.
LED_GPIOS = [6, 7, 8]

# Set up PWM on those pins
leds = [machine.PWM(machine.Pin(gpio)) for gpio in LED_GPIOS]

for l in leds:
    l.freq(1000)

# --- ADJUST THESE TO CHANGE THE FEEL ---
speed = 400         # Lower is slower (try 200 for a real crawl)
width = 30000       # Higher makes the "trail" longer
# ---------------------------------------

max_val = 65535
position = 0

print("Slow fade across GPIO pins:", LED_GPIOS)

while True:
    # 1. Move the wave position slowly
    # We use (max_val + width) so the light can fully "fade out" 
    # before restarting on the first pin
    position = (position + speed) % (max_val + width)
    
    for i in range(len(leds)):
        # 2. Give each LED a fixed spot on the line
        # LED 0 is at 0, LED 1 is at 21845, LED 2 is at 43690
        led_spot = i * (max_val // (len(leds) - 1))
        
        # 3. How far is the "wave" from this LED?
        distance = abs(position - led_spot)
        
        # 4. If the wave is close, turn on the light
        if distance < width:
            # Linear math: Brightness drops as distance increases
            brightness = int((1 - (distance / width)) * max_val)
            leds[i].duty_u16(brightness)
        else:
            leds[i].duty_u16(0)
    
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

- Brightness can change over time, not just switch on and off
- PWM makes animation feel smoother
- Small timing changes can make the whole effect feel very different

## Try this

- Make the fade slower for a softer look
- Make the fade faster for a sharper look
- Try red, yellow, and green together for a different feel
