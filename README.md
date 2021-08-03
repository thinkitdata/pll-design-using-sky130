<a href ="https://www.vlsisystemdesign.com/pll-design-using-sky130/"><img src =https://www.vlsisystemdesign.com/wp-content/uploads/2021/07/PLL-Workshop-Banner_efabless.png></a>
# Still under construction

# PLL-design-using-sky130
This repository will show how to take a basic PLL circuit through all Integrated Circuit (IC) design steps (circuit design, simulation, layout, parasitics extraction and post layout simulation) up thru making a tapeout of the PLL circuit using all open source tools.

# Table of Contents
- [Basic PLL Theory](#basic-pll-theory)
- [Open Source Tools Used and Setup](#open-source-tools-used-and-setup)
- [Simulations](#Simulations)
- [References](#References)
- [Acknowlegements](#Acknowledgements)
- [Contact](#Contact)

# Basic PLL Theory

<b>Basic components of a PLL</b>
![PLL](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/PLL.PNG)

A **_phased-lock loop (PLL)_** is a circuit used to lock an oscillator in phase with an input signal.  A PLL can act as a demodulator to demodulate a carrier frequency, or it can be used to track a carrier or synchronizing signal whose frequency varies with respect to time.  [1]

The **_Phase Frequency Detector_** helps to compare the reference frequency signal(RefCLK) with Output frequency signal(FBCLK) to find out the differnce in the signal.  If the signal is leading then we say that it is output up. When the signal is lagging we say that it is output down..
![PFD](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/PFD.PNG)

The **_Charge Pump_** converts the digital measure of phase/frequeny difference into an analog control signal to control the oscillator.
![Charge Pump](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/CP.PNG)

The **_Low Pass Filter_** is a combination of capacitance, inductance, and/or resistance, intended to produce high attenuation above a specified frequency and little to no attenuation below that frequency.  The frequency at which the transition occurs is called the cutoff frequency.  At the cutoff frequency, the attenuation is 3 decibels (DB) with respect to the minimum attenuation.  Below the cutoff frequency, the attenuation is less than 3dB.  Above the cutoff, the attenuation is more than 3 dB.  [2]
![Low Pass Filter](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/LPF.PNG)


# Open Source Tools Used and Setup

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

# Simulations

 Here are the commands used to generate the prelayout simulations
![PreLayout Simulation Commands](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/PreLayout_Sim_Cmds.PNG)
 
 Phase Frequency Detector
 ![Phase Frequency Detector](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/PD_PreLayout.PNG)
 
 Charge Pump
 ![Charge Pump](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/CP_PreLayout.PNG)
 
 Voltage Controlled Oscillator
 ![Voltage Controlled Oscillator](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/VCO_PreLayout.PNG)
 
 Frequency Divider
 ![Frequency Divider](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/FD_PreLayout.PNG)
 
 Phase Lock Loop
 ![Phase Lock Loop](https://github.com/thinkitdata/pll-design-using-sky130/blob/main/images/PLL_PreLayout.PNG)
 
# References
1. Stan Gibilisco, Neil Sclater, Encyclopedia of Electronics 2nd Edition, 1990, pp. 637-638 ISSN 0-8306-3389-8
2. Stan Gibilisco, Neil Sclater, Encyclopedia of Electronics 2nd Edition, 1990, pp. 529 - 530 ISSN 0-8306-3389-8

# Acknowledgements

* I thank Mr. Kunal Ghosh, co-founder [VSD](https://www.vlsisystemdesign.com/) and Lakshmi Sathidevi for their hard work in putting this excellent workshop together.
* I thank [Google](https://github.com/google), [Skywater](https://www.skywatertechnology.com/), [ngspice](http://ngspice.sourceforge.net/), [magic](http://opencircuitdesign.com/magic/) and [efabless](https://efabless.com/) for providing the open source tools that make it possible for a project like this.

# Contact

* Greg Phillips (Author) - greg@thinkitdata.com
* Lakshmi S, MS ECE - lakshmi.sathi96@gmail.com
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
