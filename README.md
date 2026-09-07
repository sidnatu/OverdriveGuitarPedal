# OverdriveGuitarPedal
Images and process of my overdrive guitar pedal.


# Summary
I wanted to combine one of my hobbies with what I'm studying, so naturally a guitar pedal is a great gateway into design. This board was inspired by the Boss OD-1 pedal. The circuit design was all done in LTSpice with calculations to support the gains and behaviour we see in the circuit. The behaviour we expect in a overdrive pedal is a boost of the input signal with soft clipping to ensure a warm, yet powerful tone. The reason why everything is through-hole rather than surface mount is **a.** saves me money from buying more parts and **b.** soldering is a lot easier.

Attached is a clip of my good friend Jake playing a sample from TOOL's Forty Six & 2.

https://github.com/user-attachments/assets/3524955c-d7c1-4307-9d5c-1cb33a89aa26

 # Lessons Learned
One thing I had to learn for this project was creating my own footprints. The connectors I used (ACJS-MV-5) had poor documentation, so I utilized the engineering drawings to properly place the pins. The documentation provided on the Digikey store was simply a brochure for the rest of their products, so I did a little more digging and found the actual layout recommended by the company and made the footprints myself. 

Another thing I learned was designing for user interface. The 3 potentiometers are used to control gain, tone and volume and for majority of pedals they're in a easy to access location. As I worked on the layout I was constantly reminding myself about things like "Will I be able to change the pot easily?" or "How easy would this be for me to solder/rework?". Based off of that thinking pattern, I opted to put the poteniometers near the edge of the board, but this did introduce some routing issues. Luckily everything here is very low frequency, so I didn't have to worry about impedance matching.

I also learned how to import custom components into LTSpice. Almost all guitar pedals use potentiometers to control various characteristics, so they're a fundamental building block for these pedals. LTSpice didn't have a useable potentiometer symbol so I imported one in for my design. This was done by building a pot subcircuit and adding it to my SPICE library. Doing this allowed me to properly check if the pots were working as expected. For example, the gain pot should follow the formula: $1 + \frac{R2}{R1}$, and by adding the pot behaviour, I was able to validate in simulation that it indeed followed this characteristic.
