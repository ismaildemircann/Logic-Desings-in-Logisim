# Logic-Desings-in-Logisim

## [1) Counter](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/README.md#1-counter-1)
## [2) Math Operations](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/README.md#2-math-operations-1)
- ### [Main Tasarımı](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/README.md#main-tasar%C4%B1m%C4%B1-1)
## 1) Counter		

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

## 2) Math Operations


### Main Tasarımı

![Main Tasarımı](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/Main%20Tasar%C4%B1m%C4%B1.jpg)

Main tasarımında farklı üç tip fonksiyonumuz yer almaktadır. S inputu ile Multiplexer vasıtasıyla yapacağımız işlemi seçiyoruz. N inputu fonksiyondaki değişken sayıdır. Kullanıcı bu input vasıtasıyla hesaplamak istediği fonksiyon değerine ulaşabilir.

S	inputuna karşılık gelen fonksiyonlar:

01 (1) için 4N + 2

10 (2) için MOD (N, 2)

11 (3) için ABS (2*N – 3*2 + 5)

Fonksiyondan gelen outputu Splitter yardımıyla 2 tane 7 Segment Display’e bağladım.
 
### A)

![A](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/A.jpg)


Sonucu 7 Segment Display üzerinden gösterdiğim için oluşturduğum 7447 Decoder’i kullandım. Ve bu çıkışları 14 girişli bir Splitter ile outputa verdim.



#### F=4N+X

![F=4N+X](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/F%3D4N%2BX.jpg)

 

Bu fonksiyonda 4*N için Multipler, +X için Adder kullandım. Sonucu 7 Segment Display üzerinden gösterdiğim için Divider ile mod 10 işlemine tabi tuttum ve bölümden geleni soldaki Splitter’a, kalandan geleni sağdaki Splitter’a yönlendirdim.
 

A	B	C	D	a	b	c	d	e	f	g	g	F
												
0	0	0	0	0	0	0	0	0	0	1	0	1
												
0	0	0	1	0	0	0	0	0	1	1	0	1
												
0	0	1	0	0	0	0	0	1	0	1	0	1
												
0	0	1	1	0	0	0	0	1	1	1	0	1
												
0	1	0	0	0	0	0	1	0	0	1	0	1
												
0	1	0	1	0	0	0	1	0	1	1	0	1
												
0	1	1	0	0	0	0	1	1	0	1	0	1
												
0	1	1	1	0	0	0	1	1	1	1	0	1
												
1	0	0	0	0	0	1	0	0	0	1	0	1
												
1	0	0	1	0	0	1	0	0	1	1	0	1
												
1	0	1	0	0	0	1	0	1	0	1	0	1
												
1	0	1	1	0	0	1	0	1	1	1	0	1
												
1	1	0	0	0	0	1	1	0	0	1	0	1
												
1	1	0	1	0	0	1	1	0	1	1	0	1
												
1	1	1	0	0	0	1	1	1	0	1	0	1
												
1	1	1	1	0	0	1	1	1	1	1	0	1
												




Verilen doğruluk tablosu 4N + X fonksiyonuna aittir. Tabloda fonksiyonun sadece F = 1 olduğu değerler gösterilmiştir.

F = A’B’C’D’ + A’B’C’D + A’B’CD’ + A’B’CD + A’BC’D’ + A’BC’D + A’BCD’ + A’BCD + AB’C’D’ +AB’C’D+ AB’CD’+ AB’CD + ABC’D’ + ABC’D + ABCD’ + ABCD)

Karnaugh Map ile hesaplanan çıkışın 1 olması bize ifadenin sonucunun 1 olduğunu göstermektedir.

Minterms = ∑ (m0, m1, m2, m3, m4, m5, m6, m7, m8, m9, m10, m11, m12, m13, m14, m15)
 
### B)

![B](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/B.jpg)



Sonucu 7 Segment Display üzerinden gösterdiğim için oluşturduğum 7447 Decoder’i kullandım. Ve bu çıkışları 14 girişli bir Splitter ile outputa verdim. Bu devredeki Splitter’ın 14 girişe sahip olamasının nedeni main tasarımın da kullanılan Multiplexer’ın diğer fonksiyonlarla uyumlu olması ve ikili 7 Segment Display’e aktarılmasıdır. Bu yüzden kullanılmayan 7-13 arası girişler “none” olarak tutulmuştur.


#### F = MOD(N,X)

![F = MOD(N,X)](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/F%20%3D%20MOD(N%2CX).jpg)

Bu fonksiyonda 4 bitlik giriş için bir 4 bitlik bir Divider kullandım kalan sonucu Splitter ile outplara aktardım.
 

A	B	C	D	F
				
0	0	0	0	0
				
0	0	0	1	1
				
0	0	1	0	0
				
0	0	1	1	1
				
0	1	0	0	0
				
0	1	0	1	1
				
0	1	1	0	0
				
0	1	1	1	1
				
1	0	0	0	0
				
1	0	0	1	1
				
1	0	1	0	0
				
1	0	1	1	1
				
1	1	0	0	0
				
1	1	0	1	1
				
1	1	1	0	0
				
1	1	1	1	1
				
 


Verilen doğruluk tablosu MOD (N, X) fonksiyonuna aittir. Tabloda fonksiyonun sonuncunun tek sayı olduğu yani outputun 1 olduğu durumları F = 1 olarak varsaydım ve mintermleri buna göre oluşturdum. Çift sayılar için F = 0 kabul ettim.

F = A’B’C’D + A’B’CD + A’BC’D + A’BCD +AB’C’D+ AB’CD + ABC’D + ABCD

Karnaugh Map ile hesaplanan çıkışın D inputu ile aynı olması bize fonskiyonun sonucunun D olduğunu göstermektedir.

Minterms = ∑ (m1, m3, m5, m7, m9, m11, m13, m15)
 



### C)

![C](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/C.jpg)
 

Sonucu 7 Segment Display üzerinden gösterdiğim için oluşturduğum 7447 Decoder’i kullandım. Ve bu çıkışları 14 girişli bir Splitter ile outputa verdim. Bu devredeki Splitter’ın 14 girişe sahip olamasının nedeni main tasarımın da kullanılan Multiplexer’ın diğer fonksiyonlarla uyumlu olması ve ikili 7 Segment Display’e aktarılmasıdır. Divider ile mod 10 işlemine tabi tuttum ve bölümden geleni soldaki Splitter’a, kalandan geleni sağdaki Splitter’a yönlendirdim.

#### F = ABS (2N-3X+5)

![F = ABS (2N-3X+5)](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/F%20%3D%20ABS%20(2N-3X%2B5).jpg)


ABS’nin içindeki 2N – 3X + 5 işlemini Adder ve Multiplier kullanarak yaptıktan sonra 2N – 3X + 5 sayısını Comperator ile karşılaştırarak sayının negatif mi pozitif mi olduğunu buldum. N-type transistör ile eğer sayı pozitif ise yukarıdaki Splitter’a eğer sayı negatif ise Negator ile 1’s complement değerini alıp sonrasında aşağıdaki Splitter’a yönlendirdim.
 

A	B	C	D	F
				
0	0	0	0	1
				
0	0	0	1	0
				
0	0	1	0	0
				
0	0	1	1	0
				
0	1	0	0	0
				
0	1	0	1	0
				
0	1	1	0	0
				
0	1	1	1	0
				
1	0	0	0	0
				
1	0	0	1	0
				
1	0	1	0	0
				
1	0	1	1	0
				
1	1	0	0	0
				
1	1	0	1	0
				
1	1	1	0	0
				
1	1	1	1	0
				
 


Verilen doğruluk tablosu ABS(2N - 3X + 5) fonksiyonuna aittir. Tabloda fonksiyonun içindeki işlemin sonuncunun negatif olduğu durumları F = 1 olarak varsaydım ve mintermleri buna göre oluşturdum. Pozitif olduğu durumlar için F = 0 kabul ettim.

F = A’B’C’D

Karnaugh Map ile hesaplanan çıkış A’B’C’D olması bize fonskiyonun sonucunun A’B’C’D olduğunu göstermektedir.

Minterms = ∑ (m0)
 
# Örnek Program Çıktıkları

![Örnek Program Çıktıları](https://github.com/ismaildemircann/Logic-Desings-in-Logisim/blob/master/Logisim-MathOperations/152120171029_SayTasLabC_1920BHR_FinalProje/images/%C3%96rnek%20Program%20%C3%87%C4%B1kt%C4%B1klar%C4%B1.png)


