Welcome to ospgui's Documentation
=================================

Table of Contents
-----------------

- `Installation`_
- `Launching the GUI`_
- `Features`_
- `Limitations`_
- `Examples`_

.. _installation:

Installation
============

Graphical User Interface
------------------------

The ``ospgui`` provides a graphical interface for creating and visualising
bridge grillage models without writing Python code directly. It is built with
PyQt5 and distributed as an optional extension to Ospgrillage.

.. note::
   ospgui is an optional tool. To install:

   .. code-block:: bash

      pip install ospgrillage[gui]

.. _launching-gui:

Launching the GUI
=================

Once installed, the GUI can be started from the command line with:

.. code-block:: bash

   ospgui

This will open the *ospgui* window as shown below.
.. image:: _static/gui_screenshot.png
   :alt: GUI Screenshot
   :width: 600px
   :align: center

.. _features:

Features
========

- Interactive geometry setup (straight, multi-span, and curved bridges).
- Material and section property assignment.
- Member assignment (interior beams, edge beams).
- Automatic generation of Python code for Ospgrillage models.
- Optional export to OpenSees command file.
- Integrated visualisation of the generated grillage model.

.. _limitations:

Limitations
===========

- Oblique mesh does not currently apply skew to longitudinal beams.
- Curved bridge functionality is preliminary.
- Some advanced analysis and loading options must still be defined in code.

.. _examples:

Examples
========

Example 1: Create a simple straight bridge
------------------------------------------

```python
from ospgrillage import OspGrillageModel
model = OspGrillageModel(span=30, num_beams=5)
model.generate()
