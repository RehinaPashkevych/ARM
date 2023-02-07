# ARM
<h4>Codes of Assembly Langauge ARM. I simulated it in the SSPARCSS simulator. </h4>

The program  [![Typing SVG](https://readme-typing-svg.herokuapp.com?color=%2336BCF7&lines=traffic_light.a)](https://git.io/typing-svg) shows implemented traffic light.

A GPIO circuit at address FFFF0B00(16) and an RTC at address FFFF0E00(16). LEDs are connected to the GPIO gate A as follows:
<ul>
<li> bit 5 – red</li> 
<li> bit 6 – yellow</li> 
<li>  bit 7 – green</li> 
 <ul>
  
The traffic light works by standard cycle change whose states given below.

<table>
<tr>
<th>state</th>
<th> description</th>
<th>red</th>
<th>yellow</th>
<th>green</th>
</tr>
<tr>
<th>1</th>
<th> Stop</th>
<th>1</th>
<th>0</th>
<th>0</th>
</tr>
<tr>
<th>2</th>
<th>Prepare to start   </th>
<th>1</th>
<th>1</th>
<th>0</th>
</tr>
<tr>
<th>3</th>
<th>Free to go </th>
<th>0</th>
<th>0</th>
<th>1</th>
</tr>
 <tr>
<th>4</th>
<th>Prepare to stop </th>
<th>0</th>
<th>1</th>
<th>0</th>
</tr>
</table>


Initial traffic light state is the Stop state (state 1). After that, traffic light starts cycling through the other states, i.e., once it reaches state 4, it starts again from state 1. Every state has an equal duration of exactly 5 seconds, and the duration must be measured with the RTC which works in interrupt mode and is connected to IRQ port. 

Additional note: You can suppose that the RTC counts signals of 1 Hz frequency. Exact duration of the simulation can be ignored because it depends on your computer, i.e., the platform on which the simulation is performed.
 
<h4> FRISC-V processor </h4>

  [![Typing SVG](https://readme-typing-svg.herokuapp.com?color=%2336BCF7&lines=frisc-caculator.a)](https://git.io/typing-svg)
  
Program  reads an Arabic format number and converts it into a Roman format number. The number which needs to be converted is in the memory at the address 0x500. I ssumed hat the number will be positive and in range from 1 to 10. The Roman format should simply be an ASCII code (or a series of ASCII codes) of the letters needed to represent the number.Once conversion is done, ASCII code(s) should be written in the memory, starting from the address 0x600. The program only converts a single number that is stored at the address 0x500.
 

