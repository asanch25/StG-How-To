General Information
===================
This section is primarily meant to provide a description for the various elements on St. George, or common terms that we may use. For a nice reference diagram go `here <referenceimages.rst>`_.

.. _whatis:

What is St. George?
------------
The Strong Gradient Electromagnetic Online Recoil separator for capture
Gamma Ray Experiments, or St. George is a recoil mass separator located at the University of Notre Dame. The main goal of St. George is to measure (:math:`\alpha` , :math:`\gamma`) reactions that are important for astrophysical processes. Recoil separators are complicated machines, so hopefully this explains some of the elements on St. George well enough for you to understand what is going on.





Dipole Magnets
------------


The St. George Dipole magnets are responsible for the charge state selection of the recoils after being created in the HIPPO gas target. In analogy with traditional optics, a dipole magnet seperates particles by p/q much like a prism seperates light by wavelength. 

.. math::

   F = ma = \frac{mv^2}{\rho} 

.. math::
   F = qvB 

.. math::
   qvB = \frac{mv^2}{\rho} 

.. math::
   B\rho = \frac{p}{q} 

where :math:`\rho` is the bending radius of the dipole magnet. I find the most useful interpretation of :math:`B\rho` to be how "hard" it is to bend a particle around the dipole. A particle with a higher :math:`B\rho` is moving faster and harder to bend, and a particle with lower :math:`B\rho` is moving more slowly and easier to bend. A diagram of this is shown below, with the main idea that we want to tune the dipoles such that the most probable charge state of the recoils goes down the center of the beampipe.



.. figure:: images/brho.png
    :width: 400
    :align: center

    Diagram showing the impact of :math:`B\rho` on the trajectory of a charged particle in a dipole magnet.

Quadrupole Magnets
------------
In addition to the 6 dipole magnets, St. George also has 11 quadrupole magnets for focusing and defocusing the beam. The important thing to remember about quadrupole magnets is that if the quadrupole focuses in one direction, it defocuses in the other direction.  It is for this reason that in every application I can think of, quadrupole magnets come in pairs or even triplets. 


.. figure:: images/quadmagnet.png
    :width: 400
    :align: center

    Diagram showing that a quadrupole magnet will be focusing in one axis, and defocusing in the other. This assumes a positively charged beam travelling into the screen.

Wien Filter
------------
The Wien filter is the location where the majority of the rejection of the primary beam takes place. The Wien filter consists of a perpendicular electric and magnetic field that we tune to only allow particles of a specific velocity through. Luckily this effect is easily explainable with only a semester (maybe) of electromagnetism. 

.. math::

   F_B = qvB = \frac{mv^2}{\rho} \rightarrow B\rho = \frac{p}{q} 

.. math::

   F_E = qE = \frac{mv^2}{\rho} \rightarrow E\rho = \frac{p}{q}v 

.. math::

   v = \frac{E}{B} 


The Wien filter preforms the mass separation in the case of an (:math:`\alpha` , :math:`\gamma`) reaction. Due to the beam and the recoil having the same momentum due to momentum conservation, in tuning the Wien filter for a specific velocity, we are actually allowing a particle of a specific mass to pass through. 

TOF vs Energy
------------



Acceptance
----------
.. figure:: images/ag.PNG
    :width: 200
    :align: center



You will hear us talk about the "acceptance" of St. George quite a bit. There are two types of acceptance we are concerned about; energy acceptance, and angular acceptance. As an illustrative example for what I am talking about here, lets consider a generic (:math:`\alpha` , :math:`\gamma`) reaction. In this reaction the beam reacts with the target to create a compound nucleus in an excited state. Upon de-excitation, the :math:`\gamma` can be emitted in any direction. With this freedom comes two extreme cases that effect the kinematics of the recoil producs we wish to measure. The diagram above illustrates these cases. The first extreme case is the emission of the :math:`\gamma` at 90 or 270 degrees with respect to the lab frame. This gives the nucleus a "kick" up or down that creates an angular distribution of recoils. This angular distribution forms a cone of acceptance, the half angle of which is what we refer to when we say angular acceptance. The second extreme is the :math:`\gamma` being emitted at 0 or 180 degrees with respect to the lab frame. Momentum must be conserved, so depending on which way the gamma is emitted, the recoiling nucleus either gains or loses some kinetic energy creating an energy distribution of the created recoils.  
  
Recycling
--------
"Recycling" of the magnets is required any time we need to set a magnet to a higher field than it currently is at. The reason for this is the effect of hysteresis on the magnetic field of the magnets. 


Misc Terms
------------
+ **Beam left/beam right:** left or right as seen by the beam travelling through St. George. 
+ **Rejection:** 

