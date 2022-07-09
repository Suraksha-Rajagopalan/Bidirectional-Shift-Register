# Bi-directional Shift Register
<h2>Aim</h2>
<div>
To build a 8-bit bidirectional shift register.
</div>
<h2>Materials Required</h2>
<div>
  <ol>
    <li> <a href="https://support.arduino.cc/hc/en-us/articles/360018922259-What-power-supply-can-I-use-with-my-Arduino-board-" target="_main">Power Supply</a></li>   
    <li><a href="https://forum.arduino.cc/t/when-to-use-resistors-in-a-circuit/660075" target="_main">Resistors</a></li>
    <li><a href="https://www.nexperia.com/products/analog-logic-ics/synchronous-interface-logic/flip-flops/d-type-flip-flops/series/74LVC1G74.html" target="_main">7474 IC(D- Flip Flop)</a></li>
    <li><a href="https://learnabout-electronics.org/Digital/dig21.php" target="_main">Logic Gates(AND[7408], OR[7432], NOT[7404])</a></li>
    <li><a href="https://www.miwv.com/spst-switch/" target="_main">SPST Switch</a></li>
    <li><a href="https://learn.adafruit.com/lesson-0-getting-started/breadboard" target="_main">BreadBoard</a></li>
    <li><a href="https://create.arduino.cc/projecthub/rowan07/make-a-simple-led-circuit-ce8308" target="_main">LED</a></li>
 </ol>
</div>
<h2>Theory</h2>
<div>
Bidirectional shift registers are the storage devices which are capable of shifting the data either right or left depending on the mode selected. Figure 1 shows an n-bit bidirectional shift register with serial data loading and retrieval capacity. Initially all the flip-flops in the register are reset by driving their clear pins high. Next R/LÌ… control line is made either low or high in order to opt for either left-shift or right-shift of the data bits, respectively.

Now if R/L̅ = 1, then A1 gates of all the combinational circuits get activated while the A2 gates will get disabled at the same time. Due to this, the outputs of each flip-flop appear at the inputs of the very-next flip-flop via OR gate output (except for the last flip-flop FFn).

For example, Q1 appears at D2 via the output of OR gate 1 (O1), Q2 appears at D3 via the output of OR gate 2 (O2), … and Qn-1 appears at Dn via the output of OR gate 1 (On) (red lines). At this instant if the positive edge of the clock pulse appears, then the outputs of the respective flip-flops reflect their inputs. Thus Q1 = D1, Q2 = Q1,… and Qn = Qn-1. This is nothing but right-shift of the data by a single bit within the register. Following on the same grounds, one can note that for every rising edge of the clock, the data within the register shifts right by a single bit as long as R/L̅ remains high.

On the other hand, if R/L̅ goes low, then A2 gates of the combinational circuits get enabled while A1 gates get deactivated. This causes the outputs of each flip-flop to appear at the input pins of the very-previous flip-flop through their OR gate outputs (except the first flip-flop, FF1). For example, Qn appears at Dn-1 through the output of OR gate n-1 (On-1), … Q3 appears at D2 via the output of OR gate 2 (O2), and Q2 appears at D1 via the output of OR gate 1 (O1). These input bits are latched onto their respective output pins as soon as the leading edge of the clock pulse appears and thus Qn-1 = Qn, …Q2 = Q3 and Q1 = Q2 (green lines). This means that for every clock tick, the data within the register moves left by one bit, provided R/L̅ line is zero.

![image](https://user-images.githubusercontent.com/91787553/178094237-a0374ae0-1559-4537-8c94-76f8da1cb77b.png)

</div>

<h2>Circuit Diagram </h2>
![image](https://user-images.githubusercontent.com/91787553/178093742-c33a8359-4b06-42b0-b0de-76b1ed78f27c.png)

<h2>Simulation</h2>
<a href="https://www.tinkercad.com/things/jiKIg0RZY1M" target="_main">Simulation</a></li>
