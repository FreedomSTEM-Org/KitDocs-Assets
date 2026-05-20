# 10: Color Picker

This project lets buttons choose which LED color turns on.

This is your first “inputs + outputs” code project. The buttons are **inputs** your code reads, and the LEDs are **outputs** your code controls.

Coding ideas you will use (once the code is added):

- a **loop** so the board can check the buttons again and again
- **conditions** (`if`) to decide which LED should turn on

Learn more (optional):

- [Input vs output pins](../programming-basics.md#input-vs-output-pins)
- [Conditions](../programming-basics.md#conditions)
- [Loops](../programming-basics.md#loops)

## Goal

Press one button to turn on one color and another button to turn on a different color.

## Parts you need

- 2 LEDs
- 2 resistors
- 2 pushbuttons
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

- red LED on `GP0 (GPIO 0)`
- blue LED on `GP1 (GPIO 1)`
- button A on `GP2 (GPIO 2)`
- button B on `GP3 (GPIO 3)`

For the buttons, use one side to connect to `GND` and let the code use pull-up resistors.

![Wiring diagram showing two LEDs as outputs and two pushbuttons as inputs to the RP2040-Zero]()

## Code

!!! note "Pin reminder"
    If you wire different pins than the suggested setup, make sure the GPIO numbers in your code match your wiring.

```
// placeholder
```

## What to notice

- Buttons are inputs
- LEDs are outputs
- The code checks the buttons again and again in a loop

## Challenge

Change the colors or make both LEDs turn on when both buttons are pressed.
