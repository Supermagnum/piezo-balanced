
A small board that uses a LSK389B dual N channel Jfet, for preamplifier and impedance matching of two piezo electric crystals wired in balance.
That should minimize electric noise.
It has balanced input and output.
One can read more about that here:
https://en.m.wikipedia.org/wiki/Balanced_audio

I hope it does not have any bloopers on the resistor values as I have difficulty with maths!
 
It's for +48 volt phantom power.
https://en.m.wikipedia.org/wiki/Phantom_power

It anyone spots something wrong, please fork and correct.

PCB:
https://aisler.net/p/UJQSALGW
Note: Aisler does not carry LSK170B in  TO-92 3L or LSK389B in TO-71-6 .

Component side picture:
https://raw.githubusercontent.com/Supermagnum/piezo-balanced/main/piezo-jfet.jpg

Back side picture:
https://github.com/Supermagnum/piezo-balanced/raw/main/piezo-jfet2.jpg

Electronic diagram with component values, it also shows how to wire the crystals:
https://github.com/Supermagnum/piezo-balanced/blob/main/piezo-jfet.pdf

Frequency response:
https://github.com/Supermagnum/piezo-balanced/blob/main/response.png


LSK170B datasheet:
https://www.linearsystems.com/lsdata/datasheets/201110%20-LSK170%20Rev%20A17%20dated%202017%2008%2028.pdf

Complete LSK389B datasheet:
https://linearsystems.com/lsdata/datasheets/Copy_201122%20-%20LSK389%20Datasheet%20Rev%20A24%202020%2001%2007.pdf

Digikey does not sell LSK389B in single or dual orders.

But, these does! 
https://store.nacsemi.com/Products/Detail?stock=LIS000000001342

LSK170B:
https://store.nacsemi.com/products/detail?part=LSK170B-TO-92&stock=LIS000000000640

Why: 
The problem with piezo guitar pickups and piezoelectric crystals is that they are not well matched to typical audio inputs.
By their nature they can generate a lot of signal, but they cannot drive a 50 kilohm typical line input. 
The pickup needs to work into a much higher impedance, typically 1 megohm or so.

So what to people do? 
They go and plug a piezoelectric disks output directly into the line input of their recorder, 
typical impedance 50k, or the plug-in-power mic input of their recorder, typical impedance about 7k,
and they start to bitch and moan that this damn thing sounds tinny. 
Which is does ! But they don't understand why!

The reason why these devices often sound tinny is because the piezo sensor 
presents its signal through a series capacitance which is small, typically 15nF or less. 
When wired to a normal 50 kilohm line input this forms a high-pass filter, which eliminates the bass.

This circuit board solves that, and amplifies the signal around 30 dB. 
Should also work nice with hydrophones.
PZT-5H is best for that.


In case of a hydrophone it's possible to have the hydrophone attached with a long cable and the amplifier/buffer circuit close to the recording equipment. 

The two piezoelectric elements needs to be encapsulated in Ecopoxy Flowcast epoxy, with as little thickness to the  piezoelectric tubes as possible. 
A streamlined bulb should be nice for that. 



