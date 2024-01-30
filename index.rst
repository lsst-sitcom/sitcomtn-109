###########################################################################
M1M3 - analyze position and rotation stability throughout a tracking period
###########################################################################
.. sectnum::

Laura Toribio San Cipriano

Latest Revision: 2024-01-29

.. note::
   **This technote is a work-in-progress.**

Abstract
========
This technical note describes the analysis and results of the positional and rotational stability of M1M3 through the tracking periods. The notebook is located within the notebooks_vandv GitHub repository, SITCOM-1136_M1M3_analysis_stability_tracking, and the associated ticket `SITCOM-1136 <https://jira.lsstcorp.org/browse/SITCOM-1136>`_.

We analyze displacements of M1M3 for X, Y, Z, RX, RY, and RZ during the period between slews while tracking (innitially we have been told that the tracking period is 30 s) and check if they comply with the 2 micron and 2e-5 degree requirement.

The results show that during tracking the requirements were satisfied. Only a few cases were not satisfied and it was always in the first seconds of the tracking. The detailed study of the stability in the first seconds of tracking does not belong to this ticket.

Before starting the analysis, we had been told that the duration of the tracking was 30 seconds. However, after analyzing all the tracking for two nights, the duration is 42 s. 

The data comes from the EFD: imsData

Description
==================
We have analyzed the vibrations of M1M3 using EFD data for the 6 possible motions (Position: X, Y and Z and Rotation: X, Y, Z) during the tracking period. 
We have first analyzed each of the motions individually and then we have analyzed them as a whole.

We have analyzed all the tracking for the nights 20-12-2023 and 22-12-2023.

Analysis of M1M3 during tracking
================

Requirement verified
-------------------
::

   req_rms_position = 2e-3 ## mm, tolerance from repeatability requirement for IMS positional
   req_rms_rotation = 2e-5 ## degrees, tolerance from repeatability requirement for IMS rotational

::

Test Data
---------
day Obs = 2023-12-20 and 2023-12-22

The events have been selected from block 146 in compliance:

::

   type == TMAState.TRACKING
   endReason == TMAState.SLEWING

::

We have eliminated from the analysis those tracking whose time was less than 2 seconds. These trackings are considered errors and tests and in any case there were no more than 3 cases per night.

The RMS was calculated with a rolling of 10 (50 rolling is approximately 1 s of movement). To avoid errors in the RMS when introducing data from the slew, the movement before and after the tracking, we performed the analysis from 0.1 seconds from the beginning and 0.1 seconds before the end.


Results
---------

.. list-table:: RMS greater than required in the first 3 s
   :widths: 25 25 50
   :header-rows: 1

   * - Column
     - dayObs = 20231220
     - dayObs = 20231222
   * - XPos
     - 33
     - 26
   * - YPos
     - 0
     - 1
   * - ZPos
     - 0
     - 0
   * - XRot
     - 19
     - 13
   * - YRot
     - 22
     - 22
   * - ZRot
     - 26
     - 32
   * - All
     - 34
     - 37

On the night of 12/20/2023 we analyzed 226 trackings and found instability in the first 3 seconds in 34 of them, i.e. 15%.
On the night of 12/22/2023 we analyzed 326 trackings and found instability in the first 3 seconds in 37 of them, i.e. 11%.

Examples
------------------
.. figure:: /_static/xPos.png
   :name: fig-xPos

.. figure:: /_static/xRot.png
   :name: fig-xRot

.. figure:: /_static/yRot.png
   :name: fig-yRot

.. figure:: /_static/zRot.png
   :name: fig-zRot


Analysis tracking time
=====================

Conclusion
=============



See the `Documenteer documentation <https://documenteer.lsst.io/technotes/index.html>`_ for tips on how to write and configure your new technote.


.. abstract::

   Stability during integration time
