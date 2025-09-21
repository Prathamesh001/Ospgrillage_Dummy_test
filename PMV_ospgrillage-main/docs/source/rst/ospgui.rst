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

.. _ospgui-user-guide:

osp-gui User Guide
==================

Introduction
------------
The `osp-gui` is a graphical user interface for generating OpenSeesPy scripts for bridge analysis. This guide provides a detailed walkthrough of all the features and tabs available in the application window.

.. figure:: _images/ospgui-init.png
   :alt: Main `osp-gui` Window
   :align: center
   
   The main window of the `osp-gui` application.

User Interface Overview
-----------------------
The main window is organized into several tabs, allowing you to input different types of data for your bridge model. On the top, you'll find a menu bar with **File** and **Run Analysis** options. The main panel is divided into two sections: the **Input Panels** on the left and the **Code View** on the right.

|

File Menu
---------
* **New**: Start a new project.
* **Open**: Open an existing project file.
* **Save**: Save the current project.
* **Exit**: Close the application.

Run Analysis Menu
-----------------
* **Run Analysis**: Executes the OpenSeesPy script based on the current inputs.

|

Input Panels
------------
The input panels are organized into four tabs: **Geometry**, **Materials**, **Sections**, and **Members**.

.. _geometry-tab:

Geometry Tab
++++++++++++
This tab allows you to define the fundamental geometric properties and meshing of your bridge.

.. figure:: _images/geometry-tab.png
   :alt: Geometry Tab in `osp-gui`
   :align: center

   The Geometry Tab with basic bridge parameters and mesh settings.

* **Basic Geometry**
    * **Bridge Name**: A name for your bridge model.
    * **Length**: The total length of the bridge (e.g., 30.00 m).
    * **Width**: The total width of the bridge (e.g., 10.00 m).
    * **Left Skew Angle**: The skew angle on the left side (e.g., 0.00 degrees).
    * **Right Skew Angle**: The skew angle on the right side (e.g., 0.00 degrees).

* **Mesh Settings**
    * **Bridge Type**: Defines the overall structural type (e.g., `Straight`).
    * **Longitudinal Beams**: The number of beams along the length of the bridge (e.g., `5`).
    * **Transverse Beams**: The number of beams across the width of the bridge (e.g., `10`).
    * **Mesh Type**: The type of mesh to be generated (e.g., `Ortho`).

* **Output Mode**
    * **Opensees Command File**: Generates the OpenSees script file.
    * **Visualization**: Displays a graphical representation of the generated mesh.

.. _materials-tab:

Materials Tab
+++++++++++++
Define the material properties for the bridge components.

.. figure:: _images/materials-tab.png
   :alt: Materials Tab in `osp-gui`
   :align: center

   The Materials Tab for defining material properties.

* **Material Properties**
    * **Material Type**: Select the type of material (e.g., `Concrete`).
    * **Standard Code Options**:
        * **Standard Code (Preset)**: Choose a standard code for material properties (e.g., `AS5100-2017`).
        * **Grade of material**: Select a specific grade or strength (e.g., `32MPa`).
        * **Use Preset?**: Use the predefined values from the selected code.
        * **Custom Values**: Manually enter custom material properties.

.. _sections-tab:

Sections Tab
++++++++++++
This tab is for defining the cross-sectional properties of the bridge members.

.. figure:: _images/sections-tab.png
   :alt: Sections Tab in `osp-gui`
   :align: center

   The Sections Tab for defining cross-sectional properties of beams.

* **Longitudinal Section**
    * Defines properties for the main longitudinal beams.
    * Parameters include **Area (A)**, **Torsional Constant (J)**, **Moment of Inertia (Iz)**, **Moment of Inertia (Iy)**, **Shear Area (Az)**, and **Shear Area (Ay)**.

* **Transverse Section**
    * Defines properties for the transverse beams.
    * Parameters include **Area (A)**, **Torsional Constant (J)**, **Moment of Inertia (Iz)**, **Moment of Inertia (Iy)**, **Shear Area (Az)**, **Shear Area (Ay)**, and **Unit Width**.

* **End Transverse Section**
    * Defines properties for the transverse beams at the ends of the bridge.
    * Includes the same set of parameters as the Longitudinal and Transverse sections.

* **Edge Longitudinal Section**
    * Defines properties for the longitudinal beams at the edges of the bridge.
    * Includes the same set of parameters as the other sections.

.. _members-tab:

Members Tab
+++++++++++
This tab defines the spacing and offset for the bridge members.

.. figure:: _images/members-tab.png
   :alt: Members Tab in `osp-gui`
   :align: center

   The Members Tab for defining member spacing and edge offsets.

* **External to Internal distance**: Defines the spacing between the external and internal members (e.g., `2.50 m`).
* **Edge Beams**: Defines the offset of the edge beams from the overall bridge width (e.g., `0.50 m`).

|

Code View
---------
The **Code View** panel on the right displays the generated OpenSeesPy script based on your input parameters. This allows you to review the script before running the analysis.

|

Generation and Visualization
----------------------------
* **Apply Changes**: Saves the current parameters to be used in script generation.
* **Create Geometry**: Generates the model and displays a visualization if the **Visualization** option is selected in the Geometry tab.

.. figure:: _images/visualization-example.png
   :alt: Visualization of Generated Bridge Mesh
   :align: center

   An example of the generated bridge mesh visualization.

This visualization shows the nodes (red and green dots) and members (blue lines) of the bridge model.
