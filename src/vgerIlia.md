%{
#include "vgerIlia.md.pre.c"
%}
%start stmt
%term CNSTF4=4113 CNSTF8=8209
%term CNSTI1=1045 CNSTI2=2069 CNSTI4=4117
%term CNSTP2=2071
%term CNSTU1=1046 CNSTU2=2070 CNSTU4=4118

%term ARGB=41
%term ARGF4=4129 ARGF8=8225
%term ARGI2=2085 ARGI4=4133
%term ARGP2=2087
%term ARGU2=2086 ARGU4=4134

%term ASGNB=57
%term ASGNF4=4145 ASGNF8=8241
%term ASGNI1=1077 ASGNI2=2101 ASGNI4=4149
%term ASGNP2=2103
%term ASGNU1=1078 ASGNU2=2102 ASGNU4=4150

%term INDIRB=73
%term INDIRF4=4161 INDIRF8=8257
%term INDIRI1=1093 INDIRI2=2117 INDIRI4=4165
%term INDIRP2=2119
%term INDIRU1=1094 INDIRU2=2118 INDIRU4=4166

%term CVFF4=4209 CVFF8=8305
%term CVFI2=2165 CVFI4=4213

%term CVIF4=4225 CVIF8=8321
%term CVII1=1157 CVII2=2181 CVII4=4229
%term CVIU1=1158 CVIU2=2182 CVIU4=4230

%term CVPU2=2198

%term CVUI1=1205 CVUI2=2229 CVUI4=4277
%term CVUP2=2231
%term CVUU1=1206 CVUU2=2230 CVUU4=4278

%term NEGF4=4289 NEGF8=8385
%term NEGI2=2245 NEGI4=4293

%term CALLB=217
%term CALLF4=4305 CALLF8=8401
%term CALLI2=2261 CALLI4=4309
%term CALLP2=2263
%term CALLU2=2262 CALLU4=4310
%term CALLV=216

%term RETF4=4337 RETF8=8433
%term RETI2=2293 RETI4=4341
%term RETP2=2295
%term RETU2=2294 RETU4=4342
%term RETV=248

%term ADDRGP2=2311

%term ADDRFP2=2327

%term ADDRLP2=2343

%term ADDF4=4401 ADDF8=8497
%term ADDI2=2357 ADDI4=4405
%term ADDP2=2359
%term ADDU2=2358 ADDU4=4406

%term SUBF4=4417 SUBF8=8513
%term SUBI2=2373 SUBI4=4421
%term SUBP2=2375
%term SUBU2=2374 SUBU4=4422

%term LSHI2=2389 LSHI4=4437
%term LSHU2=2390 LSHU4=4438

%term MODI2=2405 MODI4=4453
%term MODU2=2406 MODU4=4454

%term RSHI2=2421 RSHI4=4469
%term RSHU2=2422 RSHU4=4470

%term BANDI2=2437 BANDI4=4485
%term BANDU2=2438 BANDU4=4486

%term BCOMI2=2453 BCOMI4=4501
%term BCOMU2=2454 BCOMU4=4502

%term BORI2=2469 BORI4=4517
%term BORU2=2470 BORU4=4518

%term BXORI2=2485 BXORI4=4533
%term BXORU2=2486 BXORU4=4534

%term DIVF4=4545 DIVF8=8641
%term DIVI2=2501 DIVI4=4549
%term DIVU2=2502 DIVU4=4550

%term MULF4=4561 MULF8=8657
%term MULI2=2517 MULI4=4565
%term MULU2=2518 MULU4=4566

%term EQF4=4577 EQF8=8673
%term EQI2=2533 EQI4=4581
%term EQU2=2534 EQU4=4582

%term GEF4=4593 GEF8=8689
%term GEI2=2549 GEI4=4597
%term GEU2=2550 GEU4=4598

%term GTF4=4609 GTF8=8705
%term GTI2=2565 GTI4=4613
%term GTU2=2566 GTU4=4614

%term LEF4=4625 LEF8=8721
%term LEI2=2581 LEI4=4629
%term LEU2=2582 LEU4=4630

%term LTF4=4641 LTF8=8737
%term LTI2=2597 LTI4=4645
%term LTU2=2598 LTU4=4646

%term NEF4=4657 NEF8=8753
%term NEI2=2613 NEI4=4661
%term NEU2=2614 NEU4=4662

%term JUMPV=584

%term LABELV=600

%%
stmt: s ""

f4: CNSTF4 "CNSTF4[%a]"
f8: CNSTF8 "CNSTF8[%a]"
i1: CNSTI1 "CNSTI1[%a]"
i2: CNSTI2 "CNSTI2[%a]"
i4: CNSTI4 "CNSTI4[%a]"
p2: CNSTP2 "CNSTP2[%a]"
u1: CNSTU1 "CNSTU1[%a]"
u2: CNSTU2 "CNSTU2[%a]"
u4: CNSTU4 "CNSTU4[%a]"

s: ARGB(INDIRB(p2)) "ARGB[%a](%0)\n"
s: ARGF4(f4) "ARGF4(%0)\n"
s: ARGF8(f8) "ARGF8(%0)\n"
s: ARGI2(i2) "ARGI2(%0)\n"
s: ARGI4(i4) "ARGI4(%0)\n"
s: ARGP2(p2) "ARGP2(%0)\n"
s: ARGU2(u2) "ARGU2(%0)\n"
s: ARGU4(u4) "ARGU4(%0)\n"

s: ASGNB(p2, INDIRB(p2)) "ASGNB[%a](%1, %0)\n"
s: ASGNF4(p2, f4) "ASGNF4(%1, %0)\n"
s: ASGNF8(p2, f8) "ASGNF8(%1, %0)\n"
s: ASGNI1(p2, i1) "ASGNI1(%1, %0)\n"
s: ASGNI2(p2, i2) "ASGNI2(%1, %0)\n"
s: ASGNI4(p2, i4) "ASGNI4(%1, %0)\n"
s: ASGNP2(p2, p2) "ASGNP2(%1, %0)\n"
s: ASGNU1(p2, u1) "ASGNU1(%1, %0)\n"
s: ASGNU2(p2, u2) "ASGNU2(%1, %0)\n"
s: ASGNU4(p2, u4) "ASGNU4(%1, %0)\n"

s: INDIRB(p2) ".error INDIRB(%0)\n"
f4: INDIRF4(p2) "INDIRF4(%0)"
f8: INDIRF8(p2) "INDIRF8(%0)"
i1: INDIRI1(p2) "INDIRI1(%0)"
i2: INDIRI2(p2) "INDIRI2(%0)"

s: INDIRI2(p2) "INDIRI2(%0)\n"

i4: INDIRI4(p2) "INDIRI4(%0)"
p2: INDIRP2(p2) "INDIRP2(%0)"
u1: INDIRU1(p2) "INDIRU1(%0)"
u2: INDIRU2(p2) "INDIRU2(%0)"
u4: INDIRU4(p2) "INDIRU4(%0)"

f4: CVFF4(f8) "cv_f8_to_f4(%0)"
f8: CVFF8(f4) "cv_f4_to_f8(%0)"
i2: CVFI2(f4) "cv_f4_to_i2(%0)"
i2: CVFI2(f8) "cv_f8_to_i2(%0)"
i4: CVFI4(f4) "cv_f4_to_i4(%0)"
i4: CVFI4(f8) "cv_f8_to_i4(%0)"

ix: i1 "%0"
ix: i2 "%0"
ix: i4 "%0"

f4: CVIF4(i1) "cv_i1_to_f4(%0)"
f4: CVIF4(i2) "cv_i2_to_f4(%0)"
f4: CVIF4(i4) "cv_i4_to_f4(%0)"
f8: CVIF8(ix) ".error wait and see what incoming sizes we need" 100
f8: CVIF8(i2) "cv_i2_to_f8(%0)"
f8: CVIF8(i4) "cv_i4_to_f8(%0)"
i1: CVII1(ix) ".error wait and see what incoming sizes we need" 100
i1: CVII1(i2) "cv_i2_to_i1(%0)"
i1: CVII1(i4) "cv_i4_to_i1(%0)"
i2: CVII2(ix) ".error wait and see what incoming sizes we need" 100
i2: CVII2(i1) "cv_i1_to_i2(%0)"
i2: CVII2(i4) "cv_i4_to_i2(%0)"
i4: CVII4(ix) ".error wait and see what incoming sizes we need" 100
i4: CVII4(i2) "cv_i2_to_i4(%0)"
u1: CVIU1(ix) ".error wait and see what incoming sizes we need" 100
u1: CVIU1(i2) "cv_i2_to_u1(%0)"
u2: CVIU2(ix) ".error wait and see what incoming sizes we need" 100
u2: CVIU2(i2) "cv_i2_to_u2(%0)"
u2: CVIU2(i4) "cv_i4_to_u2(%0)"
u4: CVIU4(ix) ".error wait and see what incoming sizes we need" 100
u4: CVIU4(i2) "cv_i2_to_u4(%0)"
u4: CVIU4(i4) "cv_i4_to_u4(%0)"

u2: CVPU2(p2) ".error CVPU2(%0) ;no other backend handles these\n"

ux: u1 "%0"
ux: u2 "%0"
ux: u4 "%0"

i1: CVUI1(ux) ".error wait and see what incoming sizes we need" 100
i2: CVUI2(ux) ".error wait and see what incoming sizes we need" 100
i2: CVUI2(u1) "cv_u1_to_i2(%0)"
i2: CVUI2(u2) "cv_u2_to_i2(%0)"
i2: CVUI2(u4) "cv_u4_to_i2(%0)"
i4: CVUI4(ux) ".error wait and see what incoming sizes we need" 100
i4: CVUI4(u2) "cv_u2_to_i4(%0)"
i4: CVUI4(u4) "cv_u4_to_i4(%0)"
p2: CVUP2(ux) ".error wait and see what incoming sizes we need" 100
p2: CVUP2(u2) "cv_u2_to_p2(%0)"
u1: CVUU1(ux) ".error wait and see what incoming sizes we need" 100
u1: CVUU1(u2) "cv_u2_to_u1(%0)"
u1: CVUU1(u4) "cv_u4_to_u1(%0)"
u2: CVUU2(ux) ".error wait and see what incoming sizes we need" 100
u2: CVUU2(u1) "cv_u1_to_u2(%0)"
u2: CVUU2(u4) "cv_u4_to_u2(%0)"
u4: CVUU4(ux) ".error wait and see what incoming sizes we need" 100
u4: CVUU4(u2) "cv_u2_to_u4(%0)"

f4: NEGF4(f4) "NEGF4(%0)"
f8: NEGF8(f8) "NEGF8(%0)"
i2: NEGI2(i2) "NEGI2(%0)"
i4: NEGI4(i4) "NEGI4(%0)"

callAddress: p2 "%a"
resultAddress: p2 "%a"
s: CALLB(callAddress, resultAddress) "CALLB(%1, %0)\n"
f4: CALLF4(p2) "call(%0)"
f8: CALLF8(p2) "call(%0)"
i2: CALLI2(p2) "call(%0)" 100
i4: CALLI4(p2) "call(%0)"
p2: CALLP2(p2) "call(%0)"
u2: CALLU2(p2) "call(%0)"
u4: CALLU4(p2) "call(%0)"

s: CALLF4(p2) "discardF4(call(%0))\n"
s: CALLF8(p2) "discardF8(call(%0))\n"
s: CALLI2(p2) "discardI2(call(%0))\n"
s: CALLI4(p2) "discardI4(call(%0))\n"
s: CALLP2(p2) "discardP2(call(%0))\n"
s: CALLU2(p2) "discardU2(call(%0))\n"
s: CALLU4(p2) "discardU4(call(%0))\n"
s: CALLV(p2) "callv(%0)\n"


s: RETF4(f4) "RETF4(%0)\n"
s: RETF8(f8) "RETF8(%0)\n"
s: RETI2(i2) "RETI2(%0)\n"
s: RETI4(i4) "RETI4(%0)\n"
s: RETP2(p2) "RETP2(%0)\n"
s: RETU2(u2) "RETU2(%0)\n"
s: RETU4(u4) "RETU4(%0)\n"

anyRetV: i1 "%a"
anyRetV: i2 "%a"
anyRetV: i4 "%a"
anyRetV: u1 "%a"
anyRetV: u2 "%a"
anyRetV: u4 "%a"
anyRetV: f4 "%a"
anyRetV: f8 "%a"
anyRetV: p2 "%a"
s: RETV(anyRetV) "RETV(%0)\n"

p2: ADDRGP2 "ADDRGP2(%a)"

p2: ADDRFP2 "ADDRFP2(%a)"

p2: ADDRLP2 "ADDRLP2(%a)"

pOffset: p2 "%0"
pOffset: i1 "sex_8_to_16(%0)"
pOffset: i2 "%0"
pOffset: u1 "zex_8_to_16(%0)"
pOffset: u2 "%0"

f4: ADDF4(f4, f4) "ADDF4(%0, %1)"
f8: ADDF8(f8, f8) "ADDF8(%0, %1)"
i2: ADDI2(i2, i2) "ADDI2(%0, %1)"
i4: ADDI4(i4, i4) "ADDI4(%0, %1)"
p2: ADDP2(p2, pOffset) "ADDP2(%0, %1)"
p2: ADDP2(pOffset, p2) "ADDP2(%0, %1)"
u2: ADDU2(u2, u2) "ADDU2(%0, %1)"
u4: ADDU4(u4, u4) "ADDU4(%0, %1)"

f4: SUBF4(f4, f4) "SUBF4(%0, %1)"
f8: SUBF8(f8, f8) "SUBF8(%0, %1)"
i2: SUBI2(i2, i2) "SUBI2(%0, %1)"
i4: SUBI4(i4, i4) "SUBI4(%0, %1)"
p2: SUBP2(p2, pOffset) "SUBP2(%0, %1)"
p2: SUBP2(pOffset, p2) "SUBP2(%0, %1)"
u2: SUBU2(u2, u2) "SUBU2(%0, %1)"
u4: SUBU4(u4, u4) "SUBU4(%0, %1)"

i2: LSHI2(i2,i2) "LSHI2(%0, %1)"
i4: LSHI4(i4,i2) "LSHI4(%0, %1)"
u2: LSHU2(u2,i2) "LSHU2(%0, %1)"
u4: LSHU4(u4,i2) "LSHU4(%0, %1)"

i2: MODI2(i2, i2) "MODI2(%0, %1)"
i4: MODI4(i4, i4) "MODI4(%0, %1)"
u2: MODU2(u2, u2) "MODU2(%0, %1)"
u4: MODU4(u4, u4) "MODU4(%0, %1)"

i2: RSHI2(i2, i2) "RSHI2(%0,%1)"
i4: RSHI4(i4, i2) "RSHI4(%0,%1)"
u2: RSHU2(u2, i2) "RSHU2(%0,%1)"
u4: RSHU4(u4, i2) "RSHU4(%0,%1)"

i2: BANDI2(i2, i2) "BANDI2(%0, %1)"
i4: BANDI4(i4, i4) "BANDI4(%0, %1)"
u2: BANDU2(u2, u2) "BANDU2(%0, %1)"
u4: BANDU4(u4, u4) "BANDU4(%0, %1)"
u4: BANDU4(u4, u2) "BANDU4(%0, cv_u2_to_u4(%1))"

i2: BCOMI2(i2) "BCOMI2(%0)"
i4: BCOMI4(i4) "BCOMI4(%0)"
u2: BCOMU2(u2) "BCOMU2(%0)"
u4: BCOMU4(u4) "BCOMU4(%0)"

i2: BORI2(i2, i2) "BORI2(%0, %1)"
i4: BORI4(i4, i4) "BORI4(%0, %1)"
u2: BORU2(u2, u2) "BORU2(%0, %1)"
u4: BORU4(u4, u4) "BORU4(%0, %1)"

i2: BXORI2(i2, i2) "BXORI2(%0, %1)"
i4: BXORI4(i4, i4) "BXORI4(%0, %1)"
u2: BXORU2(u2, u2) "BXORU2(%0, %1)"
u4: BXORU4(u4, u4) "BXORU4(%0, %1)"

f4: DIVF4(f4, f4) "DIVF4(%0, %1)"
f8: DIVF8(f8, f8) "DIVF8(%0, %1)"
i2: DIVI2(i2, i2) "DIVI2(%0, %1)"
i4: DIVI4(i4, i4) "DIVI4(%0, %1)"
u2: DIVU2(u2, u2) "DIVU2(%0, %1)"
u4: DIVU4(u4, u4) "DIVU4(%0, %1)"

f4: MULF4(f4, f4) "MULF4(%0, %1)"
f8: MULF8(f8, f8) "MULF8(%0, %1)"
i2: MULI2(i2, i2) "MULI2(%0, %1)"
i4: MULI4(i4, i4) "MULI4(%0, %1)"
u2: MULU2(u2, u2) "MULU2(%0, %1)"
u4: MULU4(u4, u4) "MULU4(%0, %1)"

s: EQF4(f4, f4) "EQF4[%a](%0, %1)\n"
s: EQF8(f8, f8) "EQF8[%a](%0, %1)\n"
s: EQI2(i2, i2) "EQI2[%a](%0, %1)\n"
s: EQI4(i4, i4) "EQI4[%a](%0, %1)\n"
s: EQU2(u2, u2) "EQU2[%a](%0, %1)\n"
s: EQU4(u4, u4) "EQU4[%a](%0, %1)\n"

s: GEF4(f4, f4) "GEF4[%a](%0, %1)\n"
s: GEF8(f8, f8) "GEF8[%a](%0, %1)\n"
s: GEI2(i2, i2) "GEI2[%a](%0, %1)\n"
s: GEI4(i4, i4) "GEI4[%a](%0, %1)\n"
s: GEU2(u2, u2) "GEU2[%a](%0, %1)\n"
s: GEU4(u4, u4) "GEU4[%a](%0, %1)\n"

s: GTF4(f4, f4) "GTF4[%a](%0, %1)\n"
s: GTF8(f8, f8) "GTF8[%a](%0, %1)\n"
s: GTI2(i2, i2) "GTI2[%a](%0, %1)\n"
s: GTI4(i4, i4) "GTI4[%a](%0, %1)\n"
s: GTU2(u2, u2) "GTU2[%a](%0, %1)\n"
s: GTU4(u4, u4) "GTU4[%a](%0, %1)\n"

s: LEF4(f4, f4) "LEF4[%a](%0, %1)\n"
s: LEF8(f8, f8) "LEF8[%a](%0, %1)\n"
s: LEI2(i2, i2) "LEI2[%a](%0, %1)\n"
s: LEI4(i4, i4) "LEI4[%a](%0, %1)\n"
s: LEU2(u2, u2) "LEU2[%a](%0, %1)\n"
s: LEU4(u4, u4) "LEU4[%a](%0, %1)\n"

s: LTF4(f4, f4) "LTF4[%a](%0, %1)\n"
s: LTF8(f8, f8) "LTF8[%a](%0, %1)\n"
s: LTI2(i2, i2) "LTI2[%a](%0, %1)\n"
s: LTI4(i4, i4) "LTI4[%a](%0, %1)\n"
s: LTU2(u2, u2) "LTU2[%a](%0, %1)\n"
s: LTU4(u4, u4) "LTU4[%a](%0, %1)\n"

s: NEF4(f4, f4) "NEF4[%a](%0, %1)\n"
s: NEF8(f8, f8) "NEF8[%a](%0, %1)\n"
s: NEI2(i2, i2) "NEI2[%a](%0, %1)\n"
s: NEI4(i4, i4) "NEI4[%a](%0, %1)\n"
s: NEU2(u2, u2) "NEU2[%a](%0, %1)\n"
s: NEU4(u4, u4) "NEU4[%a](%0, %1)\n"

s: JUMPV(p2) "jmp(%0)\n"

s: LABELV "    %a:\n"

%%
#include "vgerIlia.md.post.c"