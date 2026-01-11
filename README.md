# Phanny – A 52 Key Wireless Split Keyboard 

![Phanny](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Top%20Complete.jpg)


This repo is going to show the process of me designing, printing, working in KiCad, Fusion360, and overall building this split keyboard. I plan to explain the issues I didn’t know were issues until it was too late, and show how I managed to overcome some of the problems in the initial design.

---

## Bill of Materials (Parts Used)

* **[52x Akko Lavender Purple MX switches](https://a.co/d/eYtUOfr)**
* **[52x Bojack 1N4148 diodes](https://a.co/d/55k6egk)**
* **[2x nice!nano compatible microcontrollers (clones)](https://a.co/d/dAoMDN4)**
* **[2x 250 mAh Li-Po batteries](https://a.co/d/eQfxd4M)**
* **[2x latching power switch](https://a.co/d/ayTqJVD)**
* **[YMDK XDA profile keycap set](https://a.co/d/iarCa5a)**
* **[M2 screws and Heat Set Inserts for assembly](https://a.co/d/6kXW8W8)**
* **[Socket headers for MCU](https://a.co/d/7FIVP1g)**
* **[Small gauge wire for BAT+ / BAT-](https://a.co/d/98wqhhf)**
* **Hand-designed Phanny PCBs** (manufactured by PCBWay)
* **3D printed PLA+ case** (plate & base)

## The Design

![KLE Layout](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/KLE.jpg)
**[KLE RAW Data](https://github.com/zackattack2130/Phanny/blob/e4addd5963249170c31529c75ea8b253667b637a/Images/KLE%20Code%20Master%20Only.txt)**



This board would not have come to life if not for Aran from [PCBWay](https://www.pcbway.com/)
. He reached out to me to see if I had any interest in working on another project, this time utilizing their PCB manufacturing service. I enjoyed the work they did on a case I designed, and I love trying new things, so I took him up on his offer and got to work.

I knew the basics of what I wanted: split, ortho, staggered column, splay, and a num-row. I decided to get the layout dialed in using the well-known [Keyboard Layout Editor](https://www.keyboard-layout-editor.com/#/) I started playing around with different layouts and testing different splay angles. Then I adjusted how much column stagger I wanted. My aim was to make something comfortable when reaching for any key. Another issue I knew I wanted to overcome from prior boards was the thumb cluster. Thanks to printing several test plates, I think I landed on something very comfortable for long typing sessions while still leaving enough keys that I don’t feel forced into multiple layers.

![Fusion Plate](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20Plate.jpg)

---

## KiCad

After finalizing my design, I moved into new territory: KiCad, a software program for designing circuit boards, schematics, and PCBs. I spent longer than expected trying to learn on the fly like I did with Fusion360, and that landed me with nothing but wasted time. I turned to YouTube and watched the tutorial videos from Modern Hobbyist [Modern Hobbyist – Designing a Custom Keyboard PCB FROM SCRATCH](https://www.youtube.com/watch?v=u13yRbBiRYM) and Joe Scotto [How to Design Mechanical Keyboard PCBs with KiCad](https://www.youtube.com/watch?v=8WXpGTIbxlQ)
. Combined, their videos give enough of a breakdown that anyone could design a PCB, and both creators offer downloadable packages containing parts and footprints.

---

## Schematic

![Phanny Schematic](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Schematic.jpg)


The schematic editor was the easy part. It’s like designing a matrix—because it *is* designing the matrix—but instead of copper wire, it's pixels on a screen. This is where my lack of knowledge showed. I didn’t realize I could just copy the left, paste, then flip. So I ended up doubling my work.

Once I fixed all my errors, I clicked the PCB Editor and hit “Update PCB from Schematic.” Suddenly I had 52 MX footprints, 52 1N4148 diode footprints, and 2 nice!nano footprints neatly arranged. Thankfully, Modern Hobbyist’s video showed plug-ins that make placing switches based on Keyboard Layout Editor files much easier.

---

## PCB Routing

![PCB Editor](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/PCB%20Editor.jpg)


Routing traces is basically a game of connect-the-dots, except the final picture is *not* a bear. This was challenging because you have to avoid blocking access to any other rows or columns. Pin by pin I worked through it until everything was connected and looking decent (to someone who knows nothing about circuitry).

Then came drawing the board outline. Adding “Edge Cuts” was another problem I discovered later. I rushed the design, eyeballed the right PCB instead of mirroring properly, and got bit in the ass designing the case.

---

## Submitting to PCBWay

![KiCad Plug-ins](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Plug-ins.jpg)

After fixing all visible errors, I sent the Gerber files to PCBWay using their plug-in. The system takes you to their site with the technical info pre-filled. You choose solder, solder mask color, silkscreen, and hit “Add to cart.”    

Someone from PCBWay reviews your work and points out issues. My reviewer noticed I accidentally set huge mounting holes (2mm *radius*, not diameter) and fixed it. They also recommended thinning the break seam so both halves would snap cleanly apart. I happily let the experts help.

One week later, I had five pristine PCBs. Holding a board you designed—and having it look good—is a feeling I now crave. I went with flat black PCBs with white accents. Safe choice, great look.

![Packaged PCBs](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Packaged%20PCBs.jpg)


---

## Case Design

I exported my PCB from KiCad into Fusion360. I included all components so I could design around them with confidence (because I had already done enough guessing elsewhere).

![Fusion PCB View](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20PCB%20All%20Top.jpg)
![Fusion PCB Bottom View](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20PCB%20All%20Bottom.jpg)

A YouTuber I watch, Stuff Made Here, says something like:
“Don’t design around a mistake instead of fixing it. It will cause more problems later.”
I ignored that advice from someone who builds robots, the proceded to go through about twelve different case iterations until landing on the one I’m sharing here.

![Fusion Case Top](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20Case%20Top.jpg)
![Fusion Base](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20Base.jpg)
![Fusion Mounting](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20Mounting.jpg)
![Fusion Leg Standoff](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Fusion%20Leg%20Standoff.jpg)

---

## Assembly & Soldering

![Soldering PCBs](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Soldering.jpg)
![Diode Soldered](https://raw.githubusercontent.com/zackattack2130/Phanny/main/Images/Diode%20Soldered.jpg)



Time to solder and hope I correctly referenced the schematic.

Order of operations:

1. Diodes (through-hole, top side)
2. MCU socket headers
3. Battery wires to BAT+ and BAT-
   **Design flaw**: I forgot a dedicated power connector
4. Latching switch to battery and pads
   **IMPORTANT**: Positive to positive, negative to negative
   Best case: you fry an MCU
   Worst case: angry lithium fire rock
5. Switches

Then for the first time, I plugged in *one half* of the keyboard.

---

## Firmware

Thanks to help on previous builds, I was pointed to the **[Shield Wizard for ZMK](https://shield-wizard.genteure.workers.dev/)**, and it changed everything. It walks you step-by-step through generating your firmware. In about 20 minutes you can go from a pile of solder, copper, and silicon to a fully functional wireless keyboard. **Then you have to edit your keymap.** It will be in alphebetical order when the firmware is built. This is easy if you use **[ZMK Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)**

---

## Completion

Next, I screwed the plate and PCB into the case and—viola—Phanny was born.
