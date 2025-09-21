=======================
Graphical User Interface
=======================

The ``ospgui`` provides a graphical interface for creating and visualising
bridge grillage models without writing Python code directly. It is built with
PyQt5 and distributed as an optional extension to Ospgrillage.

.. note::
   The GUI is optional. To install with GUI support:

   .. code-block:: bash

      pip install ospgrillage[gui]

Launching the GUI
-----------------

Once installed, the GUI can be started from the command line with:

.. code-block:: bash

   ospgui

This will open the *ospgui* window.

Features
--------

- Interactive geometry setup (straight, multi-span, and curved bridges).
- Material and section property assignment.
- Member assignment (interior beams, edge beams).
- Automatic generation of Python code for Ospgrillage models.
- Optional export to OpenSees command file.
- Integrated visualisation of the generated grillage model.


Limitations
-----------

- Oblique mesh does not currently apply skew to longitudinal beams.
- Curved bridge functionality is preliminary.
- Some advanced analysis and loading options must still be defined in code.
