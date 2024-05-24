---
layout: 8-bit_breadboard_CPU
title: Nomenclatures
mathjax: true
similar: 8-bit-computers
date_child: "May 27, 2023"
category: children
parent: 8-bit_breadboard_CPU
permalink: /blog/8-bit_breadboard_CPU/nomenclatures/
---

# Nomenclatures & Notes

- Most Posts start with a “**Basics Primer**” section containing a high-level and basic description of the module being discussed.

- Whenever I mention **SAP-1**, it specifically refers to Ben Eater’s build, unless stated otherwise.

- I use the terms "**CPU**", “**build**”, and "**computer**" interchangeably. This is a deliberate choice for clarity and ease of understanding.

- **\|←** and **\|→** are used to specify whether a control signal is an input or an output to a module, respectively.

- ~ Denotes active low control lines.

- I use **HIGH**, **ON** and **1** interchangeably, as well as **LOW**, **OFF** and **0**.

- I made all the schematics for this project using a top-notch, industry-tier, color-coded, super professional EDA software called Notability.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/nomenclatures/Notability.gif" alt="Notability EDA">
    <figcaption>Notability EDA</figcaption>
</figure>

<br>


> On a serious note, [Notability](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjm-ZuemdqBAxVqMlkFHYbXC_YQFnoECBgQAQ&url=https%3A%2F%2Fnotability.com%2F&usg=AOvVaw3aq63P4MtZ-4O2jQZRJnz4&opi=89978449) is a note taking app I’ve been using extensively throughout my college years. Most of the schematics and diagrams that I made myself(All figures without cited sources) in this series of posts, were made using Notability. Being able to freely draw the schematics helped me have control on the ICs orientations on the breadboards, which was very important to minimize the area used. You’ll notice throughout the posts that I mostly use the actual chips pinouts instead of logic/schematic symbols, because it makes it very easy to transfer the final schematics over the breadboards. 

- I’ve applied a straightforward color-coding system to the data lines in the schematics to indicate their bit significance. The coding starts with solid brown for the least significant bit (bit 0) and progresses through to dotted green for the most significant bit (bit 7). Each bit is represented by a unique color, with solid lines for the lower four bits and dotted lines for the higher four. For instance, bit 0 is linked with solid brown, bit 2 with solid purple, bit 5 with dotted light-blue, and so on. On components that use more than 8 bits the same color coding rolls over at the 9th bit, and so forth. 

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/nomenclatures/color_coding_1.png" alt="Bits Color Coding">
    <figcaption>Bits Color Coding</figcaption>
</figure>

<br>

The data and address bus notation that I've used for this project's schematics is the the drawing of an actual bus. Why? Because it makes sense!
<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/nomenclatures/bus.png" alt="Bus">
    <figcaption>Bus</figcaption>
</figure>

<br>


<figure style="text-align: center;">
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/nomenclatures/color_coding_2.png" alt="Nodes">
</figure>
<figcaption>Nodes</figcaption>

<br>


<figure style="text-align: center;">
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/nomenclatures/color_coding_3.png" alt="More symbols">
</figure>
<figcaption>More symbols</figcaption>
<br>





[**<<<<<<<<<<<<<<<<<<<< Previous Post: Overview**]({{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-overview.md %})


<a href="{{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-basics.md %}"><span class="wide-space"></span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Next Post: Basic Definitions And References     >>>>>>>>>>>>>>>>>>>>**</a>


<i class="fas fa-calendar-alt"></i> <span style="font-size: 15px; font-weight: bolder;">Updated:  </span><time>May 21, 2024</time>