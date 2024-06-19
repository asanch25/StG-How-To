HIPPO Operation
===============

Vacuum operation
----------------
Starting with HIPPO mechanically closed but at atmospheric pressure, the pumping operation is as follows:

#. Close the nitrogen vent valve (Photo 1).
#. Ensure the XDS35 pump exhaust valve to atmosphere is open (Photo 2).
#. Ensure the XDS35 pump is ON (Photo 3).
#. Depending on the status of other sections of St. George and the 5U beam line:
   * Close the beam line gate valve at the wall before the quad triplet (Photo 4).
   * Close the beam line gate valve between Q2 and B1 (Photo 5).
   * This isolates HIPPO from the rest of the beamline (Photo 6).

#. Gently open the vacuum operation turbo backing valve (Photo 2) on top of the XDS35 pump.
   * Gradually open the valve until fully open as the pump sound improves.

#. Check that the vacuum readings on CG2 gauges 1-4 (see Photo 7 and the hornet gauge guide) are decreasing.
   * If not, there may be a problem such as leaks or components not being closed properly.

#. Turn on the 4 hornet IGs and verify they indicate activity after 5-10 seconds (Photo 7).

#. When CG2 readings on the gauges reach approximately 1E-1 mbar or better, turn on the 5 turbo pumps using LabVIEW on the console (Photo 16).
   * The LabVIEW code for this operation is located on the St. George control terminal and can be found in XXX.

#. The vacuum as indicated by the four ion gauges on LabVIEW should reach better than ~5x10-5 mbar within 2-3 minutes.

#. Done.

Going from vacuum mode to jet operation
---------------------------------------
Going from vacuum mode to Jet operation
Review the whole procedure before proceeding. This procedure starts assuming vacuum mode operation with the recirculation side fully separated from HIPPO, i.e., Jet valve (Photo 8) closed, recirculation valve (Photo 8) closed, and XDS35 exhaust valve (Photo 2) opened to atmosphere.

#. Close the two beam line gate valves:
   * The one at the wall before the quad triplet (Photo 4).
   * The one between Q2 and B1 (Photo 5).
   - This isolates HIPPO from the rest of St. George (Photo 6).

#. Make sure the HIPPO collimator is fully retracted.

#. Pump the recirculation side:
   * Turn XDS 10 pump ON (Photo 3).
   * Open the two XD9S10 pumping valves (Photo 8).
   - Wait for the vacuum in the recirculation area, as read on the LabVIEW (or Hornet 2 CG1), to reach below ~2E-2 mbar.

#. If the sorption pump (Photo 3) is to be used:
   * Open the two valves on the sorption pump (Photo 9).
   - Wait for the vacuum in the recirculation area, as read on the LabVIEW (or Hornet 2 CG1), to reach below ~2E-2 mbar.
   - You can move ahead while the vacuum is going down.

#. Open the regulator and the exit valve at the helium bottle (Photo 10) on the wall to the right of “Door 10”. The regulator should indicate pressure left in the bottle; the exit pressure gauge should be between 45 and 60 PSI. Pay attention that there is also a nitrogen bottle.

#. At the panel on the wall, turn the power to the roots-blower ON (Photo 11).

#. Purge the helium line by opening the helium purging valve for 3-5 seconds (Photo 9).

#. Close the vacuum mode backing of the turbo pumps valve (Photo 2).

#. Open the two backing of the roots-blower valve (Photo 2).

#. Turn the 5 roots blower ON on the LabVIEW.

#. Open the backing of the turbo Jet mode valve (Photo 12).

#. On the LabVIEW, ensure the vacuum is OK:
   * Must read better than:
     - ~1-3E-3 mbar or better on turbo backing.
     - ~1E-4 mbar on top of the roots blower backing the turbo.
     - ~6E-3 mbar on top of roots blower backing the chamber.
     - ~5E-3 mbar on top of roots blower backing the catcher.
     - ~2E-3 mbar between the roots blower.
     - ~1E-2 mbar on top of the XDS35 pump.

#. Switch the Chamber and Catcher gate valve controller to “override” mode (Photo 13).

#. Open the chamber and catcher gate valve (Photo 13).
   - If the two sorption pump valves (Photo 9) are open, close them.

#. Close the XDS35 exhaust valve (Photo 2).

#. Quickly open the recirculation valve (Photo 8).
   - The XDS10 will pump the small volume coming from the exit of the XDS35; you’ll hear the pump.

#. Wait for recirculation vacuum (on the LabVIEW or Hornet 2 CG1) to go down to ~8E-2 mbar or better.

#. Close the two XDS10 pumping valves (Photo 8).

#. Open the Jet valve (Photo 8).

#. Very gently open the Helium intake valve (Photo 9), keeping an eye on the baratron gauge value (Photo 14).

#. You could use one of the XDS10 pumping valves (Photo 8) to remove the helium for a preliminary purge if desired.

#. If you plan to use the compressor:
   * Inject at least ~200 mbar, but no more than ~500 mbar, before starting the compressor.
   * When ~200-400 mbar is reached, close Helium intake valve (Photo 9) and turn the compressor ON (Photo 15).

#. Use the Helium intake valve (Photo 9) and one of the XDS10 pumping valves (Photo 8) to reach the desired injection pressure.

#. This should be it.
   - If purging is needed, turn the compressor off (Photo 15), open the XDS10 pumping valve (Photo 8), and go to point 17 and proceed.
   - Make sure that if you plan to inject Helium, you close the two beam line gate valves as described in point 1.

#. Done.

Going from jet mode to vacuum operation
---------------------------------------
This procedure starts assuming the Jet is in recirculation mode.

#. Close the two beam line gate valves:
   * The one at the wall before the quad triplet (Photo 4).
   * The one between Q2 and B1 (Photo 5).
   - This isolates HIPPO from the rest of St. George (Photo 6).

#. If using, turn the compressor off (Photo 15).

#. Open one of the XDS10 pumping valves (Photo 8) to remove the helium.

#. Close the Jet valve (Photo 8).

#. When the vacuum in the recirculation zone, as read on the LabVIEW (or Hornet 2 CG1), reaches ~1E-1 mbar:
   - Close the recirculation valve (Photo 8).
   - Quickly open the XDS35 exhaust valve (Photo 2).

#. Close the chamber and catcher gate valve (Photo 13).

#. Remove the chamber and catcher gate valve override (Photo 13).

#. Close the Jet mode turbo backing (Photo 12).

#. Stop the 5 roots-blower in the LabVIEW.

#. Close the two roots-blower backing valves (Photo 2).

#. Open the vacuum mode turbo backing valve (Photo 2).

#. To keep the recirculation zone under decent vacuum, open the second XDS10 pumping valve (Photo 8).

#. Close the Helium bottle (Photo 10), both the regulator and the exit valve.

#. If the roots blower are at a temperature (close to the motor of the biggest one) at which you can leave your hand on:
   - Shutdown the power to the roots blower on the wall panel (Photo 11).
   - If not, leave it overnight before shutting the power off.

#. Done.





Venting HIPPO to atmosphere 
---------------------------
#. Close the vacuum mode turbo valve (Photo 2).

#. Turn off all 5 turbo pumps (Photo XXX).

#. Turn off ion gauges on all 4 hornets:
   * Press menu then hit enter on IG OFF (Photo XXX).

#. Inject some nitrogen into the compressed gas line (Photo XXX).
   - If gas does not come out of the purging line, make sure the HIPPO valve between the zero degree and solid target lines is open.

#. Turn the nitrogen vent valve SLOWLY until CG2 on Hornet 2 reaches ~3E-1 mbar, then close the vent valve.

#. Go to the St. George console and open up the pressure reading LabVIEW (Photo XXX) to watch the turbos spin down.

#. Once turbo speeds are down to ~0-20, slowly inject more nitrogen until you reach ~900 mbar on Hornet 2 CG2.

#. At 900 mbar, loosen the flange on top of HIPPO in the picture (Photo XXX), but do NOT remove the valve.

#. At ~1E3 mbar, tilt the gauge slightly. If you feel air flowing OUT, then you can close the venting valve, and HIPPO has been vented.



Hornet Gauge Guide
------------------



.. list-table:: **Hornet 1**
   :widths: 25 25
   :header-rows: 1

   * - Readout
     - What it is reading
   * - IG
     - Upstream of cube 1
   * - CG1
     - Output of roots blower
   * - CG2
     - Entrance of XDS35 pump
  
.. list-table:: **Hornet 2**
   :widths: 25 25
   :header-rows: 1

   * - Readout
     - What it is reading
   * - IG
     - Downstream of cube 1
   * - CG1
     - Exit of XDS35 (recirculation side)
   * - CG2
     - Side chamber

.. list-table:: **Hornet 3**
   :widths: 25 25
   :header-rows: 1

   * - Readout
     - What it is reading
   * - IG
     - Upstream of cube 2
   * - CG1
     - Backing of 5 turbo pumps (recirculation side)
   * - CG2
     - Central chamber

.. list-table:: **Hornet 4**
   :widths: 25 25
   :header-rows: 1

   * - Readout
     - What it is reading
   * - IG
     - Downstream of cube 2
   * - CG1
     - Exit of jet
   * - CG2
     - Backing of turbos


.. _my_figure:

.. figure:: images/my_figure.png
   :alt: Description of the figure

   Caption for the figure.

This is a reference to :numref:`Figure <my_figure>`.
