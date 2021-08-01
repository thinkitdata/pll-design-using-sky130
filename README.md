<a href ="https://www.vlsisystemdesign.com/pll-design-using-sky130/"><img src =https://www.vlsisystemdesign.com/wp-content/uploads/2021/07/PLL-Workshop-Banner_efabless.png></a>
# PLL-design-using-sky130
This repository will show how to take a basic PLL circuit through all Integrated Circuit (IC) design steps (circuit design, simulation, layout, parasitics extraction and post layout simulation) up thru making a tapeout of the PLL circuit using all open source tools.

# Table of Contents
- [Basic PLL Theory](#basic-pll-theory)
- [Open Source Tools Used](#open-source-tools-used)
- [Acknowlegements](#Acknowledgements)
- [Contact](#Contact)

# Basic PLL Theory

<b>Basic components of a PLL</b> (<i>Image courtesy [wikipedia](https://en.wikipedia.org/wiki/Phase-locked_loop#/media/File:Phase_locked_loop.svg)</i>)
<p><a href="https://commons.wikimedia.org/wiki/File:Phase_locked_loop.svg#/media/File:Phase_locked_loop.svg"><img height="50%" width="50%" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Phase_locked_loop.svg/1200px-Phase_locked_loop.svg.png" alt="Phase locked loop.svg"></a>
 

Why is a Phase-Locked Loop Clock Multiplier IC needed?
To get a precise clock signal without frequency or phase noise.

Which are the circuits that are a minimum requirement for making a PLL?
What is meant by spectral purity of output??

# Open Source Tools Used

* [Google/SKywater 130nm pdks](https://github.com/google/skywater-pdk) (process design kit for usage with SkyWater Technology Foundry's 130nm node) <br>
* [ngspice](http://ngspice.sourceforge.net/download.html) (simulation) <br>
* [magic](http://opencircuitdesign.com/magic/) (layout design) <br>
* [caravel](https://github.com/efabless/caravel) (design preparation for tapeout)


# Acknowledgements

* I thank Mr. Kunal Ghosh, co-founder [VSD](https://www.vlsisystemdesign.com/) and Lakshmi Sathidevi for their hard work in putting this excellent workshop together.
* I thank [Google](https://github.com/google), [Skywater](https://www.skywatertechnology.com/), [ngspice](http://ngspice.sourceforge.net/), [magic](http://opencircuitdesign.com/magic/) and [efabless](https://efabless.com/) for providing the open source tools that make it possible for a project like this.

# Contact

* Greg Phillips (Author) - greg@thinkitdata.com
* Lakshmi S, MS ECE - lakshmi.sathi96@gmail.com
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
