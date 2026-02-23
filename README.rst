.. image:: https://img.shields.io/badge/dmtn--335-lsst.io-brightgreen.svg
   :target: https://dmtn-335.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-335/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-335/actions/

##################################################################################################################
Quantifying the Performance of the LSST Detection and Deblending Pipeline: Implications for LSB Science and Beyond
##################################################################################################################

DMTN-335
========

We assess the LSST detection and deblending pipeline using source injection experiments on real LSSTCam imaging (data release w_2025_37/DM-52496). Mock NewHorizon galaxies are injected into calibrated single-exposure images, processed through the full pipeline to produce deep coadds, and the resulting catalogues compared against those from unmodified coadds. Injected sources span $18 < \\mu_r < 30$ mag arcsec $^{-2}$, $1 < R_{\\rm eff} < 40$ arcsec, and $10^{7} < M_{*}/M_{\\odot} < 10^{11.5}$ .

We find: (i) detection completeness drops from $\\sim 95$% at $\\mu_r = 20$ to $\\sim 50$% at $\\mu_r = 25$ and $\\sim 10$% at $\\mu_r = 27$ ; (ii) for realistic sources, recovered $r$-band flux is overestimated by $\\sim 100$% at $\\mu_r = 27$ and by an order of magnitude at $\\mu_r = 30$ ; (iii) at fixed $R_{\\rm eff} = 5$ arcsec, flux is increasingly underestimated at fainter surface brightnesses; (iv) 2D $\\mu_r$ - $R_{\\rm eff}$  analysis shows flux underestimation is driven by extendedness, with $R_{\\rm eff} > 15$ arcsec sources underestimated by 40-100%; (v) injecting a bright source ($\\mu_r = 18$) causes $\\sim 60$% of nearest-neighbour detections to be lost; (vi) these biases distort the galaxy stellar mass function below $\\log(M_{*}/M_{\\odot}) \\sim 9$ .

These results affect LSB science, weak lensing shear calibration, photometric redshifts, and transient host-galaxy association. We outline next steps for mitigation within the Science Pipelines.

Links
=====

- Live drafts: https://dmtn-335.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-335

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-335

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
