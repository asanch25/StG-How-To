St. George Energy Change Procedure
==================================
This section will go over how we go about changing energies on St. George, as well as what should be done on the 5U to achieve this. These steps are meant to be done in the order they are presented, but many of them can be done in parellel with the help of the second shifter. If you are a St. George member on shift it is your job to know, or learn how to, delegate some of these tasks for the second shifter so that energy changes can have a quicker turnaround. This *will* take forever if you try to do it by yourself.

5U Steps
--------
On the 5U side of things, we need to actually lower the terminal voltage so that we are producing a beam that is lower in energy. The steps to do so are as follows

* Double check that the 5U master reference is on
* Close cup 2, the cup directly after the analyzing magnet
* Lower the 5U analyzing magnet slowly, and you want to end ~0.2G above where you want to be as the magnet does tend to drift down a bit
  * If you are doing a larger energy step, you might want to lower the terminal voltage in tandem with lowering the analyzing magnet current so that you don't have to refind it afterwards.
  * For smaller energy steps, you should close cup 1 and do the steps seperately.
* Turn off the liner by setting the CPO gain from 70% to 30% and turning off the liner power supply
* Bring down the terminal voltage until you have
* Scale the 5U triplet and 5U beamline Wien filter according to the suggested values in the run spreadsheet
* Check the 5U quartz and correct the position of the beamspot to match the reference photo you should have taken.
  * Horizontal corrections should be made with the 5U switching magnet. 
  * Vertical corrections should be made with the 5U beamline Wien filter.





StG Steps
---------
Immediately after a run you want to do several things.
* Close StG faraday cups
* Retract the detectors using StG magnet control interface
* Record the following in the run spreadsheet
  * Ending pressure
  * Ending NMR
  * Ending cup currents

Once these are complete, and in paralell with the steps needed to scale down in energy on the 5U the procedure for scaling StG is as follows.

* Open the remote slits
* Remove gas from HIPPO and close the elastic shutter
* Remove bias from Si detector and MCPS **Why?**
* Scale StG according to the new NMR
* Set StG WF electric field to the beam value in the run spreadsheet
* Insert the 2mm collimator into HIPPO
* Maximize transmission between HIPPO entrance and detector cup
 * Make sure current on the mass slits is <2nA
 * Make sure transmission is as close to 100% as possible. Rememeber that the current may read lower values at the detector cup due to residual vacuum interactions.
* Take collimator out
* Close remote slits all the way

.. note::

   This next step is very important. This is one of the things you want to let your second shifter know to remind you about. 
* Set StG Wien filter electric field to the **recoil** value in the run spreadsheet
* Add gas to HIPPO and open elastic shutters
* Bias MCPs and Si detector
* Test rejection
 * Make sure the scope is set to trigger on the correct signal
 * Double check that the remote slits are all the way in
 * Triple check that the Si detector and MCP2 are retracted
 * Open all the faraday cups
 * Insert MCP1 and open the remote slits symmetrically until you read ~1kHz on the scope
 * Make sure detector cup is out and then lower MCP2, make sure it is also at ~1kHz
 * Insert Si detector, make sure it is ~1kHz
* Record HIPPO entrance and exit cup currents
* Record starting gas pressure
* Begin Run


