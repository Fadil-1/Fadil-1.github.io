---
layout: 8-bit_breadboard_CPU
title: Instructions
mathjax: true
similar: 8-bit-computers
date_child: "May 27, 2023"
category: children
parent: 8-bit_breadboard_CPU
permalink: /blog/8-bit_breadboard_CPU/instructions/ 
---

# Instructions

RST

| Microsteps | Control Word |
| --- | --- |
| t_0 | ZW, _OC |
| t_1 | ZW, _OC |
| t_2 | IR_in, BRlW, RD_0, RD_1, RD_2, RD_3, WR_1, BRhW, _OC |
| t_3 | _FW, Z1, ZS, SPW, Z0, RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, _BRE, _OC |
| t_4 | _SPC, SPD, RD_0, RD_1, RD_2, RD_3, WR_0, WR_2 |
| t_5 | Z1, ZS, H_cin, _BW , _DW , GW, RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, WR_2 |
| t_6 | ZS, ZW |
| t_7 | Z1, ZS, H_cin, RD_0, RD_1, RD_2, RD_3 |
| t_8 | ZS, ZW |
| t_9 | RD_0, RD_1, RD_2, RD_3, BRhW |
| t_10 | _PCW, _BRE |
| t_11 | TI |
| t_12 |  |
| t_13 |  |
| t_14 |  |
| t_15 | IR_in, RD_2, _PCE |

STC

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, Z2, ZS, Z0 |
| t_2 | _ScR |

CLC

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, Z2, ZS |
| t_2 | _ScR |

MOV  $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, WR_1, PCC, _PCE |
| t_2 | _ScR |

ADD  $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1, PCC |
| t_5 | _ScR |

SUB  $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1, PCC |
| t_5 | _ScR |

AND  $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1, PCC |
| t_5 | _ScR |

OR   $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1, PCC |
| t_5 | _ScR |

XOR  $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1, PCC |
| t_5 | _ScR |

CMP  $A, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, PCC, _PCE |
| t_4 | _ScR |

MOV  $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _BW , RD_2, PCC, _PCE |
| t_2 | _ScR |

ADD  $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, _PCE, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

SUB  $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, _PCE, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

AND  $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, _PCE, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

OR   $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, _PCE, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

XOR  $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, _PCE, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

CMP  $B, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, PCC, _PCE |
| t_4 | _ScR |

MOV  $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, WR_0, WR_1, PCC, _PCE |
| t_2 | _ScR |

ADD  $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, PCC |
| t_5 | _ScR |

SUB  $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, PCC |
| t_5 | _ScR |

AND  $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, PCC |
| t_5 | _ScR |

OR   $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, PCC |
| t_5 | _ScR |

XOR  $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, _PCE, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1, PCC |
| t_5 | _ScR |

CMP  $C, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, PCC, _PCE |
| t_4 | _ScR |

MOV  $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _DW , RD_2, PCC, _PCE |
| t_2 | _ScR |

ADD  $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, _PCE, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

SUB  $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, _PCE, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

AND  $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, _PCE, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

OR   $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, _PCE, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

XOR  $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, _PCE, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

CMP  $D, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, PCC, _PCE |
| t_4 | _ScR |

MOV  $E, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _DW , RD_2, PCC, _PCE |
| t_2 | _ScR |

ADD  $E, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _EE, Z0, Z1, ZS |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, _PCE, ZW |
| t_4 | EW, RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

SUB $E, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _EE, Z0, Z1, ZS |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, _PCE, ZW |
| t_4 | EW, RD_0, RD_1, RD_2, RD_3, PCC |
| t_5 | _ScR |

CMP  $E, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _EE, Z0, Z1, ZS |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, PCC, _PCE |
| t_4 | _ScR |

MOV  $A, $E

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _GE, WR_1 |
| t_2 | _ScR |

MOV  $E, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | GW, RD_2, RD_3 |
| t_2 | _ScR |

CMP  $E, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, _GE, Z0 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $B, $E

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _BW , _GE |
| t_2 | _ScR |

MOV  $E, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | GW, RD_0, RD_1, RD_3 |
| t_2 | _ScR |

CMP  $E, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, _GE, Z0 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3 |
| t_4 | _ScR |

MOV  $C, $E

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _GE, WR_0, WR_1 |
| t_2 | _ScR |

MOV  $E, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | GW, RD_0, RD_2, RD_3 |
| t_2 | _ScR |

CMP  $E, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, _GE, Z0 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $D, $E

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _DW , _GE |
| t_2 | _ScR |

MOV  $E, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | GW, RD_1, RD_2, RD_3 |
| t_2 | _ScR |

CMP  $E, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, _GE, Z0 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $CLK, #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _CLKW, RD_2, _PCE |
| t_2 | PCC |
| t_3 | _ScR |

MOV  $CLK, $E

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _CLKW, _GE |
| t_2 | _ScR |

MOV  $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3, WR_1 |
| t_2 | _ScR |

ADD  $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

SUB  $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

AND  $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

OR   $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

XOR  $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

CMP  $A, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3 |
| t_4 | _ScR |

MOV  $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_2, RD_3, WR_1 |
| t_2 | _ScR |

ADD  $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

SUB  $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

AND  $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

OR   $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

XOR  $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

CMP  $A, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_1, RD_2, RD_3, WR_1 |
| t_2 | _ScR |

ADD  $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

SUB  $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

AND  $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

OR   $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

XOR  $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_5 | _ScR |

CMP  $A, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _BW , RD_2, RD_3 |
| t_2 | _ScR |

ADD  $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

SUB  $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

AND  $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

OR   $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

XOR  $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

CMP  $B, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _BW , RD_0, RD_2, RD_3 |
| t_2 | _ScR |

ADD  $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

SUB  $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

AND  $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

OR   $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

XOR  $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_0, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

CMP  $B, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _BW , RD_1, RD_2, RD_3 |
| t_2 | _ScR |

ADD  $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

SUB  $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

AND  $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_1, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

OR   $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

XOR  $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_1, RD_2, RD_3, ZW |
| t_4 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

CMP  $B, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, RD_3, WR_0, WR_1 |
| t_2 | _ScR |

ADD  $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

SUB  $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

AND  $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

OR   $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

XOR  $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

CMP  $C, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3, WR_0, WR_1 |
| t_2 | _ScR |

ADD  $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

SUB  $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

AND  $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

OR   $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

XOR  $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_0, RD_1, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

CMP  $C, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3 |
| t_4 | _ScR |

MOV  $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_2 | _ScR |

ADD  $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

SUB  $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

AND  $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

OR   $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

XOR  $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_1, RD_2, RD_3, ZW |
| t_4 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_5 | _ScR |

CMP  $C, $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _DW , RD_2, RD_3 |
| t_2 | _ScR |

ADD  $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

SUB  $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

AND  $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

OR   $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

XOR  $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

CMP  $D, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _DW , RD_0, RD_1, RD_3 |
| t_2 | _ScR |

ADD  $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

SUB  $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

AND  $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_0, RD_1, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

OR   $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_0, RD_1, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

XOR  $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_0, RD_1, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

CMP  $D, $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_1, RD_3 |
| t_4 | _ScR |

MOV  $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _DW , RD_0, RD_2, RD_3 |
| t_2 | _ScR |

ADD  $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

SUB  $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

AND  $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z1, Z2, RD_0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

OR   $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, Z0, RD_0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

XOR  $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z2, RD_0, RD_2, RD_3, ZW |
| t_4 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_5 | _ScR |

CMP  $D, $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _FW, Z0, RD_0, RD_2, RD_3 |
| t_4 | _ScR |

MOV  $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | RD_2, WR_1, _BRE |
| t_4 | _ScR |

MOV  [$CD],$A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | RD_2, RD_3, _BRE, _MW |
| t_4 | _ScR |

ADD  $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

SUB  $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

AND  $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

OR   $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

XOR  $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

CMP  $A, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | _BW , RD_2, _BRE |
| t_4 | _ScR |

MOV  [$CD],$B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | RD_0, RD_1, RD_3, _BRE, _MW |
| t_4 | _ScR |

ADD  $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

SUB  $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

AND  $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

OR   $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

XOR  $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

CMP  $B, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | RD_2, WR_0, WR_1, _BRE |
| t_4 | _ScR |

MOV  [$CD], $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | RD_0, RD_2, RD_3, _BRE, _MW |
| t_4 | _ScR |

ADD  $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

SUB  $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

AND  $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

OR   $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

XOR  $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

CMP  $C, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | _DW , RD_2, _BRE |
| t_4 | _ScR |

MOV  [$CD],$D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | RD_1, RD_2, RD_3, _BRE, _MW |
| t_4 | _ScR |

ADD  $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

SUB  $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

AND  $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

OR   $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

XOR  $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

CMP  $D, [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3 |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | RD_2, WR_1, PCC, _BRE |
| t_4 | _ScR |

MOV  @, $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | RD_2, RD_3, PCC, _BRE, _MW |
| t_4 | _ScR |

ADD  $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

SUB  $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

AND  $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

OR   $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

XOR  $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_7 | _ScR |

CMP  $A, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _BW , RD_2, PCC, _BRE |
| t_4 | _ScR |

MOV  @,$B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | RD_0, RD_1, RD_3, PCC, _BRE, _MW |
| t_4 | _ScR |

ADD  $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

SUB  $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

AND  $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

OR   $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

XOR  $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

CMP  $B, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_1, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | RD_2, WR_0, WR_1, PCC, _BRE |
| t_4 | _ScR |

MOV  @,$C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | RD_0, RD_2, RD_3, PCC, _BRE, _MW |
| t_4 | _ScR |

ADD  $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

SUB  $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

AND  $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

OR   $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

XOR  $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_7 | _ScR |

CMP  $C, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_0, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

MOV  $D, @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _DW , RD_2, PCC, _BRE |
| t_4 | _ScR |

MOV  @,$D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | RD_1, RD_2, RD_3, PCC, _BRE, _MW |
| t_4 | _ScR |

ADD  $D,  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z0, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

SUB  $D,  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

AND  $D,  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z1, Z2, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

OR   $D,  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, Z0, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

XOR  $D,  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z2, RD_2, _BRE, ZW |
| t_6 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_7 | _ScR |

CMP  $D,  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | Z1, ZS, Z0, RD_1, RD_2, RD_3, PCC |
| t_4 | ZS, ZW |
| t_5 | _FW, Z0, RD_2, _BRE |
| t_6 | _ScR |

SDL  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, RD_3, WR_0, WR_2 |
| t_2 | _ScR |

SDL  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3, WR_0, WR_2 |
| t_2 | _ScR |

SDH  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, RD_3, WR_0, WR_1, WR_2 |
| t_2 | _ScR |

SDH  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3, WR_0, WR_1, WR_2 |
| t_2 | _ScR |

OUT  #,   RA

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, _PS, PCC, _PCE |
| t_2 | _PSW, RD_2, RD_3 |
| t_3 | _ScR |

INP  RA,  #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, _PS, PCC, _PCE |
| t_2 | _PSE, WR_1 |
| t_3 | _ScR |

OUT  RB,  RA

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3, _PS |
| t_2 | _PSW, RD_2, RD_3 |
| t_3 | _ScR |

INP  RA,  RB

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3, _PS |
| t_2 | _PSE, WR_1 |
| t_3 | _ScR |

OLR

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _OC |
| t_2 | _OC |
| t_3 | _OC |
| t_4 | _OC |
| t_5 | _OC |
| t_6 | _OC |
| t_7 | _ScR |

OLD  #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 |  RD_2, _PCE |
| t_2 | OE, RD_2, PCC, _PCE |
| t_3 | _ScR |

OLC  #

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _OS, RD_2, _PCE |
| t_2 | OE, _OS, RD_2, PCC, _PCE |
| t_3 | _ScR |

OLD  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_2, RD_3  |
| t_2 | OE, RD_2, RD_3  |
| t_3 | _ScR |

OLD  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_0, RD_1, RD_3 |
| t_2 | OE, RD_0, RD_1, RD_3 |
| t_3 | _ScR |

OLC  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _OS, RD_2, RD_3  |
| t_2 | _OE, _OS, RD_2, RD_3  |
| t_3 | _ScR |

OLC  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _OS, RD_0, RD_1, RD_3 |
| t_2 | _OE, _OS, RD_0, RD_1, RD_3 |
| t_3 | _ScR |

LSL  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, ZS, Z0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_4 | _ScR |

LSL  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, ZS, Z0, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

LSL  $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, ZS, Z0, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_4 | _ScR |

LSL  $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, ZS, Z0, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

LSL  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _FW, ZS, Z0, RD_2, _BRE |
| t_4 | ZS, PCC, ZW |
| t_5 | RD_0, RD_1, RD_2, RD_3, _BRE, _MW |
| t_6 | _ScR |

LSL  [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | _FW, ZS, Z0, RD_2, _BRE |
| t_4 | ZS, ZW |
| t_5 | RD_0, RD_1, RD_2, RD_3, _BRE, _MW |
| t_6 | _ScR |

LSR  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, Z1, ZS, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | RD_0, RD_1, RD_2, RD_3, WR_1 |
| t_4 | _ScR |

LSR  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, Z1, ZS, RD_0, RD_1, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _BW , RD_0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

LSR  $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, Z1, ZS, RD_0, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | RD_0, RD_1, RD_2, RD_3, WR_0, WR_1 |
| t_4 | _ScR |

LSR  $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _FW, Z1, ZS, RD_1, RD_2, RD_3 |
| t_2 | ZS, ZW |
| t_3 | _DW , RD_0, RD_1, RD_2, RD_3 |
| t_4 | _ScR |

LSR  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _FW, Z1, ZS, RD_2, _BRE |
| t_4 | ZS, PCC, ZW |
| t_5 | RD_0, RD_1, RD_2, RD_3, _BRE, _MW |
| t_6 | _ScR |

LSR  [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | _FW, Z1, ZS, RD_2, _BRE |
| t_4 | ZS, ZW |
| t_5 | RD_0, RD_1, RD_2, RD_3, _BRE, _MW |
| t_6 | _ScR |

PSH  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | SPD, RD_2, RD_3, _MW, _SPE |
| t_2 | _SPC, SPD |
| t_3 | _ScR |

PUL  $A

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC |
| t_2 | _DW , RD_2, _SPE |
| t_3 | _ScR |

PSH  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | SPD, RD_0, RD_1, RD_3, _MW, _SPE |
| t_2 | _SPC, SPD |
| t_3 | _ScR |

PUL  $B

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC |
| t_2 | _DW , RD_2, _SPE |
| t_3 | _ScR |

PSH  $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | SPD, RD_0, RD_2, RD_3, _MW, _SPE |
| t_2 | _SPC, SPD |
| t_3 | _ScR |

PUL  $C

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC |
| t_2 | _DW , RD_2, _SPE |
| t_3 | _ScR |

PSH  $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | SPD, RD_1, RD_2, RD_3, _MW, _SPE |
| t_2 | _SPC, SPD |
| t_3 | _ScR |

PUL  $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC |
| t_2 | _DW , RD_2, _SPE |
| t_3 | _ScR |

PSF  $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | SPD, RD_1, RD_3, _MW, _SPE |
| t_2 | _SPC, SPD |
| t_3 | _ScR |

PLF  $D

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC, ZW |
| t_2 | _FW, Z2, Z0, RD_2, _SPE |
| t_3 | _ScR |

MOV  $SP, $CD

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | SPW, _BRE |
| t_4 | _ScR |

MOV  $CD, $SP

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | RD_1, RD_2, WR_0, WR_1 |
| t_2 | _DW , RD_0, RD_1, RD_2 |
| t_3 | _ScR |

JMP  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _PCW, _BRE |
| t_4 | _ScR |

JSR  @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, PCC, _PCE, BRhW |
| t_3 | SPD, _PClE, _MW, _SPE |
| t_4 | _SPC, SPD |
| t_5 | SPD, _PChE, _MW, _SPE |
| t_6 | _SPC, SPD, _PCW, _BRE |
| t_7 | _ScR |

JMP  [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | _PCW, _BRE |
| t_4 | _ScR |

JSR  [$CD]

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_0, RD_2, RD_3 |
| t_2 | RD_1, RD_2, RD_3, BRhW |
| t_3 | SPD, _PClE, _MW, _SPE |
| t_4 | _SPC, SPD |
| t_5 | SPD, _PChE, _MW, _SPE |
| t_6 | _SPC, SPD, _PCW, _BRE |
| t_7 | _ScR |

RTS

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC |
| t_2 | RD_2, BRhW, _SPE |
| t_3 | _SPC |
| t_4 | BRlW, RD_2, _SPE |
| t_5 | _PCW, _BRE |
| t_6 | _ScR |

JZ @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _PCW, _BRE |
| t_4 | _ScR |

JO @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _PCW, _BRE |
| t_4 | _ScR |

JN @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _PCW, _BRE |
| t_4 | _ScR |

JC @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | BRlW, RD_2, PCC, _PCE |
| t_2 | RD_2, _PCE, BRhW |
| t_3 | _PCW, _BRE |
| t_4 | _ScR |

JNZ @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | PCC |
| t_2 | PCC |
| t_3 | _ScR |

JNO @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | PCC |
| t_2 | PCC |
| t_3 | _ScR |

JP @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | PCC |
| t_2 | PCC |
| t_3 | _ScR |

JNC @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | PCC |
| t_2 | PCC |
| t_3 | _ScR |

JGZ @

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | PCC |
| t_2 | PCC |
| t_3 | _ScR |

SII

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | TI |
| t_2 | _ScR |

CII

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _ScR |

ITR

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | TI, Z1, Z2, SPD, Z0, RD_1, RD_3, ZW, _MW, _SPE |
| t_2 | ZS, _SPC, SPD, Z0, RD_0, RD_1, RD_2, RD_3, BRhW |
| t_3 | ZS, SPD, _PClE, ZW, _MW, _SPE |
| t_4 | _SPC, SPD, BRlW, RD_0, RD_1, RD_2, RD_3 |
| t_5 | Z1, Z2, SPD, _PChE, Z0, ZW, _MW, _SPE |
| t_6 | Z1, Z2, _SPC, SPD, RD_2, _BRE, ZW |
| t_7 | SPD, RD_0, RD_1, RD_2, RD_3, _MW, _SPE |
| t_8 | Z1, Z2, Z0, ZW |
| t_9 | BRlW, RD_0, RD_1, RD_2, RD_3 |
| t_10 | Z1, Z2, RD_2, _BRE, ZW |
| t_11 | RD_0, RD_1, RD_2, RD_3, BRhW |
| t_12 | BRlW, RD_2, _SPE |
| t_13 | _FW, Z2, ZS, _PCW, _BRE |
| t_14 | _ScR |

RTI

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _SPC |
| t_2 | RD_2, BRhW, _SPE |
| t_3 | _SPC |
| t_4 | BRlW, RD_2, _SPE |
| t_5 | _SPC, _PCW, _BRE |
| t_6 | TI, _FW, Z1, ZS, Z0, RD_2, _SPE |
| t_7 | _ScR |

NOP

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | _ScR |

HLT

| Microsteps | Control Word |
| --- | --- |
| t_0 | IR_in, RD_2, PCC, _PCE |
| t_1 | HLT |
| t_2 | _ScR |


[**<<<<<<<<<<<<<<<<<<<< Previous Post: Microcode Generator**]({{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-microcode_generator.md %})

<a href="{{ site.baseurl }}{% link _posts/8-bit_breadboard_CPU/2023-05-27-oled_display.md %}"><span class="wide-space"></span><span class="wide-space"></span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Next Post: OLED Display     >>>>>>>>>>>>>>>>>>>>**</a>

<i class="fas fa-calendar-alt"></i> <span style="font-size: 15px; font-weight: bolder;">Updated:  </span><time>May 21, 2024</time>