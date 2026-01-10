# Phanny – 52 Key Split

This repo is going to show the process of me designing, printing, working in KiCad, Fusion360, and overall building this split keyboard. I plan to explain the issues I didn’t know were issues until it was too late, and show how I managed to overcome some of the problems in the initial design.

---

## The Design

This board would not have come to life if not for Aran from PCBWay. He reached out to me to see if I had any interest in working on another project, this time utilizing their PCB manufacturing service. I enjoyed the work they did on a case I designed, and I love trying new things, so I took him up on his offer and got to work.

I knew the basics of what I wanted: split, ortho, staggered column, splay, and a num-row. I decided to get the layout dialed in using the well-known Keyboard Layout Editor. I started playing around with different layouts and testing different splay angles. Then I adjusted how much column stagger I wanted. My aim was to make something comfortable when reaching for any key. Another issue I knew I wanted to overcome from prior boards was the thumb cluster. Thanks to printing several test plates, I think I landed on something very comfortable for long typing sessions while still leaving enough keys that I don’t feel forced into multiple layers.

---

## KiCad

After finalizing my design, I moved into new territory: KiCad, a software program for designing circuit boards, schematics, and PCBs. I spent longer than expected trying to learn on the fly like I did with Fusion360, and that landed me with nothing but wasted time. I turned to YouTube and watched the tutorial videos from Modern Hobbyist [Modern Hobbyist – Designing a Custom Keyboard PCB FROM SCRATCH](https://www.youtube.com/watch?v=u13yRbBiRYM)

 and Joe Scotto [How to Design Mechanical Keyboard PCBs with KiCad](https://www.youtube.com/watch?v=8WXpGTIbxlQ)
. Combined, their videos give enough of a breakdown that anyone could design a PCB, and both creators offer downloadable packages containing parts and footprints.

---

## Schematic

The schematic editor was the easy part. It’s like designing a matrix—because it *is* designing the matrix—but instead of copper wire, it's pixels on a screen. This is where my lack of knowledge showed. I didn’t realize I could just copy the left, paste, then flip. So I ended up doubling my work.

Once I fixed all my errors, I clicked the PCB Editor and hit “Update PCB from Schematic.” Suddenly I had 52 MX footprints, 52 1N4148 diode footprints, and 2 nice!nano footprints neatly arranged. Thankfully, Modern Hobbyist’s video showed plug-ins that make placing switches based on Keyboard Layout Editor files much easier.

---

## PCB Routing

Routing traces is basically a game of connect-the-dots, except the final picture is *not* a bear. This was challenging because you have to avoid blocking access to any other rows or columns. Pin by pin I worked through it until everything was connected and looking decent (to someone who knows nothing about circuitry).

Then came drawing the board outline. Adding “Edge Cuts” was another problem I discovered later. I rushed the design, eyeballed the right PCB instead of mirroring properly, and got bit in the ass designing the case.

---

## Submitting to PCBWay

After fixing all visible errors, I sent the Gerber files to PCBWay using their plug-in. The system takes you to their site with the technical info pre-filled. You choose solder, solder mask color, silkscreen, and hit “Add to cart.”

Someone from PCBWay reviews your work and points out issues. My reviewer noticed I accidentally set huge mounting holes (2mm *radius*, not diameter) and fixed it. They also recommended thinning the break seam so both halves would snap cleanly apart. I happily let the experts help.

One week later, I had five pristine PCBs. Holding a board you designed—and having it look good—is a feeling I now crave. I went with flat black PCBs with white accents. Safe choice, great look.

---

## Case Design

I exported my PCB from KiCad into Fusion360. I included all components so I could design around them with confidence (because I had already done enough guessing elsewhere). A YouTuber I watch, Stuff Made Here, says something like:

> “Don’t design around a mistake instead of fixing it. It will cause more problems later.”

I ignored that advice from someone who builds robots. I went through about twelve different case iterations until landing on the one I’m sharing here.

---

## Assembly & Soldering

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

Thanks to help on previous builds, I was pointed to the **ZMK Shield Wizard**, and it changed everything. It walks you step-by-step through generating your firmware. In about 20 minutes you can go from a pile of solder, copper, and silicon to a fully functional wireless keyboard.

---

## Completion

Next, I screwed the plate and PCB into the case and—viola—Phanny was born.










# ZMK Configuration for Phanny

*Generated by Shield Wizard for ZMK*

Download compiled firmware from the Actions tab. <https://zmk.dev/docs/user-setup#installing-the-firmware>

Trigger the initial build by going to the **Actions** tab, select **Build ZMK firmware** workflow on the left, and clicking the **Run workflow** button.
All subsequent builds will be triggered automatically whenever a change is pushed to the repository.

Edit your keymap <https://zmk.dev/docs/keymaps>, or use <https://nickcoutsos.github.io/keymap-editor/> to edit it visually.
User keymap is located at [`config/phanny.keymap`](config/phanny.keymap).

-----

<details>
<summary>
debug information
</summary>

For the purpose of debugging Shield Wizard for ZMK in case of broken configuration, here is the data used to generate this configuration:

```json
{"info":{"name":"Phanny","shield":"phanny","controller":"nice_nano_v2","wiring":"matrix_diode","dongle":false},"layout":[{"partOf":0,"row":0,"column":1,"width":1,"height":1,"x":1,"y":0.37,"r":0,"rx":0,"ry":0},{"partOf":0,"row":0,"column":2,"width":1,"height":1,"x":2,"y":0.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":0,"column":3,"width":1,"height":1,"x":3,"y":0,"r":0,"rx":0,"ry":0},{"partOf":0,"row":0,"column":4,"width":1,"height":1,"x":4,"y":0.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":0,"column":5,"width":1,"height":1,"x":5,"y":0.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":0,"column":8,"width":1,"height":1,"x":10.5,"y":0.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":0,"column":9,"width":1,"height":1,"x":11.5,"y":0.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":0,"column":10,"width":1,"height":1,"x":12.5,"y":0,"r":0,"rx":0,"ry":0},{"partOf":1,"row":0,"column":11,"width":1,"height":1,"x":13.5,"y":0.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":0,"column":12,"width":1,"height":1,"x":14.5,"y":0.37,"r":0,"rx":0,"ry":0},{"partOf":0,"row":1,"column":0,"width":1,"height":1,"x":0,"y":1.5,"r":0,"rx":0,"ry":0},{"partOf":0,"row":1,"column":1,"width":1,"height":1,"x":1,"y":1.37,"r":0,"rx":0,"ry":0},{"partOf":0,"row":1,"column":2,"width":1,"height":1,"x":2,"y":1.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":1,"column":3,"width":1,"height":1,"x":3,"y":1,"r":0,"rx":0,"ry":0},{"partOf":0,"row":1,"column":4,"width":1,"height":1,"x":4,"y":1.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":1,"column":5,"width":1,"height":1,"x":5,"y":1.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":1,"column":8,"width":1,"height":1,"x":10.5,"y":1.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":1,"column":9,"width":1,"height":1,"x":11.5,"y":1.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":1,"column":10,"width":1,"height":1,"x":12.5,"y":1,"r":0,"rx":0,"ry":0},{"partOf":1,"row":1,"column":11,"width":1,"height":1,"x":13.5,"y":1.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":1,"column":12,"width":1,"height":1,"x":14.5,"y":1.37,"r":0,"rx":0,"ry":0},{"partOf":1,"row":1,"column":13,"width":1,"height":1,"x":15.5,"y":1.5,"r":0,"rx":0,"ry":0},{"partOf":0,"row":2,"column":0,"width":1,"height":1,"x":0,"y":2.5,"r":0,"rx":0,"ry":0},{"partOf":0,"row":2,"column":1,"width":1,"height":1,"x":1,"y":2.37,"r":0,"rx":0,"ry":0},{"partOf":0,"row":2,"column":2,"width":1,"height":1,"x":2,"y":2.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":2,"column":3,"width":1,"height":1,"x":3,"y":2,"r":0,"rx":0,"ry":0},{"partOf":0,"row":2,"column":4,"width":1,"height":1,"x":4,"y":2.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":2,"column":5,"width":1,"height":1,"x":5,"y":2.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":2,"column":8,"width":1,"height":1,"x":10.5,"y":2.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":2,"column":9,"width":1,"height":1,"x":11.5,"y":2.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":2,"column":10,"width":1,"height":1,"x":12.5,"y":2,"r":0,"rx":0,"ry":0},{"partOf":1,"row":2,"column":11,"width":1,"height":1,"x":13.5,"y":2.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":2,"column":12,"width":1,"height":1,"x":14.5,"y":2.37,"r":0,"rx":0,"ry":0},{"partOf":1,"row":2,"column":13,"width":1,"height":1,"x":15.5,"y":2.5,"r":0,"rx":0,"ry":0},{"partOf":0,"row":3,"column":0,"width":1,"height":1,"x":0,"y":3.5,"r":0,"rx":0,"ry":0},{"partOf":0,"row":3,"column":1,"width":1,"height":1,"x":1,"y":3.37,"r":0,"rx":0,"ry":0},{"partOf":0,"row":3,"column":2,"width":1,"height":1,"x":2,"y":3.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":3,"column":3,"width":1,"height":1,"x":3,"y":3,"r":0,"rx":0,"ry":0},{"partOf":0,"row":3,"column":4,"width":1,"height":1,"x":4,"y":3.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":3,"column":5,"width":1,"height":1,"x":5,"y":3.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":3,"column":8,"width":1,"height":1,"x":10.5,"y":3.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":3,"column":9,"width":1,"height":1,"x":11.5,"y":3.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":3,"column":10,"width":1,"height":1,"x":12.5,"y":3,"r":0,"rx":0,"ry":0},{"partOf":1,"row":3,"column":11,"width":1,"height":1,"x":13.5,"y":3.12,"r":0,"rx":0,"ry":0},{"partOf":1,"row":3,"column":12,"width":1,"height":1,"x":14.5,"y":3.37,"r":0,"rx":0,"ry":0},{"partOf":1,"row":3,"column":13,"width":1,"height":1,"x":15.5,"y":3.5,"r":0,"rx":0,"ry":0},{"partOf":0,"row":4,"column":3,"width":1,"height":1,"x":2.5,"y":4.12,"r":0,"rx":0,"ry":0},{"partOf":0,"row":4,"column":4,"width":1,"height":1,"x":3.5,"y":4.15,"r":0,"rx":0,"ry":0},{"partOf":0,"row":4,"column":5,"width":1,"height":1,"x":4.5,"y":4.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":4,"column":8,"width":1,"height":1,"x":11,"y":4.25,"r":0,"rx":0,"ry":0},{"partOf":1,"row":4,"column":9,"width":1,"height":1,"x":12,"y":4.15,"r":0,"rx":0,"ry":0},{"partOf":1,"row":4,"column":10,"width":1,"height":1,"x":13,"y":4.15,"r":0,"rx":0,"ry":0}],"pinouts":[{"d4":"input","d3":"input","d2":"input","d0":"input","d1":"input","d9":"output","d8":"output","d7":"output","d6":"output","d5":"output","d10":"output"},{"d1":"input","d0":"input","d2":"input","d3":"input","d4":"input","d5":"output","d6":"output","d7":"output","d8":"output","d9":"output","d10":"output"}],"wiring":[{"input":"d4","output":"d8"},{"input":"d4","output":"d7"},{"input":"d4","output":"d6"},{"input":"d4","output":"d5"},{"input":"d4","output":"d10"},{"input":"d4","output":"d9"},{"input":"d4","output":"d8"},{"input":"d4","output":"d7"},{"input":"d4","output":"d6"},{"input":"d4","output":"d5"},{"input":"d3","output":"d9"},{"input":"d3","output":"d8"},{"input":"d3","output":"d7"},{"input":"d3","output":"d6"},{"input":"d3","output":"d5"},{"input":"d3","output":"d10"},{"input":"d3","output":"d9"},{"input":"d3","output":"d8"},{"input":"d3","output":"d7"},{"input":"d3","output":"d6"},{"input":"d3","output":"d5"},{"input":"d3","output":"d10"},{"input":"d2","output":"d9"},{"input":"d2","output":"d8"},{"input":"d2","output":"d7"},{"input":"d2","output":"d6"},{"input":"d2","output":"d5"},{"input":"d2","output":"d10"},{"input":"d2","output":"d9"},{"input":"d2","output":"d8"},{"input":"d2","output":"d7"},{"input":"d2","output":"d6"},{"input":"d2","output":"d5"},{"input":"d2","output":"d10"},{"input":"d0","output":"d9"},{"input":"d0","output":"d8"},{"input":"d0","output":"d7"},{"input":"d0","output":"d6"},{"input":"d0","output":"d5"},{"input":"d0","output":"d10"},{"input":"d0","output":"d9"},{"input":"d0","output":"d8"},{"input":"d0","output":"d7"},{"input":"d0","output":"d6"},{"input":"d0","output":"d5"},{"input":"d0","output":"d10"},{"input":"d1","output":"d7"},{"input":"d1","output":"d6"},{"input":"d1","output":"d5"},{"input":"d1","output":"d8"},{"input":"d1","output":"d7"},{"input":"d1","output":"d6"}]}
```

</details>
