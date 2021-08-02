<a href ="https://www.vlsisystemdesign.com/pll-design-using-sky130/"><img src =https://www.vlsisystemdesign.com/wp-content/uploads/2021/07/PLL-Workshop-Banner_efabless.png></a>
# Still under construction

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
 
 ngspice is a circuit simulator that numerically solves equations describing (electronic) circuits: These are made of passive and active devices. Time varying currents and voltages are simulated as well as noise and small signal behavior. ngspice is the Open Source successor of the venerable spice3f5 from UC at Berkeley.
 
 ngspice and an optional GUI is installed on Windows10 by following the instructions here: http://ngspice.sourceforge.net/download.html
![ngspice GUI](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/ngspiceGUI.png)



Running Magic on Windows requires the use of Cygwin.  The details of which are documented here: http://opencircuitdesign.com/cygwin/tcltk.html

Part of the Cygwin installation and configuration is the requirement of installing Xwindows.  One problem you'll encounter is trying to install the startxwin package under X11

 ![X11 prereqs](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/X11reqs.png)

startxwin is now called xinit and as such when you launch cygwin xinit is the comment you'll need to execute to launch the Xwindows server which is the prerequisite to launching magic.
 
 ![Cygwin setup](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/cygwinSetup.png)

When attempting to run magic the first time you'll encounter the below error:

greg@DESKTOP-I22BTM7 /cygdrive/d/magic
$ usr/local/bin/magic
<br>**_usr/local/bin/magic: line 43: /usr/local/lib/magic/tcl/tkcon.tcl: No such file or directory_**


This is because when using cygwin the use of / for meaning the root of the filesystem in scripts is interpreted differently than the actual root of the filesystem from the Windows perspective.  If you look at line 43 in the below you can see that we needed to edit for the actual root path to the file.

![magic.sh edit](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/magicScriptEdit.png)

Now magic launches via Cygwin in Xwindows as expected.
![Cygwin X11](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/cygwinXwindows.png)

# Acknowledgements

* I thank Mr. Kunal Ghosh, co-founder [VSD](https://www.vlsisystemdesign.com/) and Lakshmi Sathidevi for their hard work in putting this excellent workshop together.
* I thank [Google](https://github.com/google), [Skywater](https://www.skywatertechnology.com/), [ngspice](http://ngspice.sourceforge.net/), [magic](http://opencircuitdesign.com/magic/) and [efabless](https://efabless.com/) for providing the open source tools that make it possible for a project like this.

# Contact

* Greg Phillips (Author) - greg@thinkitdata.com
* Lakshmi S, MS ECE - lakshmi.sathi96@gmail.com
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
