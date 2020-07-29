# Logic-Desings-in-Logisim
Digital Systems Laboratory		

Objectives
•	To demonstrate the count sequence of binary number and the binary-coded decimal (BCD) representation.
•	To get familiar with BCD-to-7 segment decoders and 7-segment displays.

Apparatus
7493 4-bit ripple counter
7447 BCD-to-seven segment decoder
Seven segment display, common anode (CA)
330 ohm resistors (x10)

IC Description:

1.	BCD to 7-Segment Decoders

A light emitting Diode (LED) is a PN junction diode. When the diode is forward biased, a current flows through the junction and the light is emitted. See Fig.1.

 
![Figure1](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-Counter/152120171029_SayTasLabC_1920BHR_Uyg2/Images/Figure1.png)
 
Figure 1

A seven segment LED display contains 7 LEDs. Each LED is called a segment and they are identified as (a, b, c, d, e, f, g) segments Fig.2.


![Figure2](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-Counter/152120171029_SayTasLabC_1920BHR_Uyg2/Images/Figure2.png)

Figure 2. Decimal digits represented by the 7 segments

The display has 7 inputs each connected to an LED segment. All anodes of LEDs are tied together and joined to 5 volts (this type is called common anode type). A current limiting resistance network must be used at the inputs to protect the 7-segment from overloading. BCD inputs are converted into 7 segment inputs (a, b, c, d, e, f, g) by using a decoder, as shown in Fig.3.
Digital Systems Laboratory		

![Figure3](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-Counter/152120171029_SayTasLabC_1920BHR_Uyg2/Images/Figure3.png)

Figure 3

A decoder is a combinational circuit that converts binary information from n input lines to a maximum of 2 n output lines. The input to the decoder is a BCD code and the outputs of the systems are the seven segments a, b, c, d, e, f, and g. For further information and pin connections, consult the specification sheet for decoder and 7-segment units. 

The 7447 BCD-to-seven segment decoder is used to drive a seven-segment LED display. The outputs, a-g, drive the corresponding segments on the seven-segment display according to the binary number present at the inputs A-D, D being the most significant bit of the number. Three additional inputs, LAMP TEST, BI/RBO, and RBI are provided. The blanking input/ripple-blanking output (BI/RBO) blanks (turns off) the display when set LOW. Otherwise, when BI/RBO is set high, the outputs drive the display according to the inputs A-D. The ripple blanking input (RBI) must be HIGH if blanking of a decimal zero is not desired. This input is useful in blanking higher order zeroes when using several displays for a multi-digit decimal number. Finally, LAMP TEST selects (turns on) all the segments when set LOW. It is used to test the segments on the display.

Procedure

1.	Build the binary counter given in figure 4.  Check the binary counting sequence on 7-segment display. What do you think about the reason of insignificant symbols occurred on display? 



The 7-segment display can show figures (0-9), but our system can count from 0 to 15. Different leds become active when system is counting from 10 to 15, so it displays insignificant symbols after the figures are finished.

Evaluation

I did not use grounding and power and ohm resistance in the experiment because it presents them as simulation the Logisim platform. Since I had to add the integrations as a library, I drew the 7493 integration by looking at the internet. On the other hand, I created 7447 integrated on the logisim using the truth table. I have done the necessary tests and the simulation is working correctly as desired.









Digital Systems Laboratory		
	

![Figure4](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-Counter/152120171029_SayTasLabC_1920BHR_Uyg2/Images/Figure4.png)


Figure 4. Binary Counter Circuit
2.	Build the BCD counter given in figure 5. Check the BCD counting sequence on 7-segment display.


![Figure5](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-Counter/152120171029_SayTasLabC_1920BHR_Uyg2/Images/Figure5.png)


Figure 5. BCD Counter Circuit
