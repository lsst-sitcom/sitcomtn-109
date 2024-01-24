.. image:: https://img.shields.io/badge/sitcomtn--109-lsst.io-brightgreen.svg
   :target: https://sitcomtn-109.lsst.io
.. image:: https://github.com/lsst-sitcom/sitcomtn-109/workflows/CI/badge.svg
   :target: https://github.com/lsst-sitcom/sitcomtn-109/actions/

###########################################################################
M1M3 - analyze position and rotation stability throughout a tracking period
###########################################################################

SITCOMTN-109
============

Stability during integration time

Analyze displacements of M1M3 for X, Y, Z, RX, RY, and RZ during the period between slews while tracking (approximately 30 s) and check if they comply with the 2 micron and 2e-5 degree requirement.

The data comes from the EFD: imsData
SITCOM-1136

**Links:**

- Publication URL: https://sitcomtn-109.lsst.io
- Alternative editions: https://sitcomtn-109.lsst.io/v
- GitHub repository: https://github.com/lsst-sitcom/sitcomtn-109
- Build system: https://github.com/lsst-sitcom/sitcomtn-109/actions/


Build this technical note
=========================

You can clone this repository and build the technote locally if your system has Python 3.11 or later:

.. code-block:: bash

   git clone https://github.com/lsst-sitcom/sitcomtn-109
   cd sitcomtn-109
   make init
   make html

Repeat the ``make html`` command to rebuild the technote after making changes.
If you need to delete any intermediate files for a clean build, run ``make clean``.

The built technote is located at ``_build/html/index.html``.

Publishing changes to the web
=============================

This technote is published to https://sitcomtn-109.lsst.io whenever you push changes to the ``main`` branch on GitHub.
When you push changes to a another branch, a preview of the technote is published to https://sitcomtn-109.lsst.io/v.

Editing this technical note
===========================

The main content of this technote is in ``index.rst`` (a reStructuredText file).
Metadata and configuration is in the ``technote.toml`` file.
For guidance on creating content and information about specifying metadata and configuration, see the Documenteer documentation: https://documenteer.lsst.io/technotes.
