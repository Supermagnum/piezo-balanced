
A small board that uses a LSK389B, for preamplifier and impedance matching of two piezo electric crystals wired in balance.
That should protect against electric noise.
It has balanced input and output.

I hope it does not have any bloopers as I have difficulty with maths!
 
I think it should work on +48 phantom power.

It anyone spots something wrong, please fork and correct.

PCB:
https://aisler.net/p/UJQSALGW

Component side picture:
https://raw.githubusercontent.com/Supermagnum/piezo-balanced/main/piezo-jfet.jpg

Back side picture:
https://github.com/Supermagnum/piezo-balanced/raw/main/piezo-jfet2.jpg

Electronic diagram with component values, it also shows how to wire the crystals::
https://github.com/Supermagnum/piezo-balanced/blob/main/piezo-jfet.pdf

Complete LSK389B datasheet:
https://linearsystems.com/lsdata/datasheets/Copy_201122%20-%20LSK389%20Datasheet%20Rev%20A24%202020%2001%2007.pdf

Digikey does not sell LSK389B in single or dual orders.

But, these does! 
https://store.nacsemi.com/Products/Detail?stock=LIS000000001342

Why: 
The problem with piezo guitar pickups and piezoelectric crystals is that they are not well matched to typical audio inputs.
By their nature they can generate a lot of signal, but they cannot drive a 50 kilohm typical line input. 
The pickup needs to work into a much higher impedance, typically 1 megohm or so.

So what to people do? 
They go and plug a piezoelectric disks output directly into the line input of their recorder, 
typical impedance 50k, or the plug-in-power mic input of their recorder, typical impedance about 7k,
and they start to bitch and moan that this damn thing sounds tinny. 
Which is does ! 

The reason why these devices often sound tinny is because the piezo sensor 
presents its signal through a series capacitance which is small, typically 15nF or less. 
When wired to a normal 50 kilohm line input this forms a high-pass filter, which eliminates the bass.

This circuit board solves that, and amplifies the signal around 30 dB. 
Should also work nice with hydrophones.


