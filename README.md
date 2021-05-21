
A small board that uses a LSK389B, for preamplifier and impedance matching of two piezo electric crystals wired in balance.
That should protect against electric noise.
It has balanced input and output.
I hope it does not have any bloopers as I have difficulty with maths, 
I think it should work on +48 phantom power.

It anyone spots something wrong, please fork and correct.

PCB:
https://aisler.net/p/JXZFPNKS

Electronic diagram with component values:
https://github.com/Supermagnum/piezo-balanced/blob/main/piezo-jfet.pdf

How to wire the crystals:
https://github.com/Supermagnum/piezo-balanced/blob/main/Balanced-Microphone-Correct-polarisation-correct-colors.jpg

Why: 
The problem with piezo guitar pickups and contact mics is that they are not well matched to typical audio inputs.
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



