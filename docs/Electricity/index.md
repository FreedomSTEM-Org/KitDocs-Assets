# Electricity

Electricity is everywhere: lights, game systems, doorbells, chargers, and computers all use it. This page starts small and builds up step by step, from atoms to the main ideas you will use in circuits: voltage, current, resistance, and power.

![Quincylus, Public domain, via Wikimedia Commons](https://upload.wikimedia.org/wikipedia/commons/9/9a/LEDCircuit.PNG){width="50%"}

## Matter is made of atoms

Everything around us is made of atoms. An atom has two main parts:

- A **nucleus** at the center
- A surrounding **electron cloud**

Inside the nucleus are:

- **Protons**, which have a positive charge
- **Neutrons**, which have no charge

Outside the nucleus are:

- **Electrons**, which have a negative charge

Electrons are much lighter than protons and neutrons, and in many materials they are the particles that can move around most easily. That movement is what matters most for basic electricity.

![AG Caesar, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons](https://upload.wikimedia.org/wikipedia/commons/8/80/Atom_Diagram.svg){width="50%"}

## Positive and negative charge

Electric charge comes in two kinds:

- **Positive**
- **Negative**

Opposite charges attract each other, and like charges repel each other. A negatively charged electron is attracted toward positive charge and pushed away by negative charge.

That push-and-pull is one of the reasons electrons can be driven through a circuit.

## What electricity is

In basic circuits, **electricity is the movement of electrons through a material**.

Not every material lets electrons move easily. In some materials, electrons move fairly well. In others, they are held tightly in place.

- **Conductors** let electrons move more easily
- **Insulators** resist electron movement

Examples:

- Copper wire is a good conductor
- Rubber, plastic, and glass are good insulators

When electrons move through a complete path, we call that **electric current**.

## A circuit needs a complete path

A circuit is a loop that gives electrons a path to follow.

For current to flow, there must be:

- A **source** of electrical energy, such as a battery
- A **path**, such as a conductor like metal wire
- A **load**, such as a light, motor, or resistor
- A **complete loop** back to the source

If the path is broken, current stops.

That is what a switch does. When the switch is open, the path is broken. When the switch is closed, the path is complete.

## Series and parallel

There are two very common ways to arrange parts in a circuit:

- **Series**
- **Parallel**

In a **series circuit**, parts are connected one after another in a single path.

Example:

`battery -> switch -> resistor -> LED -> battery`

In a series circuit:

- there is one main path for current
- if one important connection breaks, the whole path stops working
- each part affects the others in that same path

In a **parallel circuit**, there is more than one path for current to follow.

Example idea:

- one button path can light an LED
- a second button path can also light the same LED

In a parallel circuit:

- current can have more than one route
- one path can sometimes keep working even if another path is open
- it is useful when you want choices or branches in a circuit

Real-world examples:

- Old-style holiday lights often caused trouble because one broken bulb could interrupt a series string
- Rooms in a house are wired in parallel so one light turning off does not shut off everything else

![Azarboon, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons](https://upload.wikimedia.org/wikipedia/commons/f/f9/Series_vs_parallel_components.png){width="50%"}

## Where batteries fit in

A battery does not "store electricity" in the sense of keeping electrons packed up like water in a bottle. A more accurate way to think about it is:

- A battery stores **chemical energy**
- That chemical energy creates a **difference in electric potential**
- That potential difference pushes charges through a circuit when a path is available

Inside a battery, chemical reactions separate charge in a way that creates two terminals:

- A terminal with lower electric potential
- A terminal with higher electric potential

When you connect those terminals through a circuit, electrons are pushed through the external path.

Real-world example:

- A AA battery in a flashlight provides the push that moves electrons through the bulb or LED circuit
- A phone battery does the same thing on a larger and more carefully controlled scale

## Voltage

**Voltage** is the electrical push that drives charge through a circuit.

You can think of voltage as the amount of "push per charge" available between two points.

The unit of voltage is the **volt**, written as `V`.

Examples:

- A single AA battery is about `1.5 V`
- A small coin cell battery might be `3 V`
- A typical USB power source is `5 V`

Higher voltage means there is a stronger push available to move charge, but that does not automatically tell you how much current will flow. Current also depends on the rest of the circuit.

## Current

**Current** is the rate at which electric charge flows through a circuit.

In metal wires, the moving particles are electrons. In some diagrams, you will also see arrows showing current from positive to negative. That is a standard way people draw circuits, even though the electrons themselves move the other way.

The unit of current is the **ampere**, shortened to **amp**, written as `A`.

Examples:

- A small LED circuit might use a few milliamps
- A phone charging cable might carry around `1 A` to `3 A`, depending on the device and charger
- A starter motor in a car can draw a very large current for a short time

One milliamp is:

`1 mA = 0.001 A`

## Resistance

**Resistance** is how much a material or component opposes the flow of current.

The unit of resistance is the **ohm**, written as `Ω`.

A resistor is a component designed to add a known amount of resistance to a circuit. Resistors are useful because they help control current.

Real-world examples:

- A resistor in series with an LED keeps too much current from flowing and burning the LED out
- A long, thin wire has more resistance than a short, thick wire of the same material
- The filament in an old incandescent bulb resists current so strongly that it gets hot enough to glow

## Conductors and insulators

It helps to connect resistance to real materials.

- Copper has low resistance, which is why it is used in wires
- Rubber has very high resistance, which is why it is used around wires as insulation
- Water by itself is not a great conductor, but water with dissolved salts and minerals can conduct much better

In practical circuits, we want current to go where we choose, which is why wires are metal on the inside and insulated on the outside.

## Simple logic with circuits

Circuits can also help us think about **logic**, which means rules for when something should happen.

For example:

- Should a light turn on if **either** button is pressed?
- Should it turn on only if **both** buttons are pressed?

That is where basic logic gates come in.

## OR gate

An **OR** idea means the output turns on if this is true:

- button A is pressed, **or**
- button B is pressed, **or**
- both are pressed

If you build two button paths in parallel so either one can complete the circuit, you are making something that acts like an OR gate.

Real-world example:

- A game could start if player 1 presses a button or player 2 presses a button

## AND gate

An **AND** idea means the output turns on only if both conditions are true at the same time.

In a button circuit, that means:

- button A must be pressed
- button B must also be pressed

If the buttons are placed in series, both of them have to close for the current to flow. That acts like an AND gate.

Real-world example:

- A machine might need two safety buttons pressed together before it starts

## NOT gate

A **NOT** idea flips the result.

That means:

- if the input is on, the output becomes off
- if the input is off, the output becomes on

This is easier to do with a controller and code than with a very simple hand-built circuit, but the idea still matters.

Real-world example:

- A night light may turn on when the room is dark, meaning it does the opposite of a bright-light signal

## Input and output

Logic gates are easier to understand if you think in terms of:

- **input**: the thing you check, like a button
- **output**: the result, like an LED turning on

So a simple logic question might be:

- If these buttons are the inputs, when should the LED output turn on?

That way of thinking becomes very useful once you start combining circuits with code.

![Chemsaint, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons](https://upload.wikimedia.org/wikipedia/commons/e/ef/Table_2._Select_dual-input_logic_gates_with_truth_tables.png){width="50%"}

## Power

**Power** is the rate at which electrical energy is transferred or used.

The unit of power is the **watt**, written as `W`.

Power tells you how quickly energy is being delivered.

Examples:

- A small indicator LED uses very little power
- A laptop uses much more power than a simple LED circuit
- A space heater uses a lot of power because it is converting electrical energy into heat quickly

Power matters because two circuits can have the same voltage but use very different amounts of current and energy.

## Energy vs. power

These two ideas are related, but they are not the same.

- **Power** is how fast energy is used
- **Energy** is how much total work is done over time

For example:

- A `60 W` light bulb uses energy at a faster rate than a `10 W` light bulb
- If both run for one hour, the `60 W` bulb uses six times as much energy

This is one reason batteries are rated by how much charge or energy they can deliver over time. A small battery may provide the right voltage, but it may not be able to supply a large current for very long.

## Why components heat up

When current moves through resistance, some electrical energy is converted into heat.

That can be useful:

- Toasters and heaters rely on it

Or it can be a side effect:

- A phone charger gets a little warm during use
- A resistor can become hot if too much power is dissipated in it

This is one reason current limits matter in circuits.

## Putting the ideas together

A simple way to connect the main terms is:

- **Voltage** provides the push
- **Current** is the flow
- **Resistance** limits that flow
- **Power** tells you how quickly energy is being used or delivered

If you increase the voltage across the same resistor, current increases.

If you increase the resistance while keeping voltage the same, current decreases.

If a circuit has both substantial voltage and substantial current, the power can become large very quickly.

## Ohm's Law

**Ohm's Law** connects voltage, current, and resistance.

Formula:

`V = I x R`

Where:

- `V` is voltage in volts
- `I` is current in amps
- `R` is resistance in ohms (`Ω`)

You can rearrange it as:

- `I = V / R`
- `R = V / I`

Example:

If you connect a `9 V` battery across a `300 Ω` resistor:

`I = 9 V / 300 Ω = 0.03 A`

So the current is:

`0.03 A = 30 mA`

This is why resistors are used with LEDs. Without enough resistance, the current can become too large.

## How we chose the resistor values at `3.3 V`

In the FreedomSTEM Circuits Kit, many LED circuits use the board's `3V3` pin. When choosing resistor values, we were trying to balance three things:

- keep the LED current low enough to be safe
- keep the LED bright enough to see clearly
- use simple resistor values that are easy to repeat across projects

For LED circuits, a practical version of Ohm's Law is:

`I = (V_supply - V_LED) / R`

That means:

- start with the supply voltage
- subtract the LED's voltage drop
- use the resistor to set the current you want

The exact LED voltage depends on the color and the specific LED, but these are good estimates for the kit:

- red or yellow LED: about `2.0 V`
- green, blue, or white LED: about `2.8 V` to `3.0 V`

#### Red or yellow LED

Suppose we want a red LED on `3.3 V` to run at around `10 mA`, which is:

- bright enough for beginner circuits
- still comfortably below the current level where we would start getting less safe for simple kit use

Using Ohm's Law:

`R = (3.3 V - 2.0 V) / 0.01 A`

`R = 1.3 V / 0.01 A = 130 Ω`

There usually is not a perfect resistor for every calculation, so we choose a nearby real value.

Instead of `130 Ω`, the kit uses:

`150 Ω`

That choice lowers the current a little more:

`I = 1.3 V / 150 Ω = 0.0087 A`

So the current is about:

`8.7 mA`

We chose `150 Ω` because it is a simple standard value and gives a little extra safety margin.

#### Green, blue, or white LED

These LEDs usually have a higher voltage drop, so there is less voltage left for the resistor.

If we estimate a `3.0 V` LED:

`R = (3.3 V - 3.0 V) / 0.003 A`

`R = 0.3 V / 0.003 A = 100 Ω`

That gives:

`I = 0.3 V / 100 Ω = 0.003 A = 3 mA`

If the LED's forward voltage is a little lower, such as `2.8 V`, then:

`I = (3.3 V - 2.8 V) / 100 Ω = 0.005 A`

So the current would be about:

`5 mA`

That is why `100 Ω` works well for green, blue, and white LEDs in the kit: it still limits current, but it does not dim those higher-voltage LEDs too much.

#### Why the kit uses these two resistor values

So the resistor choices were not random:

- `150 Ω` was chosen for red and yellow LEDs because the math says we need a little more resistance there
- `100 Ω` was chosen for green, blue, and white LEDs because those LEDs already use more of the `3.3 V`
- both values are common, easy to identify, and close to the current ranges we want for beginner-friendly circuits

The exact current can still vary from one LED to another, but these resistor values are a practical way to make the circuits both safe and usable.

![Sivam29, CC BY-SA 3.0 <https://creativecommons.org/licenses/by-sa/3.0>, via Wikimedia Commons](https://upload.wikimedia.org/wikipedia/commons/5/5f/Ohm%27s_law_triangle_%28VIR%29.jpg)

## Watt's Law

**Watt's Law** connects power, voltage, and current.

Formula:

`P = V x I`

Where:

- `P` is power in watts
- `V` is voltage in volts
- `I` is current in amps

Useful rearrangements:

- `I = P / V`
- `V = P / I`

Example:

If a circuit runs at `5 V` and draws `0.2 A`:

`P = 5 V x 0.2 A = 1 W`

So that circuit is using `1 watt` of power.

There are also forms of Watt's Law that combine with Ohm's Law:

- `P = I^2 x R`
- `P = V^2 / R`

These are useful when you know resistance and either current or voltage.

## Final takeaway

At the most basic level:

- Atoms contain protons, neutrons, and electrons
- Electrons have negative charge and occupy the electron cloud around the nucleus
- In many circuits, electricity is the movement of electrons through a complete path
- Batteries provide the push that can drive that movement
- Voltage, current, resistance, and power describe different parts of what the circuit is doing

From there, two formulas show up again and again:

- **Ohm's Law:** `V = I x R`
- **Watt's Law:** `P = V x I`

Once those ideas make sense, building and understanding circuits becomes much easier.
