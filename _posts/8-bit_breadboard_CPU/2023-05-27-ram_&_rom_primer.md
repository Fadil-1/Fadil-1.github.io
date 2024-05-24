---
layout: 8-bit_breadboard_CPU
title: RAM & ROM Primer
mathjax: true
similar: 8-bit-computers
date_child: "May 27, 2023"
category: children
parent: 8-bit_breadboard_CPU
permalink: /blog/8-bit_breadboard_CPU/ram_&_rom_primer/ 
---
# RAM & ROM Primer

# Basics Primer

<div class="grey-background">
<h3>Random Access Memory</h3>

<p>A random access memory (RAM) is one in which the locations in the semiconductor memory can be written to or read from in any order, at approximately the same speed, regardless of the physical location of data inside the memory. Most RAMs are said to be volatile: Volatile memory only keeps its data as long as the device is powered, but data is lost when power is cut off. The main difference between volatile and non-volatile memory is the process used to hold data. Non-volatile memory devices such as hard drives use more complicated mechanisms to keep the integrity of the data regardless of power states. These mechanisms typically increases read and/or write time.</p>

<p>Volatile random-access semiconductor memory comes in two main forms: static random-access memory (SRAM) and dynamic random-access memory (DRAM).</p>
</div>

## DRAM

DRAM is commonly used as the main memory in computers because it offers a good balance between cost and storage capacity. It works by storing bits within memory cells: These cells, in their most basic form, consist of a capacitor paired with a transistor. When a bit needs to be stored or retrieved, the transistor either charges or discharges its paired capacitor, representing a bit as either a “1” (charged) or “0” (discharged). These charges and discharges are controlled by two lines: the wordline and the bitline, which are just “wires” connecting to nodes within the memory array.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/ram_&_rom_primer/1.webp" alt="Figure 1: DRAM cell">
    <figcaption>Figure 1: DRAM cell-<a href="https://www.allaboutcircuits.com/technical-articles/introduction-to-dram-dynamic-random-access-memory/" target="_blank">allaboutcircuits.com</a></figcaption>
</figure>
<br>


In DRAM, reading data is a destructive process, because when data is read, it results in the discharge of the capacitors. To counteract this, an operation known as pre-charging is performed to  restore the data into the capacitors after it has been read. Additionally, the capacitors in DRAM have a tendency to leak their charge over time. To ensure that data isn't lost due to this leakage, the capacitors are refreshed periodically. This necessity for regular refreshing of the charge is what gives DRAM its "dynamic" characteristic.

As more memory cells are packed into a given area, each cell has less space, resulting in smaller capacitors that hold less charge, making the charge in each cell's capacitor increasingly difficult to read directly. For this reason, to read the content of a cell, a sense amplifier is used to detect the minor variations in charge and then output the corresponding logic level.

## SRAM

In contrast to DRAM, SRAM cells are typically made up of a cross-coupled flip-flop, which consists of two pairs of transistors and two more transistors, often referred to as access transistors. This design doesn't suffer from leakage issues like DRAM, so it doesn't need periodic refreshing. However, it still requires constant power to retain data, making it volatile.

SRAM is faster than DRAM, which makes it ideal for use as a cache memory. However, because it uses more transistors per bit of memory, it is more expensive and less dense compared to DRAM. As a result, SRAM is not typically used for main processor memory.

Both DRAM and SRAM organize their memory in a matrix of rows and columns, controlled by integrated address decoders.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/ram_&_rom_primer/2.png" alt="Figure 2: Six Transistors(6T) SRAM Cell -  By Inductiveload ****Wikimedia Commons">
    <figcaption>Figure 2: Six Transistors(6T) SRAM Cell- By Inductiveload, Wikimedia Commons</figcaption>
</figure>
<br>

The static property of SRAM comes from its use of cross-coupled inverters to introduce a feedback mechanism which maintains the stored bit state. My CPU uses SRAM just because it is more convenient than DRAM: It is relatively cheap nowadays, faster than most RAM types, and most importantly, it does not require building a refreshing circuit needed for DRAMs. 

Figure 3 shows how the pairs (**M1**, **M2**) and (**M3**, **M4**) each form a CMOS inverter.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/ram_&_rom_primer/3.jpeg" alt="Figure 3: 6T SRAM Cell (Inverters are circled)">
    <figcaption>Figure 3: 6T SRAM Cell (Inverters are circled)</figcaption>
</figure>

<br>

SRAM operates in three primary modes: hold, read, and write:

**Hold State**: In this state, the word line “WL” is set to 0, turns OFF transistors **M5** and **M6**. As a result, the state of the internal latch, which holds the bit value, remains unchanged. This is how the cell retains its data when not being actively read or written.

**Read Operation**: When reading data, the word line gets activated by the input address from the address decoder. This activation turns **M5** and **M6** on, allowing the bit values at points Q and ~Q to transmit to their respective bit lines. The sense amplifier, connected to these bit lines senses whether the cell stores a logic 1 or 0. This data is then transferred to the output buffer and finally to the output pad. There are typically as many sense amplifiers as output pads in the system.

**Write Operation**: For writing data, a similar process is initiated. The address decoder activates the word line. The new data, which is to be stored, is then provided through the sense/write circuit. The bit values on the bit lines are overwritten by this new data. During this process, the drivers in the write circuitry, which are stronger than the cell's flip-flop transistors, force the new data onto the cell, effectively updating its stored state.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/ram_&_rom_primer/4.png" alt="Figure 4: SRAM Read/Write Operations -">
    <figcaption>Figure 4: SRAM Read/Write Operations-<a href="https://web.eecs.umich.edu/~prabal/teaching/eecs373-f11/readings/sram-technology.pdf" target="_blank">web.eecs.umich.edu</a></figcaption>
</figure>
<br>

## Memory Array

Generally, RAM cells(bitcells) are grouped in as an array. Specific addresses are accessed using column and row decoders. In DRAM, these arrays form banks, which in turn when associated in groups of two (DDR), four (DDR2) or eight (DDR3), form ranks (These concepts are detailed in [3]).   DDR stands for **Double Data Rate** and can transfer data to the processor on both the rising and falling edge of the clock signal, so twice per cycle.

Ranks primarily boost memory capacity within a single RAM module/stick, as more ranks mean more memory cells in the same physical space. Some systems with multiple memory channels can interact with different ranks on different channels simultaneously. This can, in some cases, allow for more efficient use of memory bandwidth. For example, while one rank is busy or refreshing, another rank on a different channel can be accessed for read or write operations.

# ROM

**ROM** stands for **Read-Only Memory**, and unlike RAM, ROM is characterized by its non-volatile nature. This means that the data stored within ROM chips doesn't disappear when power is cut off. ROM serves as a foundational memory type in computers and many electronic devices.

Typically, ROM is used to store essential data that shouldn’t be altered during regular operations. This data typically includes firmware or software that is fundamental to the operation of an electronic device. For instance, ROM is often used to store the boot instructions that a computer follows when powering up, such as conducting system checks and loading the operating system into RAM.

## Types of ROM

While traditional ROM was strictly read-only, over time, more flexible variations have become available:

- **PROM (Programmable Read-Only Memory):** This is a type of ROM that can be programmed once after manufacturing. Once programmed, its data becomes permanent.
- **EPROM (Erasable Programmable Read-Only Memory):** Can be reprogrammed and can be erased using strong ultraviolet light.
- **EEPROM (Electrically Erasable Programmable Read-Only Memory):** This more modern variation allows data to be electrically erased and rewritten, providing more flexibility.
- **Flash Memory:** (Yes! Flash is a type of ROM)A form of EEPROM, which allows for multiple areas to be erased or written in one operation. It is widely used in USB drives, memory cards, and solid-state drives.

## ROM in Modern Computing

In contemporary computers, the boot firmware, often referred to as BIOS (Basic Input/Output System) in PCs, is stored in ROM. This firmware is very important as it runs the initial hardware checks and loads the operating system from a hard drive or other storage devices into RAM.

<br>

[**<<<<<<<<<<<<<<<<<<<< Previous Post: ALU & Flags**]({{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-alu_&_flags.md %})


<a href="{{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-ram_&_transfer_register.md %}"><span class="wide-space"></span><span class="wide-space"></span>**Next Post: RAM & Transfer Register     >>>>>>>>>>>>>>>>>>>>**</a>

<i class="fas fa-calendar-alt"></i> <span style="font-size: 15px; font-weight: bolder;">Updated:  </span><time>May 21, 2024</time>