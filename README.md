
A small board that uses a LSK389B dual N channel Jfet,and a LSK170B N channel Jfet for preamplifier and impedance matching of two piezo electric crystals wired in balance.
Those J-FET's are ultra low noise components.
Please use 0,5 W metal film resistors with 1% tolerance or better and audio quality capacitors.
C0G (NP0) or X7R capacitors is very good.


The circuit may benefit from a Zobel network, that is a 680 pF capacitor and a 150 ohms resistor in series between pin 2 and 3 on the output or the input connector. It should avoid high frequency oscillation in a long cable.

It has balanced input and output.
That should minimize electric noise picked up from the environment.
One can read more about that here:
https://en.m.wikipedia.org/wiki/Balanced_audio

It's for +48 volt phantom power.
https://en.m.wikipedia.org/wiki/Phantom_power

+48 volt phantom power supply with mono headphone jack, runs on 9V battery:
https://github.com/Supermagnum/48power

PCB:
https://aisler.net/p/UJQSALGW
Note: Aisler does not carry LSK170B in  TO-92 3L or LSK389B in TO-71-6 .

PCB dimentions:
https://github.com/Supermagnum/piezo-balanced/blob/main/dimentions.png

Component side picture:
https://raw.githubusercontent.com/Supermagnum/piezo-balanced/main/piezo-jfet.jpg

Back side picture:
https://github.com/Supermagnum/piezo-balanced/raw/main/piezo-jfet2.jpg

Electronic diagram with component values, it also shows how to wire the crystals:
https://github.com/Supermagnum/piezo-balanced/blob/main/piezo-jfet.pdf

Gerber files for production of the PCB:
https://github.com/Supermagnum/piezo-balanced/tree/main/gerbers

Simulation in Ltspice:

Ltspice setup:
https://github.com/Supermagnum/piezo-balanced/blob/main/Ltspice-setup.png

Frequency response:
https://github.com/Supermagnum/piezo-balanced/blob/main/response.png

LSK170B datasheet:
https://www.linearsystems.com/lsdata/datasheets/201110%20-LSK170%20Rev%20A17%20dated%202017%2008%2028.pdf

Complete LSK389B datasheet:
https://linearsystems.com/lsdata/datasheets/Copy_201122%20-%20LSK389%20Datasheet%20Rev%20A24%202020%2001%2007.pdf

Digikey does not sell LSK389B or LSK170B in single or dual orders.
The 40 ohm resistor is also not sold by digikey .
Alternatively two 80 ohm resistors in parallel can be used.
That gives 40 ohm.

But, these does have LSK389B !
https://store.nacsemi.com/Products/Detail?stock=LIS000000001342

LSK170B:
https://store.nacsemi.com/products/detail?part=LSK170B-TO-92&stock=LIS000000000640

Picture of a piezoelectric disc, with red wire for positive polarity and black for negative:
https://github.com/Supermagnum/piezo-balanced/blob/main/Piezo-element-6.jpg

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

This circuit board solves that, and amplifies the signal around 15~30 dB. 
How many dB it amplifies is dependent on the impedance on the recording equipment.

I am getting 24 dB with 10K ohm impedance of the recorder ( simulated ).

If R4, R8 and R12 is removed,and jumpers installed in their place, the gain is 38 dB with 10K impedance.
You get more with higher impedance, expect 40 dB with 40K impedance of the recorders input.

It's fairly easy and straight forward to solder the components to the circuit board,
a nice pointy soldering iron, solder, a magnifying glass, and a ohm or multimeter is all that is needed.
Of course one needs a suitable metal box, and the circuit boards components
must not come in contact with the metal box. 
That will cause short circuit, so it's best mounted on stand offs.
Also, use the magnifying glass to check that no one of the soldering pads has been bridged.

It can be used for a reverb plate, listening to the insides of a engine,recording the sound of vibrating things.
You will need two piezoelectric disks for that, mounted in a metal box. 
Non electric conductive super glue is useable for that. Just glue them to a flat surface.
The piezoelectric disks should be electrically insulated from the metal box.

Mechanics may even use it to discover trouble with bearings or other mechanisms not easily opened,
but it will need a dedicated +48 volts phantom power supply with headphone jack for that specific usage. 

Of course one can use a recorder like a tascam dr40x, as long as it can supply +48 volt phantom power, and has a headphone jack for monitoring.

They usually have a 3 pin XLR plug.
Those are wired up like this:
https://github.com/Supermagnum/piezo-balanced/blob/main/XLR%2BConnector%2BPinout%2BDiagram%2BRear%2BPin%2B2%2BHot%2Bv2%2Bgreen__01.jpg

NOTE:  
The XLR 3 pin plug has a solder lug for the shield for a reason.
It is my opinion that a shielded cable with 3 conductors inside is the best.
Suggested cable: Digi-Key Part Number: 30-00910-5-ND

A good set of headphones or ear protection with built in speakers will keep out unwanted sounds or noise.

Should also work nice with hydrophones.
PZT-5H tubes is best for that.

For hydrophone usage:
The two piezoelectric tubes elements needs to be encapsulated in Ecopoxy Flowcast epoxy, with as little thickness to the outside of the piezoelectric tubes as possible. 
Commercial ones uses kerosene oil, so olive oil or sunflower oil is a great alternative as it will not pollute the environment if any leaks occurs.
A streamlined bulb should be nice for that. The more streamlined, the less water flow noise. 

Some interesting ideas can be found in:
https://github.com/Supermagnum/piezo-balanced/blob/main/Barlow-et-al-2008-HydrophoneConstruction_TM-417.pdf
Note: Ecopoxy Flowcast does not need any vacuum, just a mold and a way to hold the piezoelectric tubes centered.
It's also safer to work with.
Of course two piezoelectric disks inside something waterproof that can handle the water pressure is also useable.

Some methods of mounting a piezoelectric disk can be found here: https://locusonus.org/wiki/index.php?page=Hydrophone.en

Made with:
http://www.kicad.org/

KiCad uses an integrated environment for all of the stages of the design process: Schematic capture, PCB layout, Gerber file generation/visualization, and library editing.

KiCad is a cross-platform program, and of curse free!


The PCB board is tested and works.
