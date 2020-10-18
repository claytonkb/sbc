# Stochastic bitstream computing

Most of the elements are based on [this PDF excerpt](http://pages.cpsc.ucalgary.ca/~gaines/reports/COMP/SCS69/SCS69.pdf)
titled "Stochastic Computing Systems" by B. R. Gaines. There is a broader field
of stochastic computing than that described by Gaines, and so I have renamed
his approach "stochastic bitstream computing." There is also a form of computing
termed "bitstream computing" which does not necessarily utilize stochasticity.

This repository contains [logisim](http://www.cburch.com/logisim/) files.

![Logisim](img/logisim_screenshot.png)

You can run logisim on Windows or Linux systems by installing a Java runtime.
Download and run the Logisim installer for your OS and everything should just
work. Unfortunately, Logisim is no longer being maintained so if you have an
issue, there may be no solution. In the future, I plan to port to Verilog so
these elements can be built with standard EDA tools.

Note that if you want to copy objects from one Logisim file to another, you
need to use the "File->Open" menu from within Logisim. If you double-click the
.circ files from your file explorer, you will not be able to copy and paste
objects between the files.

Gaines describes three stochastic representations. Most of the SBC elements
I've built so far operate on representation I. But I plan to implement some
elements based on representation III (this will facilitate differentials).
Representation II is of limited interest. By and large, the counter elements
are 8-bit (saturating). I am also building some 16-bit elements for handling
higher resolution.

I'll try to add a description for each Logisim file as I publish it.

* 01_basics.circ

This file introduces the inputs and outputs for the SBC circuits we will build.
It introduces the VAR element which can be used to drive an 8-bit value. To
increase the output value of the VAR element, click the upper button. To
decrease it, click the lower button. It introduces the DISPH element which can
drive two 7-segment displays showing an 8-bit hex value. It introduces the
DISP11 element which can drive 7-segment displays and an LED-matrix showing the
Representation III value of an 8-bit counter input. It introduces the DISP01
element which is just like the DISP11 element except that it ranges from 0 to
1. It introduces the GRAPH element which can visually track the level of an
8-bit value over time. Note that the graphical elements only have 16 LEDs so
they are only using the upper hex digit of the 8-bit value and throwing away
the lower hex digits. Practically, this means you will click VAR four times in
one direction before you see a visual change on the LEDs.

The next circuit will introduce a few basic elements that are used in a
stochastic bitstream circuit. Stay tuned...


