# PLL-design-using-sky130
This begins with basic PLL concepts and then proceeds to cover all Integrated Circuit (IC) design steps (circuit design, simulation, layout, parasitics extraction, post layout simulation).  It concludes with making a tapeout of the PLL circuit using magic.

# Table of Contents
- [Basic PLL Theory](#basic-pll-theory)
- [Open Source Tools Used](#open-source-tools-used)
- [Acknowlegements](#Acknowledgements)
- [Contact](#Contact)

# Basic PLL Theory

<b>Basic components of a PLL</b> (<i>Image courtesy wikipedia</i>)
<p><a href="https://commons.wikimedia.org/wiki/File:Phase_locked_loop.svg#/media/File:Phase_locked_loop.svg"><img height="50%" width="50%" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Phase_locked_loop.svg/1200px-Phase_locked_loop.svg.png" alt="Phase locked loop.svg"></a>
 

Why is a Phase-Locked Loop Clock Multiplier IC needed?
To get a precise clock signal without frequency or phase noise.

Which are the circuits that are a minimum requirement for making a PLL?
What is meant by spectral purity of output??

# Open Source Tools Used

* [ngspice](http://ngspice.sourceforge.net/download.html) (simulation) <br>
* [magic](http://opencircuitdesign.com/magic/) (layout design) <br>
* [Google/SKywater 130nm pdks](https://github.com/google/skywater-pdk) (process design kit for usage with SkyWater Technology Foundry's 130nm node)

# Acknowledgements

* I thank Mr. Kunal Ghosh, co-founder [VSD](https://www.vlsisystemdesign.com/) and Lakshmi Sathidevi for their hard work in putting this excellent workshop together.
* I thank [Google](https://github.com/google), [Skywater](https://www.skywatertechnology.com/), [ngspice](http://ngspice.sourceforge.net/) and [magic](http://opencircuitdesign.com/magic/) for providing the open source tools that make it possible for a project like this.

# Contact

* Greg Phillips (Author) - greg@thinkitdata.com
* Lakshmi S, MS ECE - lakshmi.sathi96@gmail.com
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
