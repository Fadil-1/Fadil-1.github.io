---
layout: 8-bit_breadboard_CPU
title: Numerical Display
mathjax: true
similar: 8-bit-computers
date_child: "May 27, 2023"
category: children
parent: 8-bit_breadboard_CPU
permalink: /blog/8-bit_breadboard_CPU/numerical_display/ 
---
# Numerical Display Module

# Basics Primer

<div class="grey-background">
<p>A BCD (Binary-Coded Decimal) decoder is a circuit that converts a binary-coded(binary equivalent) decimal number into a format that can be easily displayed or understood, usually for the purpose of display on segmented screens. In BCD, each digit of a decimal number is represented by its binary equivalent.</p>

<p>A segment(ed) display is a type of LED-based numerical display consisting of individual segments, each of which can be illuminated independently to form digits and characters. They usually come in two configurations:</p>

<p>Common Anode: All the anodes of the LED segments are connected together to a common positive voltage. Each segment is powered by grounding its cathode.</p>

<p>Common Cathode: All the cathodes of the LED segments are connected together to a common ground. Each segment is powered by applying a positive voltage to its anode.</p>
</div>


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/1.png" alt="Figure 1: Common Anode vs Common Cathode 7 Segment LED">
    <figcaption>Figure 1: Common Anode vs Common Cathode 7 Segment LED</figcaption>
</figure>
<br>


The SAP-1 drives four 7-segment displays able to represent all decimal numbers fitting within 8 bits (0 to 255) as well as signed two’s complement(-128 to 127). My display module uses a set of six 14-segment displays that can cover all numbers fitting in 16 bits (0 to 65,535), including signed two's complements (-32768 to 32767). 

## Why Choose a ROM?

Segmented displays can be driven in various ways. Below is an example of one of the simplest methods, in theory, though not the most straightforward in practice:

Given a 4-bit input, a seven-segment display can be used to show the hexadecimal representation of each of the input's 16 possible values. Below is a truth table that outlines the required state for every segment of a common-anode seven-segment display to represent numbers from 0 to 15 in hexadecimal.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/2.png" alt="Figure 2: Segments State for Every Digit">
    <figcaption>Figure 2: Segments State for Every Digit</figcaption>
</figure>
<br>


The picture below shows a circuit that implements the truth table. Note that beside the NOT gates, all the gates used in the implementation below are four-input gates, which means that regardless of how you’d want to implement this, if you only have two-input gates, you’d need a minimum of 3 gates per NAND and AND gate used in the figure.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/3.png" alt="Figure 3: Seven segment decoder, by Mateusz Baran-">
    <figcaption>Figure 3: Seven segment decoder, by Mateusz Baran-<a href="https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgzCAMB0l3BWK0AsBGATGMCME48B2DANjwA4M0IFIQlb6BTAWjTQCg0FCRzy6WDCDTwQQqCF51IHAO4gSAkGxJ1CkFCrRqo8xWGGq6JBCW27ZChOS3HFkchZkcAkouX2ldNpkkwGNwMjHRNDbT8ZaED3GztQ+lsI4SiY+jBzewQM5P9o+g4AGQ8fBO9tJJSQADMAQwAbAGcmej1iknCvTrRKyTqmlqRZYrjnRPjeun7m1uH0zITshcmahpmh-SWxs1LLLgQ0EUhiFQwtUROzkRAtOgR9w6JMq6fxc5vW++5HjCcWF9+b2uWkC3yOV3+50gVyuhxBBTB-B8VyRQLhnweUiSkKxWlhH1BBz4nRR4Xx8K+jEISR0TmpeJ0wIx3HUgNpUkBVHMh3MhJMsKUihhjMODARjBIJ3ZkuEXKZfPofnZB1lIs+4ruguVgrlPOZjBQJHOgsNDO5Hzu+jlKBMjhuLgUpC0KCcJCNNycVnAundKBdilu+hQZj4JkZyi9NrpwkIuA5egUon4pyhyZYNoTR08sMcPhDXtE7pxhbsJwLkBDxYrmWTXp2210LDw5i9aj+ZTtLAj+lMCx9lfdXo08V0w5U-rrOV8wi2Xc9m2x7Bn2LLPe6fg6RnzPc8S5K44dR0ZLClkCLq4UxGRWivKlr+kIgpxj7+94U5GPKOPb74RZRRZ-PA-BxICjEAxsXkbH9iD+K4YLvQ9CEfFMpGQrtD0oOwUQhbswUIKc4JyckMUTOBYKhTsf1nZNbznTNaJop9oKYpwPxred32-ViAI4387GTUC714wS6ObHxwPEpxREo3jpNfKTqyEzNyBOHEVLAw88Awa8QC0nwL10p9IL+AzRE-KFjwMtsEI5V9EMBdDUJrRC0OUTCbK9dzHPUjyF1LYQ9JUAzApPAKn2C8LhDMzJTM0HTRAzdNhK0lCCCMDMvTwP1UuypLlObFDyAK9MMP9NSyonfQBB06qD3ouNnwayrSJJKFOm3BQKCwrQupUQd9DwAieqnfr3zTFE0w6vhEpRRKpsIFLn0W0apFyuDcpW3s+pvDbA0vXapGWvbDqMd1BsyFbzu23TsU29rzFsPMWyquaHsm56xr+ENRHuzMfq3blcxUebNHHOkmt42N0tYireNsP5-Syuxmt03L-QSnwUfKErQ0xjC4DqorMgyqriozNK6syxaMyTBHDwwCEYQhFaMFUmFVJWwwdK54GPu9cj+d5zN0GeZ1jxW00UMllgVpVFC5ZYKaJBxZWUd+HT1cp-RDAFnWwczMA0KuQ3icPFBGedCEUZQNnnVUknrG0+WnbyyNiquFBioMv0BZ9oKUiDAmcRtfSA4UHAjGNhrcKJOUVcZYjAnD0GcTAFPu0dSsYUrDPxE7GFKJcMEwGA42-ET8VDidFDq4rylDgybndDrzFaG6+hQZbsEoylu0u6JYNRZuEMW4UF1fbTArIxm51Eqn7XFuNxb5-DtatDAXKV-Ed28WKrezgFg+VH3oOC58Lf6ybcxx+Pvmb6vm457vp-wGXvmwDf8BN-f7-t8yfe97mCPg-L0wCCraXPnzayjkI6+XDtHOgad+KHiQTZDAOd6YYLznZTMoxQo3C9mHAhMVhB+3wdPEypCg5WQHM6IsEt6FiwusdEW11WanWOuwthzNjqbiFgrKaAjzAZC+u-J8IYeaKz5mOPKuBMa8Tkfrc2yNeLKP1nrV22sHL+lVrxbGGYbbpTNvbRBaEHbgDMYITw5iXR0G4FFY4UU4zlkuFCKUzj9CiBhFCWE2VMrIReMhagfMtJOABFJQEnllATTsU7TyZItDkHCHuIclQbw0lBkOIiN4cgX07iCUGP5B5AmKbnHuHs7QGUbkCapnNy7rz8Erd0MJfS8TlMKa++M7GClqmgPxD4UrsgWlFOJD4gmCiQuYAyL4RATMFPNQZTtUSYC6SIbKXjzj9MvJURk9JxDhCiYIcIeyJBZO5BMnIKSHzrImeszJD44xDLjNM0GQzQbmMIEqCZfgUa3iGU7FaUN4yTPjGckQfgklRUiNcqE6TYXKWie6eC1chyciRZyRkrZkzSmxTkLF3TXTKE2u6aUrTMxbWlCGcxRoCUBjsVsoUxpXSQXJXaaUdpqUikFCQcMGFokFRlH-cllwBWXExT2DlJgqWHi2hmMc1KyWfNIXoolN4AW8JZfhcwW8lBSVyUEvFPYabZV6Qy1EesSDG0iT2K1zKzS4MGfMwZDLRjKhpNa6w4ynA8G5KM6wuhtR2OhdYR58y4wXxud6k1wlsrVLME4apdZBRxp1OKzqyFqmvDAEkfxwikhy2zcdAt+by5pqOHaapcl7SyTItWm4vo7SRgbU4SWco6xsnmWyF1TtlQ9sNdYL53qlQeo7ky0dhlhYFXZJ7Xkd9lDTvnR4seUoTRSgZcU6dIYt5+2nf6CWa6QRdqLUe+gzqi1nrpWs49dici6pEP2xUIzvXuoUS+3SbIR18JWSdEQfr6ABr8Fq8FRDikFTbhOusoMwPhr5ggGDjKIObGjeOope6tDlAlmBqZ8yoHJO5ckv9X6nY+t-WbLD4BGnPQAB70AcnKBAa1qAfCuAAQQ4DRkj-xGQIEXkxvEWgABC7GhQQC4+YGlpw+NAgAMLCclIcMTHhYJSauAAEQ4EAA)" target="_blank"> Falstad.com</a></figcaption>
</figure>
<br>


Clearly, the number of gates required to implement the logic for all segments is substantial, even when using higher-input gates. A ROM chip, on the other hand, offers a more compact and cost-effective solution by storing the entire truth table for all segments. **ROMs can emulate any combinational circuit** by storing their truth tables, thereby serving as lookup tables. This approach replaces the need for a complex circuit dedicated solely to specific character outputs. It not only simplifies the circuit but also enhances adaptability and ease of programming for various display requirements.

Since the display module for the SAP-1 uses four 7-segment displays, a ROM with at least a 22-bit output(3 x 7 bits for the digit displays, and 1 bit for the sign display) can be used to drive all of them. Such a ROM would be relatively expensive, hard to find in through-hole and parallel format, and not easy to program without a dedicated PROM programmer. Another alternative could be the use of a combination of smaller-sized ROMs. For the four displays, four separate ROMs could be used to encode the value for each display individually.

Both of these methods are acceptable, considering their straightforwardness.

The SAP-1, however achieves this encoding with only one 16 Kbit (2Kb x8) Parallel EEPROM, with only 11 address pins and 8 output pins. Ben Eater’s display module by itself is to me a simple, but excellent example of electronic design ingenuity. Each display is activated sequentially, creating the illusion that all digits are displayed at the same time. This is achieved through a combination of a dedicated clock, a binary counter, and a decoder. The counter and decoder select which display is active and ensure the correct data from the EEPROM is shown, while the clock sets the rate at which each display is selected.

I made a Falstad <a href="http://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjOB0CsBsBM0CmBaAHCal4GZYE58C018AWaM-CaTEMnTVMMAKDFjJCIAZN4MYPH2gCQfLiLp8AZgEMANgGck49mlpgeZPvHhcWsDHskh4rMkPBl9-QQVh3x4CBj6xGj6iADs+cDzwAf5giL7g8D4uEB4gXhB+AUFaIWFRoekscZ7cCSGBwRG06ZHR2XG5vvnJPKnFEZkxOd6JWjV14RllsfFVSYWh9V0sTRUt1QNpDd3Nef0pRZ2lI+W9rQULg0uNq5Xr7YslOz17E5tTw1kn4-O1h9Mr13Ntk0PLV7N9L+dvx5-7r22MzGzw2dy2R2BazO4Iu71G0NuHUhj3+MORDw+IK+YIxlwRpyR93xuxu31hvyhhPJePhpNBBwhmIJZNxxLpTxxBx6nl5qz5PN2jmFFRFYsq3klEClEulcr6iUV-iVCuVatuNU1Gu15MZ4P1+UNAwNgK2ZrC5s0FutVvqUXt4QdToey1dKLdLpRWRWPu9fogvoD-v5IcFYYFosj4pFMtj8rjhJVSfVyZ1YK1urTeqNmxNuZzFMWlqLNpLtsdFedzuGHpr7vrzLKgabwebqNDAs7oajPfFCf78flqeHKfVmfH6azRPzxqN4Y7C-nS67y8XK-Xa83q+3G53W93B-3R73J8PJ97F+jl+vV9vN-vd8fD+fT9fL-fMcHsu-A5-X9-AH-kBf4gYBoHAWBMp8NBzgwXBsEIfBSGIShyFoahGHoVhmE4dheG4QR+FEYRJHEWRpEUeRVGUTR1F0bRDH0UxGFdCUmj6kEiTeMKjA+qUbHGpx-jceUfEOmaHF9CJsRiUs7ETFxMSid6-FFpJimirxKniRa6nCUpMnaXJglSQZWkBqpEkKfpmlNpZunWZUPF2Tp8n9BpzmyQJuZCU5ykWa5Jkef50zeXpfmcgCPxAu2iI0uyfzYlFhZeiyDKAql9JchljaReiCVUqyjJwolcVskyJJ5dOJWFel0WZVV8UVRyaLVZSsXUuVUyQcBb7Rmeh5tq2w1BqNLmehNdaTapVaVhWxYLaWi3ljOq15utBYZpOE5bVqI6qgdKo9eBH62aex4DUK77Hb++13WO22PbtU5rQWb2zqaS1fSt31zbN1a1oDDZTSSQ1jWDLYIpdS6nTd8p9adCO3tDKMXWj50Y6jmPo1juM4-j2OE3jRME8TZOkxTJNU+T1OUzkSOIx+XCcHEzNs6zHMs1z7Pc5zPP83zgu88LAsi0LosS+LUtizLkuy9LcuKwryvy6rStqyr6ta5rOti8x+uMYbBvG0bpsm+bzgoBAKDmAA7tYtgIAYPA+EETtqPbWhwHEthaK7PuSKwns2Fw0D4MkWih+HHsBN7YcR9omDRzwrAAG4BDo1jO5nJgIZntBwTArAAOYZ3wYBkNn5diNB7DQOkrsYGQaDl2g-vNzB6TgHXUTwDwHD0C3ZgcBIQ98F3bBgPXZjx4Pug+Hgc-OBPPdmDgicd2YldN2PnTd57PihEvYCH0EliOCnB9H+f4D4GgXA35ft-3-QA9gHfD9j0H4CN5gR8cEPaAR8n4AJEP-IwEgeC109hA+gUDb5GDgdAhBTd4Hv0QUAoIT8+4D0wSgv+WDv4nzEJQAwDhMCVxjqAzAPhHDUJ8InEBsCGEGA-r4Rh38cGOHrnQthPCqF8Noc-LgLCqG-34dQ-hTCiAULITIowbgiHkIUfglRICiAYBUegjApCBEYMoVw2RMdDGb3fi-TeIDT7H1-hYzh69P66EiGfL+9s9BxwMfYox2DEDChIGYHxXjOFOJoY4PQ-tRHYM8fwsJQQpF2MTngtx3DgFBO9joRxccUmuOCTfGJS9sGz03j40eyDECUN0YgaOuiCmUJUWU0OlCCmwBEEI4p7DA6uNntEuALSL6cK6UfepBDjG6PSTPcpWSZ7NNfqEnp+SiFsNyTkge6jEFjKSUggRL9RF5IiQsxBdSAlqNSb44wujjnZPCYnNpezslpPgUMsZ3j24DzaY-ThPhzFD0iOY5uxjPkPz+foGR29jFUEcKC4FEKXFmABcMgQ8C8HYJbmAoICKJA4EIa4lF9BMUz2vnigpBK0V4KRf0o+iTwXDOwXCipcLOClJxdEnFsBvY0pfgy-FbtM7stDq0plQjkXwNZaEqlIqRlH05YgCljTyWxIMVS6pnDFWtLFWyoJjtvbvz7nEdV2SeA6NabnOJ+rNGZ3fovTl3jbDRNzuK7xBqjF6EdVajVD88UWohYSt18Lc4MCxf4x1iTjWTOdU3P52qJB-IdTvRxjrQXqJ1aCyN8zPbh1RbfReZK01Zv-vgRe-qBGWvNfm7hsqc1ltYTqpVaadXipTXEgAki4RBudDAYBkdBGAmAiEAKmREB5eqW3GD8aEPFAhFGez7Zi6uLMZ1qGbaEQddC+7VzcOIbt0BWCLtwGi0du7wDTK7bQLdO6506tCCzbVsFN29sQTIxAQjO39KEc0s5T6+mdNfY6ypbtHXeL8W+teicgMAc0T+idERJ1mCge4H9-dhT-s4bBuI8G0FHqIVYoDxDwPQZPpKx1+HkjJyIauqD-j914YPSPGD6HkGXqrT-PNAaU31tEO4IdnrWbl2gMW+jvHhTmoE3EPxIDhNaPYyJvDpbcXJGgKIWTVDJOux4wplTSm1MXvk2fb1tao2CDgOGvDhn6ARpMz4BTYmdUWbk4gmzVDYESOgC-E14BnN8roe53wL8xPbJflPazPmlEyN0SPEQ5bD2IsoWFkAaAVlKPgXFzzOqksOcAeA3BkyiPHw8M4+jsBMvJAK44e+eHiuxbMyl6NRDJMkHLrl2LMKOB4rq4evFtiAAyDtQ7TIY5gI94AQDyGUKoAurAusVxtWISbD9O2DeGyoaQ423PVum5JqlMEFujYlTptFfrdNbxBUCvuRmdvccDWa0parQl2vVQAJW4NM0QGBSDcOm2YAdsHdDdvgN249RCXZu19oDkAOAgtToSdHFgicweBwe-S726n60fanl9sw3awB-Y3VujgIiOVarAPji+sXnAF2kKTugW2qEh11SVoe9qiE05Ua1i53XfApaHupkBNP7Otfs9z2wcK+fg7Z61sXTWaelca3wKXAuuCpbF-FgAHhEGwIAUCMD0LAYnoc+AACEACiAA5AAOkoA3ABBAAKgbu7AByAAymbtAKA9eNqt2bgAwgABQAKpm4ACKNod97jrFuACaXvG13c97793rAVdCAXo9gzLN8CH3oHAkAevPcB7N3dgA8gAWQT74Xj3By-4HgfgNJoO+Ce4L77o3Nu7ul+c4wQgdCT60EIP4LgYQAAUAApAArkoAALmb8fAB7M3ABjAAnnPhQSAp8AAsABO0+R-FzX+v1fSgAB2I+AC2AAjJAG+lBm4AJaH-3-n4vABKUvBBGBUBe6yzA-dM84FoA3pvFvV-SgMwF+IgRwHAdeTPTOIPAAcXdwAHpvcC8Hd3dG0C9TcTdD8A8DcG8cDW8gA" target="_blank">circuit</a> to visualize this process.


<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/4.gif" alt="Figure 4: SAP-1 Display module">
    <figcaption>Figure 4: SAP-1 Display module</figcaption>
</figure>
<br>


This is the highest frequency at which I could run the simulation with a decent recording render. This is just a replica, limited by lots of underlying code; the real circuit runs so fast that the switching rate cannot be perceived with the naked eyes. 

This simulation follows the same logic as the SAP-1’s display module. The bottom left counter is for demo purposes; it is just there to cycle through all the values stored in the BCD ROM. On the actual module, the ROM is driven by the output register. The lower 8 address bits of the ROM are what selects the digit to be displayed, while the next 2 higher address bits are used to select which display the digit must be displayed on. The most significant address bit selects the encoding mode(Signed or Unsigned). 

**Note:** *As of April 1, 2023 (the day I made this simulation), Falstad did not support 14-segment displays nor ROMs with an input address size greater than 15 bits. For these reasons, I will refer to the 7-segment display demo mentioned above when describing my version.*

# Implementation

## **Control lines involved(4):**

- \|← **~SE**    Segmented display enable: Turn ON the display.
- \|← **SdW**	Segmented display write: Loads the two 16-bit output register.
- \|← **SdT**	Segmented display: Loads the 8-bit output temporary register.
- \|← **SdM**	Segmented display Mode: Signed or unsigned.

My BCD ROM is an M27C160 16 Mbit (1 Mb x 16) UV EPROM. It has 20 address lines (A0 to A19) and 16 data lines (Q0 to Q15). Emulative of the SAP-1’s display ROM, the lower 16 address bits (A0 to A16 ) of my BCD ROM are what selects the digit to be displayed, while the next 3 higher address bits are used to select which display the digit must be displayed on. The most significant address bit selects the encoding mode(Unsigned or signed two’s complements). 

I did not have any 3-to-8 decoder at the time of making the display module, so I used the 74HCT139 Dual 2-Line To 4-Line Decoders to make a 3-to-8 decoder. Note that since I only have six displays, I only need 6 out of the 8 output lines of the decoder, therefore I tied the seventh output lines to the reset pin of the counter so that as soon as the display shows the last digit, no time is wasted on the the unused 7th and 8th output of the decoder, and the counter points right back to the first digit’s display.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/5.png" alt="Figure 5: Output Word Latching">
    <figcaption>Figure 5: 3-to-8 Decoder</figcaption>
</figure>
<br>


## Output Register

Since my display ROM supports 16-bit numbers, the driving register naturally has to be able to output 16-bit values. The output register however gets its input from the 8-bit data bus. I use a 16-bit register(made with to 8-bit registers), which is loaded in two cycles from a temporary register, and the data bus.

<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/6.png" alt="Figure 6: Output Word Latching">
    <figcaption>Figure 6: Output Word Latching</figcaption>
</figure>
<br>

The reason I use three registers(16-bit reg + temp reg) instead of two(just the 16-bit reg) is to keep whatever value being displayed unchanged even through transitions. 

The output register (Reg_1 and Reg_2) is always outputting to the ROM. In other words its “output enable” is always active.

Assume the display is currently displaying **00000** (`0000000000000000`), meaning Reg_1 and Reg_2 are holding `00000000` each.

Now let’s say I want to display **65534** (`1111111111111111`); meaning Reg_1 and Reg_2 must both be loaded with `11111111`.

With no temporary register, first Reg_1 would be loaded with `11111111`, a that point, the display would show **00255**, because Reg_2 is still holding `00000000`; which also means that the output register currently contains `0000000011111111`. It is not until at least one additional cycle that Reg_2 would be loaded with `11111111`, completing the whole value.

With the temp reg, first it would be loading it with `11111111`, at which point the **00000** on the display wouldn’t change. Then when loading Reg_2 with `11111111` Reg_1’s load signal is simultaneously activated so that it reads the `11111111` already stored in the temp reg. This way the display does not show unrelated transitional values when changing the content of the output register.
<br>
<figure>
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/posts/8-bit_bb_cpu/numerical_display/7.png" alt="Figure 7: Numerical Display Schematic">
    <figcaption>Figure 7: Numerical Display Schematic</figcaption>
</figure>
<br>

## BCD CODE

Below is a breakdown of the ROM organization and a Python code generating it:

```python
Import array
```

I’ve experimented with a couple of binary handling libraries to generate ROM images using Python, and I find the “array” module to be the simplest to use.

```python
# Segment patterns for digits on a 14-segment display.
# Modified the patterns for digits 0, 1, and 5.
digits = [0x3f, 0x6, 0xdb, 0x8f, 0xe6, 0xed, 0xfd, 0x7, 0xff, 0xef]
```

**Note:** *I have a GitHub [repository](https://github.com/Fadil-1/pins_encoding_for_segmented_displays) with code and a guide to generate digits and character patterns(ROM outputs) for different types of segmented displays.*

```python
# Opening/Creating the output file in binary mode to save ROM's image.
doc = open('rom1.bin', 'wb') 

# Constants for the ROM's output mode and the ROM size.
OUTPUT_WORD_SIZE = 16 
ROM_SIZE = 2**OUTPUT_WORD_SIZE

# Number of digits used, excluding sign digit.
DISPLAY_DIGITS = 5

# Deducting the number of unused states.
DECODER_SELECTS = 3
UNUSED_STATES = 2**DECODER_SELECTS - (DISPLAY_DIGITS + 1)

# Start address for unsigned numbers.
UNSIGNED_START = 0

# Start and end addresses for the sign of unsigned numbers.
UNSIGNED_0_START = UNSIGNED_END = ROM_SIZE*DISPLAY_DIGITS
UNSIGNED_0_END = UNSIGNED_0_START + ROM_SIZE

# Calculates the size to fill unused addresses with zeros.
FILL = ROM_SIZE*UNUSED_STATES

# Start and end addresses for the complements of numbers.
COMPLEMENT_START = UNSIGNED_0_END + FILL
COMPLEMENTS_SIGN_START = COMPLEMENT_END = COMPLEMENT_START + (ROM_SIZE*DISPLAY_DIGITS)
COMPLEMENTS_SIGN_END = COMPLEMENTS_SIGN_START + ROM_SIZE
```

### ROM Organization

1- **Addresses 0 to 393216 (First Half)**:

- This half of the ROM is divided into six sections, each corresponding to one of the six displays. Each section has 65536 addresses:

    1's place, from 0 to 65536
    10's place, from 65536 to 131072
    100's place, from 131072 to 196608
    1000's place, from 196608 to 262144
    10000's place, from 262144 to 327680
    Signs place, from 327680 to 393216,

    The signs place is the 6th tick of the counter(6 * 65,536 = 393,216).

    **Note:** *`"H"` in `write(array.array("H", []))`stands for unsigned short integers (Usually 2 bytes in most systems). It specifies the type of data that the array will hold.*

    ```python
    # Writes data for unsigned numbers.
    for i, index in enumerate(range(UNSIGNED_START, UNSIGNED_END, ROM_SIZE)):
      print(f"{10**i}'s place, from {index:,} to {index+ROM_SIZE:,}")
      for x in range(ROM_SIZE):
        doc.write(array.array("H", [ (digits[x % 10] if i==0 else digits[\
        int(x / (10**i))% 10])] ))
    ```

- The data in these sections represents unsigned numbers, with each section corresponding to a different place value in a decimal number (units, tens, hundreds, etc.).

    ```python
    # Writes data for the sign place of unsigned numbers.
    print(f"signs place, from {UNSIGNED_0_START:,} to {UNSIGNED_0_END:,}\n")
    for x in range(ROM_SIZE):
      doc.write(array.array("H", [0x0]))
    ```

2- **Addresses 393216 to 458,752 to 524288 (Middle Section)**:

- This area is unused and filled with zeros. It acts as a buffer zone between the sections for unsigned numbers and their complements.

    ```python
    # Fill unused addresses with zeros.
    print(f"Filling {UNSIGNED_0_END:,} to {UNSIGNED_0_END + FILL:,}\
    (unused addresses) with zeros\n")
    for x in range(FILL):
      doc.write(array.array("H", [0x0]))
    ```

3- **Addresses 524288 to 917504 (Second Half)**:

- This section is also divided into six segments, each with 65536 addresses.

    ```python
    # Writes data for the complements of numbers.
    for i, index in enumerate(range(COMPLEMENT_START, COMPLEMENT_END, ROM_SIZE)):
      print(f"Complements {10**i}'s place, from {index:,} to {index+ROM_SIZE:,}")
      for x in range(-(int(ROM_SIZE/2)), (int(ROM_SIZE/2))):
        doc.write(array.array("H", [ (digits[abs(int(x/(10**i))) % 10]) ]))
    ```

- These segments store the complements of the numbers. The data represents the negative values of the corresponding positive values in the first half. The two complements digits are activated using a switch connected to pin A19.

    ```python
    # Writes data for the sign place of complements.
    print(f"Complements signs place, from {COMPLEMENTS_SIGN_START:,} to \
    {COMPLEMENTS_SIGN_END:,}")
    for x in range(-(int(ROM_SIZE/2)), (int(ROM_SIZE/2))):
        if x < 0:
            doc.write(array.array("H", [0xc0]))
        else:
            doc.write(array.array("H", [0x0]))
    ```

- Just like in the first half, each segment represents a different place value.

4- **Addresses 917504 to 1048576 (End Section)**:

- This final section, like the middle one, is unused and filled with zeros. It fills the remainder of the ROM, ensuring the EEPROM image (bin file) size is the same as the EEPROM's actual size.

    ```python
    # Fills remaining unused addresses with zeros.
    print(f"Filling {COMPLEMENTS_SIGN_END:,} to {COMPLEMENTS_SIGN_END + FILL:,}\
    (unused addresses) with zeros\n")
    for x in range(FILL):
      doc.write(array.array("H", [0x0]))
    
    doc.close()
    ```
This code is also available on my [GitHub](https://github.com/Fadil-1/8-BIT-BREADBOARD-CPU).

<br>

## ICs

1x M27C160-100F1 27C160 16MBIT UV EPROM([Datasheet](https://media.digikey.com/pdf/Data%20Sheets/ST%20Microelectronics%20PDFS/M27C160.pdf))

1x LMC555CN CMOS Single 555 Timer Low Power ([Jameco](https://www.jameco.com/webapp/wcs/stores/servlet/ProductDisplay?langId=-1&storeId=10001&catalogId=10001&productId=126797), [Datasheet](https://www.jameco.com/Jameco/Products/ProdDS/126797Philips.pdf))

1x 74HCT161, Synchronous 4-Bit Binary Counter, ([Digikey](https://rocelec.widen.net/view/pdf/yyfxbvvpnb/cd54hc161.pdf?t.download=true&u=5oefqw), [Datasheet](https://www.jameco.com/Jameco/Products/ProdDS/46818.pdf))

2x74HCT245, Octal Bus Transceivers With 3-State Outputs, ([Digikey](https://www.digikey.com/en/products/detail/texas-instruments/CD74HCT245E/38454), [Datasheet](https://www.ti.com/general/docs/suppproductinfo.tsp?distId=10&gotoUrl=https%3A%2F%2Fwww.ti.com%2Flit%2Fgpn%2Fcd74hc245))

1x Common-Cathode 6-digits 14-segment display, ([Alibaba](https://www.alibaba.com/product-detail/6-digits-14-segments-Red-green_60748284169.html))

1x Dual 2-Line To 4-Line Decoders/Demultiplexers ([Digikey](https://www.digikey.com/en/products/detail/texas-instruments/SN74HCT139N/376857), [Datasheet](https://www.ti.com/general/docs/suppproductinfo.tsp?distId=10&gotoUrl=https%3A%2F%2Fwww.ti.com%2Flit%2Fgpn%2Fsn74hct139))

<br>

[**<<<<<<<<<<<<<<<<<<<< Previous Post: EPROM Programmer**]({{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-eprom_programmer.md %})

<a href="{{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-pc_&_sp.md %}"><span class="wide-space"></span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Next Post: Program Counter and Stack Pointer     >>>>>>>>>>>>>>>>>>>>**</a>

<i class="fas fa-calendar-alt"></i> <span style="font-size: 15px; font-weight: bolder;">Updated:  </span><time>March 31, 2024</time>