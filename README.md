📘 6T CMOS SRAM Cell Design and Simulation (180nm Technology)
📌 Project Overview

Designed and simulated a 6-Transistor (6T) CMOS SRAM cell in 180nm CMOS technology using LTspice.
The objective was to analyze Read, Write, and Hold stability, evaluate Static Noise Margin (SNM), and measure standby leakage current under realistic bitline loading conditions.

🧱 Technology & Device Parameters
Parameter	Value
Technology Node	180 nm
Supply Voltage (VDD)	1.8 V
Channel Length (L)	180 nm
Pull-Up PMOS Width	2 µm
Pull-Down NMOS Width	1 µm
Access NMOS Width	1.2 µm
Bitline Capacitance	150 fF
Wordline Signal	PULSE (0 → 1.8V)
⚙️ Transistor Sizing and Ratio Calculations
1️⃣ Cell Ratio (CR)

Definition:

𝐶
𝑅
=
(
𝑊
/
𝐿
)
𝑝
𝑢
𝑙
𝑙
−
𝑑
𝑜
𝑤
𝑛
(
𝑊
/
𝐿
)
𝑎
𝑐
𝑐
𝑒
𝑠
𝑠
CR=
(W/L)
access
	​

(W/L)
pull−down
	​

	​


Since length is same (180nm) for all devices:

𝐶
𝑅
=
𝑊
𝑝
𝑢
𝑙
𝑙
−
𝑑
𝑜
𝑤
𝑛
𝑊
𝑎
𝑐
𝑐
𝑒
𝑠
𝑠
CR=
W
access
	​

W
pull−down
	​

	​

𝐶
𝑅
=
1
1.2
CR=
1.2
1
	​

𝐶
𝑅
=
0.83
CR=0.83
2️⃣ Pull-Up Ratio (PR)

Definition:

𝑃
𝑅
=
(
𝑊
/
𝐿
)
𝑎
𝑐
𝑐
𝑒
𝑠
𝑠
(
𝑊
/
𝐿
)
𝑝
𝑢
𝑙
𝑙
−
𝑢
𝑝
PR=
(W/L)
pull−up
	​

(W/L)
access
	​

	​

𝑃
𝑅
=
𝑊
𝑎
𝑐
𝑐
𝑒
𝑠
𝑠
𝑊
𝑝
𝑢
𝑙
𝑙
−
𝑢
𝑝
PR=
W
pull−up
	​

W
access
	​

	​

𝑃
𝑅
=
1.2
2
PR=
2
1.2
	​

𝑃
𝑅
=
0.6
PR=0.6
📊 Static Noise Margin (SNM)
3️⃣ Hold Static Noise Margin

Definition:

SNM is the side length of the largest square that can be embedded inside the butterfly curve obtained from DC transfer characteristics.

𝑆
𝑁
𝑀
ℎ
𝑜
𝑙
𝑑
=
𝑉
𝑡
𝑟
𝑖
𝑝
1
−
𝑉
𝑡
𝑟
𝑖
𝑝
2
2
SNM
hold
	​

=
2
V
trip1
	​

−V
trip2
	​

	​


From DC sweep simulation:

𝑆
𝑁
𝑀
ℎ
𝑜
𝑙
𝑑
≈
0.24
𝑉
SNM
hold
	​

≈0.24V
𝑆
𝑁
𝑀
ℎ
𝑜
𝑙
𝑑
≈
240
𝑚
𝑉
SNM
hold
	​

≈240mV
4️⃣ Read Static Noise Margin

During read operation, access transistor weakens the internal node.

𝑆
𝑁
𝑀
𝑟
𝑒
𝑎
𝑑
=
𝑉
𝑟
𝑒
𝑎
𝑑
−
𝑡
𝑟
𝑖
𝑝
1
−
𝑉
𝑟
𝑒
𝑎
𝑑
−
𝑡
𝑟
𝑖
𝑝
2
2
SNM
read
	​

=
2
V
read−trip1
	​

−V
read−trip2
	​

	​


From simulation:

𝑆
𝑁
𝑀
𝑟
𝑒
𝑎
𝑑
≈
0.18
𝑉
SNM
read
	​

≈0.18V
𝑆
𝑁
𝑀
𝑟
𝑒
𝑎
𝑑
≈
180
𝑚
𝑉
SNM
read
	​

≈180mV
📉 Leakage Current Analysis
5️⃣ Subthreshold Leakage Current

Subthreshold leakage is given by:

𝐼
𝑠
𝑢
𝑏
=
𝐼
0
𝑒
𝑉
𝐺
𝑆
−
𝑉
𝑡
ℎ
𝑛
𝑉
𝑇
I
sub
	​

=I
0
	​

e
nV
T
	​

V
GS
	​

−V
th
	​

	​


Where:

𝑉
𝑇
=
𝑘
𝑇
𝑞
V
T
	​

=
q
kT
	​


𝑛
n = subthreshold slope factor

Measured standby leakage during hold mode:

𝐼
𝑙
𝑒
𝑎
𝑘
𝑎
𝑔
𝑒
≈
18
 nA
  
to
  
35
 nA
I
leakage
	​

≈18 nAto35 nA
6️⃣ Total Cell Standby Power
𝑃
𝑠
𝑡
𝑎
𝑛
𝑑
𝑏
𝑦
=
𝑉
𝐷
𝐷
×
𝐼
𝑙
𝑒
𝑎
𝑘
𝑎
𝑔
𝑒
P
standby
	​

=V
DD
	​

×I
leakage
	​

𝑃
𝑠
𝑡
𝑎
𝑛
𝑑
𝑏
𝑦
=
1.8
×
35
 nA
P
standby
	​

=1.8×35 nA
𝑃
𝑠
𝑡
𝑎
𝑛
𝑑
𝑏
𝑦
≈
63
 nW
P
standby
	​

≈63 nW
📈 Write Margin

Write margin is defined as the minimum bitline voltage required to flip the stored state.

𝑊
𝑀
=
𝑉
𝐷
𝐷
−
𝑉
𝑓
𝑙
𝑖
𝑝
WM=V
DD
	​

−V
flip
	​


From simulation:

𝑊
𝑀
≈
0.35
𝑉
WM≈0.35V
𝑊
𝑀
≈
350
𝑚
𝑉
WM≈350mV
🔍 DC Sweep Analysis

DC voltage transfer characteristics were obtained by sweeping internal node voltage from 0 to 1.8V.

Butterfly curve extracted using:

𝑉
𝑜
𝑢
𝑡
1
=
𝑓
(
𝑉
𝑖
𝑛
)
V
out1
	​

=f(V
in
	​

)
𝑉
𝑜
𝑢
𝑡
2
=
𝑓
−
1
(
𝑉
𝑖
𝑛
)
V
out2
	​

=f
−1
(V
in
	​

)

Maximum embedded square side length gives SNM.

🛠 Simulations Performed

Transient analysis for functional verification

Leakage current measurement in hold mode

Write margin extraction

Bitline stability verification

📊 Final Measured Performance Summary
Parameter	Value
Hold SNM	≈ 240 mV
Read SNM	≈ 180 mV
Write Margin	≈ 350 mV
Standby Leakage	18 – 35 nA
Standby Power	≈ 63 nW
Cell Ratio (CR)	0.83
Pull-Up Ratio (PR)	0.6
