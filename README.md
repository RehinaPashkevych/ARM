# ARM
<h4>Codes of Assembly Langauge ARM. I simulated it in the SSPARCSS simulator. </h4>

The program <b><i>traffic_light.a</i></b> shows implemented traffic light.

A GPIO circuit at address FFFF0B00(16) and an RTC at address
FFFF0E00(16). LEDs are connected to the GPIO gate A as follows:
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


Initial traffic light state is the Stop state (state 1). After that, traffic light starts cycling through the other states,
i.e., once it reaches state 4, it starts again from state 1. Every state has an equal duration of exactly 5 seconds,
and the duration must be measured with the RTC which works in interrupt mode and is connected to IRQ port.
There are no other traffic lights in the system, e.g., traffic lights for the opposite direction and for pedestrians
shouldn’t be considered.

Additional note: You can suppose that the RTC counts signals of 1 Hz frequency. Exact duration of the simulation
can be ignored because it depends on your computer, i.e., the platform on which the simulation is performed.

<hr/>
