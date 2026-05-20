# Coding

If circuits are the hardware side of a project, programming is the instruction side. You write steps, the board follows them, and the circuit does something because of it.

You do not need to know everything at once. The main ideas that come up over and over are:

- values
- variables
- data types
- loops
- scope
- inputs and outputs
- GPIO pins

## Variables

A **variable** is a name that stores a value so you can use it later.

Examples:

- a score in a game
- whether a button is pressed
- how long to wait before blinking again
- which pin an LED is connected to

A variable lets you stop repeating the same raw value everywhere.

## Data types

A **data type** tells you what kind of value something is.

Common beginner data types are:

- integer: whole numbers like `3` or `42`
- float: numbers with decimals like `3.14`
- boolean: `true` or `false`
- string: text like `"hello"`
- list or array: a group of values
- dictionary or object: named pieces of data grouped together

### Integer

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="int-mp">MicroPython</button>
    <button class="code-tab" data-tab="int-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="int-mp">

```python
count = 5
lives = 3
```

  </div>
  <div class="code-panel" data-tab="int-arduino">

```cpp
int count = 5;
int lives = 3;
```

  </div>
</div>

### Float

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="float-mp">MicroPython</button>
    <button class="code-tab" data-tab="float-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="float-mp">

```python
temperature = 21.5
wait_time = 0.5
```

  </div>
  <div class="code-panel" data-tab="float-arduino">

```cpp
float temperature = 21.5;
float waitTime = 0.5;
```

  </div>
</div>

### Boolean

A boolean answers a yes-or-no question.

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="bool-mp">MicroPython</button>
    <button class="code-tab" data-tab="bool-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="bool-mp">

```python
led_on = True
button_pressed = False
```

  </div>
  <div class="code-panel" data-tab="bool-arduino">

```cpp
bool ledOn = true;
bool buttonPressed = false;
```

  </div>
</div>

### String

A string is text.

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="string-mp">MicroPython</button>
    <button class="code-tab" data-tab="string-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="string-mp">

```python
name = "FreedomSTEM"
message = "Ready to blink"
```

  </div>
  <div class="code-panel" data-tab="string-arduino">

```cpp
String name = "FreedomSTEM";
String message = "Ready to blink";
```

  </div>
</div>

### List or array

A list or array holds multiple values in order.

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="list-mp">MicroPython</button>
    <button class="code-tab" data-tab="list-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="list-mp">

```python
colors = ["red", "yellow", "green"]
pins = [0, 1, 2]
```

  </div>
  <div class="code-panel" data-tab="list-arduino">

```cpp
String colors[] = {"red", "yellow", "green"};
int pins[] = {0, 1, 2};
```

  </div>
</div>

### Dictionary or object-style data

This is useful when you want one thing to hold several named values.

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="dict-mp">MicroPython</button>
    <button class="code-tab" data-tab="dict-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="dict-mp">

```python
player = {
    "name": "Person",
    "score": 12,
    "ready": True
}
```

  </div>
  <div class="code-panel" data-tab="dict-arduino">

```cpp
struct Player {
  String name;
  int score;
  bool ready;
};

Player player = {"Person", 12, true};
```

  </div>
</div>

## Variables and naming

Good variable names make code much easier to read.

Better examples:

- `button_pin`
- `reaction_time`
- `green_led`
- `is_ready`

Harder-to-read examples:

- `x`
- `thing`
- `data1`

Short names are not always wrong, but clear names help a lot when you come back later.

## Scope

**Scope** means where a variable exists and where you are allowed to use it.

A variable made at the top level is available in more places. A variable made inside a function stays inside that function.

That matters because two variables can have the same name in different places, but they are not always the same variable.

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="scope-mp">MicroPython</button>
    <button class="code-tab" data-tab="scope-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="scope-mp">

```python
count = 0
message = "ready"

def add_point():
    global count
    local_only = 1
    count = count + 1
    # local_only only exists inside this function
```

  </div>
  <div class="code-panel" data-tab="scope-arduino">

```cpp
int count = 0;
String message = "ready";

void addPoint() {
  int localOnly = 1;
  count = count + 1;
  // localOnly only exists inside this function
}
```

  </div>
</div>

Here is the main idea:

- `count` is made outside the function, so the function can work with it
- `local_only` or `localOnly` is made inside the function, so it stays inside the function
- if you try to use `local_only` outside the function, it will not be there
- if you make a brand-new variable inside a function, the rest of the program cannot see it

Scope matters because it helps you keep code organized. It also helps prevent one part of a program from accidentally changing something that belongs somewhere else.

## Loops

A **loop** repeats instructions.

That is important in electronics because a board often needs to keep checking buttons, updating lights, and reacting over and over.

### Infinite loop

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="loop-mp">MicroPython</button>
    <button class="code-tab" data-tab="loop-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="loop-mp">

```python
while True:
    print("still running")
```

  </div>
  <div class="code-panel" data-tab="loop-arduino">

```cpp
void loop() {
  Serial.println("still running");
}
```

  </div>
</div>

### Counted loop

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="for-mp">MicroPython</button>
    <button class="code-tab" data-tab="for-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="for-mp">

```python
for i in range(5):
    print(i)
```

  </div>
  <div class="code-panel" data-tab="for-arduino">

```cpp
for (int i = 0; i < 5; i++) {
  Serial.println(i);
}
```

  </div>
</div>

## Conditions

A **condition** lets the program choose what to do.

Examples:

- if the button is pressed, turn the LED on
- if the score is high enough, show a win message
- if the sensor value is low, sound an alarm

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="if-mp">MicroPython</button>
    <button class="code-tab" data-tab="if-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="if-mp">

```python
if button_pressed:
    print("Go")
else:
    print("Wait")
```

  </div>
  <div class="code-panel" data-tab="if-arduino">

```cpp
if (buttonPressed) {
  Serial.println("Go");
} else {
  Serial.println("Wait");
}
```

  </div>
</div>

## Functions

A **function** is a named block of code that does one job.

Functions help because they:

- break a big problem into smaller parts
- make code easier to read
- let you reuse the same job more than once

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="func-mp">MicroPython</button>
    <button class="code-tab" data-tab="func-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="func-mp">

```python
def blink_once():
    print("blink")
```

  </div>
  <div class="code-panel" data-tab="func-arduino">

```cpp
void blinkOnce() {
  Serial.println("blink");
}
```

  </div>
</div>

## What GPIO means

**GPIO** stands for **General Purpose Input/Output**.

That means a pin can be used in a general way instead of doing only one fixed job.

A GPIO pin can be used as:

- an **input** to read something, like a button
- an **output** to control something, like an LED

Examples:

- input: read whether a button is pressed
- output: turn a light on or off

## HIGH and LOW

When a pin is being used as a digital output, it is set to one of two states:

- **HIGH**
- **LOW**

For beginner projects, a good way to think about that is:

- `HIGH` means the pin is sending its active voltage
- `LOW` means the pin is sending `0V`

In many simple LED projects:

- `HIGH` can turn something on
- `LOW` can turn something off

That depends on how the circuit is wired, but for this kit that is the main pattern you will see.

## Input vs output pins

If a pin is set as an **input**, the board listens.

If a pin is set as an **output**, the board sends a signal.

That is why the same pin can do different jobs depending on the code.

<div class="code-tabs">
  <div class="code-tabs-nav">
    <button class="code-tab" data-tab="gpio-mp">MicroPython</button>
    <button class="code-tab" data-tab="gpio-arduino">Arduino</button>
  </div>
  <div class="code-panel" data-tab="gpio-mp">

```python
from machine import Pin

led = Pin(0, Pin.OUT)
button = Pin(1, Pin.IN, Pin.PULL_UP)
```

  </div>
  <div class="code-panel" data-tab="gpio-arduino">

```cpp
void setup() {
  pinMode(0, OUTPUT);
  pinMode(1, INPUT_PULLUP);
}
```

  </div>
</div>

## Digital, analog, and PWM

These three words sound similar at first, but they describe different kinds of signals.

### Digital

A **digital** signal uses clear states.

For the projects in this kit, that means:

- `LOW`
- `HIGH`

Examples:

- a button is pressed or not pressed
- an LED is off or on

### Analog

An **analog** value can change smoothly across a range instead of jumping between just two states.

Examples:

- a light sensor reading
- a temperature sensor voltage
- a knob that changes value gradually

The RP2040 can read analog values on certain pins, but that is not the focus of this kit.

### PWM

**PWM** stands for **Pulse Width Modulation**.

PWM uses a digital pin, but it switches that pin on and off so quickly that the result can feel more like an analog change.

That is why PWM is useful for things like:

- fading an LED
- changing brightness
- creating smoother light animations

So even though PWM is built from fast digital switching, it can create effects that look smooth.

## Common extra jobs a GPIO pin can do

Many RP2040 pins can also do more specialized jobs, including:

- **PWM** for dimming LEDs or controlling speed
- **I2C** for talking to some sensors and displays
- **SPI** for fast communication with some modules
- **UART** for serial communication
- **ADC** on certain pins for reading analog voltages

For beginner projects, you will use pins as simple digital input or output pins.

That means:

- you do **not** need I2C
- you do **not** need SPI
- you do **not** need UART

Those extra systems are useful later when you connect more advanced parts, but simple input and output work fine with plain GPIO by itself.

For this kit, we will keep it simple:

- we will use **HIGH** and **LOW** for normal digital on/off control
- we will use **PWM** for fades and smooth lighting effects
- we will **not** need I2C, SPI, or UART for the main projects here

## RP2040-Zero pin guide

The RP2040 chip has many functions, but the `RP2040-Zero` board brings a smaller set of easy-to-reach pins out to the edges. The list below focuses on the pins most people will actually use on the board headers.

### Power and ground pins

| Pin | What it is for | Beginner use |
|---|---|---|
| `5V` / `VBUS` | 5-volt power from USB or external 5V input | Powering the board |
| `3V3` | regulated 3.3V power | Powering 3.3V parts |
| `GND` | ground reference | The return path for almost every circuit |

### Digital GPIO pins

| Pin | What it can do | Good beginner use |
|---|---|---|
| `GP0` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP1` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP2` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP3` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP4` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP5` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP6` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP7` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP8` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP9` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP10` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP11` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP12` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP13` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP14` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |
| `GP15` | digital I/O, PWM, UART, I2C, SPI options | LED, button, general output |

### Analog-capable pins

| Pin | What it can do | Good beginner use |
|---|---|---|
| `GP26` / `ADC0` | digital I/O, analog input, PWM | reading analog sensors later on |
| `GP27` / `ADC1` | digital I/O, analog input, PWM | reading analog sensors later on |
| `GP28` / `ADC2` | digital I/O, analog input, PWM | reading analog sensors later on |
| `GP29` / `ADC3` | digital I/O, analog input, PWM | advanced analog reading and extra GPIO use |

## A simple way to remember the pins

You do not need to memorize every special feature right now.

A good beginner way to think about the board is:

- `3V3` gives power
- `GND` gives the return path
- `GP` pins do the thinking and signaling
- `GP26` to `GP29` are extra useful because they can also read analog values

## Good beginner habits with GPIO

- Pick one pin and stay consistent in your wiring and code
- Label your pins in code with clear variable names
- Check whether a pin is supposed to be an input or an output
- Do not connect LEDs directly without a resistor
- Start with simple pins like `GP0`, `GP1`, or `GP2` before worrying about special features

## Final takeaway

Programming and circuits fit together really well.

- variables store values
- data types describe what those values are
- loops keep the board running
- conditions help the board make choices
- GPIO pins let code interact with the real world

Once those ideas click, the projects in this kit start to make much more sense.
