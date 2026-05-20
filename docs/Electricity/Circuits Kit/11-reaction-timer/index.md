# 11: Reaction Timer

This project turns your circuit into a game.

This is an input + timing game. The board controls an LED, then measures how long it takes you to press the button after the light appears.

Coding ideas you will use (once the code is added):

- a **loop** to run multiple rounds
- **timing** to measure reaction time
- **randomness** so you cannot predict the exact moment

Learn more (optional):

- [Loops](../programming-basics.md#loops)
- [Input vs output pins](../programming-basics.md#input-vs-output-pins)

## Goal

Wait for the light, then press the button as fast as you can.

## Parts you need

- 1 LED
- 1 resistor
- 1 pushbutton
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

Suggested setup:

- LED on `GP0 (GPIO 0)`
- button on `GP1 (GPIO 1)`

Use the button with `Pin.PULL_UP`, with the other side connected to `GND`.

![Wiring diagram showing one LED output and one button input connected to the RP2040-Zero for a reaction game]()

## Code

!!! note "Pin reminder"
    If you wire different pins than the suggested setup, make sure the GPIO numbers in your code match your wiring.

```
// placeholder
```

## What to notice

- The random wait makes the game less predictable
- The board can measure short time differences
- The shell can show your score

## Challenge

Try five rounds and see which reaction time is your fastest.
