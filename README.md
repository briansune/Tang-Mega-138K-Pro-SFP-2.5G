# TangMega-138KPro-SFP-2.5G

## If this project is constructive, welcome to donate a drink to PayPal.

<img src="https://github.com/briansune/FPGA-Camera-MIPI-DVP-Verilog/assets/29487339/75ccc568-4f17-48a1-b2af-20211f98896c" style="height:20%; width:20%">

This example is modified from https://www.gowinsemi.com/en/support/ip_detail/150/

The purpose of the SFP 2.5G loop is to verify the sanity of the SFP+ hardware and interface.

The reference clock of the serial high speed bank 1 is 125MHz. Such reference clock is generated from the U2 MS5351M.

No IIC is needed to setup the MS5351M oscillator as OTP is set to 125MHz (differential clock).

## User would require a SFP+ adapter 2G or above.

![image](https://github.com/briansune/TangMega-138KPro-SFP-2.5G/assets/29487339/94bcc062-ae9a-4b0e-953e-0976f0121516)

![image](https://github.com/briansune/TangMega-138KPro-SFP-2.5G/assets/29487339/3d0eea7d-f153-4627-bed8-84c6477f4094)

# How to test?

Open serial terminal (no newline and carrier return)

Enter the following address:

1) E> W 0003 F5A1490D
2) E> R 0003
3) R< G 0003 F5A1490D
4) E> R 0080
5) R< G 0080 80000000
6) E> W 0000 00000001
7) E> W 0001 00000001
8) E> W 0030 00000021  // LED should off
9) E> W 0030 00000001
10) E> W 0020 00000063
11) E> W 0011 00000003  // LED should off (link down)
12) E> W 0011 00000002  // LED should on (link up)

Reference: https://www.gowinsemi.com/upload/database_doc/2787/document/65c1e06fef5ce.pdf
