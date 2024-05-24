---
layout: 8-bit_breadboard_CPU
title: Debugging Clock
mathjax: true
similar: 8-bit-computers
date_child: "May 27, 2023"
category: children
parent: 8-bit_breadboard_CPU
permalink: /blog/8-bit_breadboard_CPU/debugging_clock/
---
# Debbuging Clock

# Basics Primer

<div class="grey-background">
In electronics systems, a clock can be thought of as the "heartbeat" of the system. It simply is a signal (a voltage) that alternates between ON and OFF. Every time this signal oscillation "ticks", it tells parts of the system when to act.

In many ways, the speed of the clock defines the speed/pace at which the system operates; a faster clock rate generally means that operations are carried out at a faster pace. However, as discussed in the next post, there must be a balance. The physical properties and layout of a system's components can set a cap on how fast its clock can be pushed.
</div>

## Multivibrators

Multivibrators are digital oscillator circuits with two stable states. The transitions between the  states can be controlled or automatic, and define the multivibrator’s behavior and application. The three forms of a multivibrator circuits are astable, monostable, and bistable.

### Astable Multivibrator

The astable multivibrator continuously oscillates between two states, making it ideal for generating clock pulses in microprocessors and other synchronized systems.

### Monostable Multivibrator

The monostable multivibrator has one stable state. When triggered, it shifts to a quasi-stable(temporary) state for a predetermined period before returning to its stable state.

### Bistable Multivibrator

The bistable multivibrator has two stable states. It changes from one state to another when triggered. A latch is a good example of a bistable multivibrator, as it maintains its output state either HIGH or LOW until it receives a trigger(Set or Reset) signal to change state.

## The 555 Timer

Just like the SAP-1’s, the clock module of my CPU employs a 555 timer. The 555 timer is a versatile chip that can generate accurate pulses of various widths, making it a suitable choice for this application. Compared to crystal oscillators, which are used in many electronic devices for their precise frequency generation capabilities, the 555 timer offers greater flexibility. The circuitry of the 555, which will be explored shortly, allows for easy manual adjustment of the clock speed.

On the other hand, crystal oscillators, as the name suggests, use the mechanical resonance of a vibrating crystal to produce an electrical frequency. A single crystal oscillator is typically designed to generate a specific fundamental frequency determined by the physical properties of the crystal, such as its size, shape, and the way in which it is cut. It is possible for a crystal to support harmonics, which are integer multiples of its fundamental frequency. However, in the context of this breadboard CPU, the adaptability and control offered by the 555 timer are more convenient, especially for debugging and real-time modifications.

Below is a Modularized schematic of the Texas Instruments LM_555 timer.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/lm555.png" alt="Figure 1: LM555 Timer datasheet - Texas Instruments">
    <figcaption>Figure 1: LM555 Timer datasheet - Texas Instruments</figcaption>
</figure>

<br>


As can be seen, there are three resistors in the center of the circuit, forming a voltage divider. The 555 timer is called this way because on the original model the value of R was 5kΩ.

# Implementation

I’ve built two clocks for this project: a portable clock for debugging and a permanent clock for ongoing use. the permanent clock is described in the [next post]({{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-permanent_clock.md %}).

The debugging clock is similar to the SAP-1’s. It has an astable and a monostable configuration, which can be selected for different testing needs using a switch. 

The difference between my clock and the SAP-1’s is the use of NAND logic for the astable-monostable output switching instead of AND logic.

The simplified diagram of the 555 timer that Ben Eater used in his videos, shown below, is in my opinion very helpful for understanding the intuition behind the functioning of the timer.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/1.png" alt="Figure 2: 555 Simplified View">
    <figcaption>Figure 2: 555 Simplified View</figcaption>
</figure>

<br>

## Astable Multivibrator with 555

### 1. Initial Conditions

Upon powering up, let’s assume nodes **a** and **b**(In the figure below) are at 0V initially. No matter how fast the capacitor at node **b** charges; the voltage divider’s node on the **C2** comparator will reach 1.67V, before node **a** reaches 1.67V. In other words, **C2** will be ON until the voltage at not **b** surpasses 1.67V.

While **C2** is ON, the “set” input of the latch stays ON, keeping its "not" output OFF; consequently, the transistor connected to the “discharge” pin (pin 7/node **a**) of the timer also turns OFF, disconnecting the path to ground and allowing the charging of the external capacitor through the leftmost resistors.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/2.png" alt="Figure 3: Astable configuration of 555 timer">
    <figcaption>Figure 3: Astable configuration of 555 timer</figcaption>
</figure>

<br>



### 2. Capacitor Charging

The external capacitor starts charging through the resistors. Current flows, and the voltage across the capacitor rises exponentially, following the RC charging curve.

As the capacitor charges, the voltage at node **b** eventually exceeds 1.67V. **C2**'s output goes LOW because the voltage at the inverting input is now higher than that of the non-inverting input. However, the state of the latch remains unaffected.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/3.png" alt="Figure 4: Astable configuration of 555 timer">
    <figcaption>Figure 4: Astable configuration of 555 timer</figcaption>
</figure>

<br>


### 2.1 Latch Reset

The capacitor continues to charge until the voltage at node **b** surpasses 3.3V. At this point, the "reset" input of the latch is activated due to the output of **C1** turning HIGH (as the non-inverting input connected to node **b** is now higher than the inverting input). The "not" output of the latch goes HIGH, resulting in the activation of the transistor.

### 2.2 Capacitor Discharging

With the transistor ON, the capacitor begins to discharge through the discharge pin of the timer, leading to a decrease in voltage at node **b**. As it drops below 1.67V, **C2**'s output goes HIGH again, setting the latch and turning the transistor OFF.

The cycle repeats, giving rise to an oscillating output at pin 3 of the timer. This self-sustaining oscillation produces a square wave output, characterized by the charging and discharging times of the capacitor. The frequency of oscillation and duty cycle(The proportion of the cycle when the signal is in a HIGH state) can then be adjusted by varying these components’ values.

Typically, to have flexibility on the clock rate, a variable resistor is added in addition to a resistor between nodes **a** and **b**. The variable resistor alters the time it takes for the capacitor to charge and discharge, thereby altering the clock rate.

The 1KΩ resistor in series with the variable resistor is there so that in the event that the variable resistor is set to 0Ω, there would still be some resistance between pin 6 and pin 7, otherwise the discharge time would theoretically be zero(The capacitor would immediately discharge every time the voltage at node **b** hits 3.3V), keeping the timer’s output constantly ON.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/4.png" alt="Figure 5: Astable configuration of 555 timer(Variable resistor) ">
    <figcaption>Figure 5: Astable configuration of 555 timer(Variable resistor) </figcaption>
</figure>

<br>


Let **RA** be the resistance between the voltage supply and the discharge pin; and **RB** the resistance between the discharge and the threshold pin. 

The charging time for the capacitor exceeds the discharging time, because the capacitor charges through both **RA** and **RB**, but only discharges through **RB**. As a result, the duty cycle exceeds 50%, with the exact excess percentage depending on the value of **RA**(The higher the value of **RA**, the further above 50% the duty cycle will be, and vice versa.)

The datasheet provides the following timing equations:

$t1$ = $0.693 (R_A + R_B) C$

$t2$ = $0.693 (R_B) C$

$T = t1 + t2 = 0.693 (R_A +2R_B) C$

$==> f =1/T=1.44/((R_A + 2R_B)C)$

Achieving a precise 50% duty cycle isn’t feasible in this setup without modifications. A zero-ohm **Ra** would technically yield a 50% duty cycle, but it's impractical as it would create a direct short from VCC to ground via the discharge pin (pin 7).

However, as discussed in the permanent clock’s post, adding a (or a combination of) bypass diode(s) between pin 7 and pin 6 can allow duty cycles of 50% and below. The slightly imbalanced duty cycle resulting from the absence of such a modification is more than acceptable for the debugging clock.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/5.png" alt="Figure 6: Astable configuration of 555 timer">
    <figcaption>Figure 6: Astable configuration of 555 timer</figcaption>
</figure>

<br>


The 555 datasheet suggests adding a 10nf capacitor between pin 5 and ground, to reduce noise. As can be seen from the schematic, pin 5 is directly connected to the top node of the voltage divider, thereby setting the reference voltage for the comparator. Attaching a bypass capacitor to this pin helps keep the voltage level steady, and makes the timer more reliable.

## Monostable Multivibrator with 555

The astable output on the debugging clock is used as the ongoing/permanent clock would: To keep the CPU running continuously. However, the point of a debugging clock is to mainly allow single, manual pulses. 

A push button, by itself, can be used to tie the reference voltage to the clock node/input of the CPU. The problem here is that when pressing the button, its switch can unexpectedly close and open more times than intended. Just like in wristwatches with clicky buttons, where a single button press can sometimes result in multiple increments in the displayed time due to mechanical bounces of the button's internal contacts.

To mitigate this, the 555 timer is used in a monostable configuration. In this setup, a trigger causes the output to change state for a specified period(Staying at that state no matter what happens to the trigger during the time period) before returning to its original state. This helps ensure each button press results in a single, clean clock cycle, despite any bouncing.

### Working Principle

When the push button is not being pressed, **C2** stays OFF because of the reference voltage at pin 2 (through the 1KΩ pull up resistor), and the latch stays on its reset sate with the “not” output HIGH. This turns the transistor ON and discharges the capacitor.

Upon pressing the button, pin 2 essentially gets connected to ground, activating **C2**. With **C2** ON, the output goes HIGH, and the transistor turns OFF, initiating the capacitor's charging process.

The cycle resets when the capacitor’s voltage exceeds 3.3V, turning ON **C1** and resetting the latch. 

This turns the transistor ON and restarts the cycle.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/6.png" alt="Figure 7: Monostable configuration Diagram of 555 timer">
    <figcaption>Figure 7: Monostable configuration Diagram of 555 timer</figcaption>
</figure>

<br>

This mechanism ensures that each button press results in a single, clean transition of the clock cycle,  mitigating the issue of button bounce.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/7.png" alt="Figure 8: Monostable Configuration of 555 timer">
    <figcaption>Figure 8: Monostable Configuration of 555 timer</figcaption>
</figure>

<br>

## Bistable 555 Debouncer and Switching Logic

### Bistable Debouncer

Just as a push button could have been used by itself to trigger clock pulses, a simple single-pole-double-throw(SPDT) switch can be used to switch between the two multivibrators outputs, as follows:

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/8.png" alt="Figure 9: Simplistic Clock Switch">
    <figcaption>Figure 9: Simplistic Clock Switch</figcaption>
</figure>

<br>



But just like push buttons, switches can also bounce. My switch, just like the one in the original SAP-1 kit, is a Break-Before-Make(BBM) switch.

The image below shows what’d happen within a SPDT BBM switch if used as shown above.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/9.png" alt="Figure 10: Break-Before-Make Switch As a Clock Mode Switch">
    <figcaption>Figure 10: Break-Before-Make Switch As a Clock Mode Switch</figcaption>
</figure>

<br>



The pole within the switch can bounce with the last throw it made contact with due to slight vibrations, and all of the CLK input pins within the CPU would be momentarily left in a floating state during the switching process.

As mentioned earlier in this post, an SR latch is a bistable multivibrator by definition, and its output can be used with the switch through a switch-select logic to select(more so than switch) between the astable and monostable clock. 

Ben Eater used a bistable configuration of the 555 timer to implement this debouncer just to expose learners to another use of the chip. The only component of the 555 timer used here is its SR latch, and in fact, an SR latch IC could have been used by itself. 

An advantage that I initially personally found in using the 555 instead of an SR latch IC was that it’d have saved me room on the clock breadboard as I initially intended to use my debugging clock as my main clock, and I wanted to pack as many ICs as possible on the same breadboard.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/10.png" alt="Figure 11: Bistable configuration of 555 timer">
    <figcaption>Figure 11: Bistable configuration of 555 timer</figcaption>
</figure>

<br>


With this configuration, even if the switch bounces between a make(closed) and a floating state(break), it won’t change the output of the latch, because anytime the switch goes into one of the two make states, the latch will hold the output for that specific state, and won’t change until and only until the switch goes into the opposite make state.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/11.png" alt="Figure 12: Bistable Debouncing Mechanism">
    <figcaption>Figure 12: Bistable Debouncing Mechanism</figcaption>
</figure>

<br>

In other words, unless the opposite input(Trigger or Reset) is grounded, which does not happen until the switch is fully actuated, the output of the latch is not going to change even if the current input is being toggled!

### Switching Logic

Now that all the parts of the clock are completed; they must be joined together. The goal is to have a select input, tied to the bistable output, to switch between the astable and monostable pulses.

The logic below is the one built that the original kit follows.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/12.png" alt="Figure 13: Clock switching Logic using And Gates">
    <figcaption>Figure 13:  Clock switching Logic using AND Gates<a href="https://youtu.be/WCwJNnx36Rk?si=5iUGnE1f3fyTPNT4">- Ben Eater Clock Module Video</a></figcaption>
</figure>
<br>


For the sake of saving room on the breadboard, I implemented the logic with NAND gates as it required only two ICs, instead of four with the implementation above.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/13.png" alt="Figure 14: Clock switching Logic using NAND Gates">
    <figcaption>Figure 14:  Clock switching Logic using NAND Gates<a href="https://youtu.be/WCwJNnx36Rk?si=5iUGnE1f3fyTPNT4">- Ben Eater Clock Module Video</a></figcaption>
</figure>
<br>


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/14.png" alt="Figure 15: Portable Clock Schematic">
    <figcaption>Figure 15: Portable Clock Schematic</figcaption>
</figure>
<br>


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/debugging_clock/15.jpg" alt="Figure 16: Portable Clock">
    <figcaption>Figure 16: Portable Clock</figcaption>
</figure>
<br>


# ICs

3x LMC555CN CMOS Single 555 Timer Low Power DIP-8 ([Jameco](https://www.jameco.com/webapp/wcs/stores/servlet/ProductDisplay?langId=-1&storeId=10001&catalogId=10001&productId=126797), [Datasheet](https://www.jameco.com/Jameco/Products/ProdDS/126797Philips.pdf))

2x 74HCT00 QUAD 2-INPUT POSITIVE NAND GATE ([Jameco](https://www.jameco.com/webapp/wcs/stores/servlet/ProductDisplay?catalogId=10001&langId=-1&storeId=10001&productId=44871), [Datasheet](https://www.jameco.com/Jameco/Products/ProdDS/44871FSC.pdf))

<br>



[**<<<<<<<<<<<<<<<<<<<< Previous Post: Basic Definitions And References**]({{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-basics.md %})


<a href="{{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-permanent_clock.md %}"><span class="wide-space"></span><span     class="wide-space"></span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Next Post: Permanent Clock     >>>>>>>>>>>>>>>>>>>>**</a>

<i class="fas fa-calendar-alt"></i> <span style="font-size: 15px; font-weight: bolder;">Updated:  </span><time>May 21, 2024</time>