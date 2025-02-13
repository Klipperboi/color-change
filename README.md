# ADVANCED (SAME LAYER) COLOR CHANGE

No matter how good your printer is tuned, the 1st layer, with the bed texture will always look better than the top one. 
That being said, if you want to make nice things that have color changes, you should take advantage of that thing, and organise the color changes to be made on the 1st layer, rather than having them made the simple way, at the top, with layer changes. 

## CORRECT GCODE FOR COLOR CHANGING

Before you start, you should make sure that you have the adequate color change gcode in _Printer settings > Machine G-code > Change filament G-code_.

![alt text](https://github.com/Klipperboi/color-change/blob/main/assets/m600.png)

If you use Marlin, just put M600 there; if you use klipper, you will have to make a macro that does the same action (pauses the print, parks the toolhead, retracts, allows you to insert the new filament, extrude, and resume the print), but more on that [here](https://github.com/Klipperboi/klipper_se/blob/main/macro.cfg).

## USE CASES

There are 3 main use cases that we'll cover in this tutorial:
- a custom model, made in Fusion360
- using SGVs
- models that were made for layer change color change (on the top)

## PREPARING

You need to import your model into OrcaSlicer. For the sake of this tutorial, I'll be using [this model](https://www.printables.com/model/914446-rammstein-keychain). Add at least 2 colors/filaments from the *Filament* section, so you can color change properly, in this case black and white.

![alt text](https://github.com/Klipperboi/color-change/blob/main/assets/filament.png)

### Custom made models

If you want to make something with a color change, avoid extruding the text on top to change the color.

![alt text](https://github.com/Klipperboi/color-change/blob/main/assets/f1.png)

Instead, mirror the sketch, and cut in the body the amount you want the color change to be done. I recommend working with mutliples of 0.2mm (or whatever layer height you are using), and do at least 3-4 layers for the accent color, especially if you want to switch from a "weak" to a "strong" color (ie. from white to black).

![alt text](https://github.com/Klipperboi/color-change/blob/main/assets/f2.png)

Now extrude the sketch again, the same amount.

![alt text](https://github.com/Klipperboi/color-change/blob/main/assets/f3.png)

If you want to send the file straight to Orca, as a .3mf file, make sure to make each body a different color, from the _Appearance_ menu.
