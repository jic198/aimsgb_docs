===============
SrTiO3
===============

Let's take SrTiO3 Σ3[110]/(1-12) tilt grain boundary as an example. The initial structure is a `cubic structure
<https://next-gen.materialsproject.org/materials/mp-5229?formula=SrTiO3>`_. Enter ``110`` for the **Rotation axis**, 
``3`` for the **Σ**, and ``1 -1 2`` for the **GB plane**, and upload an :download:`initial structure <images/SrTiO3.cif>`.
Remember to add the space between the integers in ``1 -1 2``. The default output formate is ``poscar`` for VASP calculations.

.. image:: images/SrTiO3_fig1.png
    :width: 800px

Then click **Build**, you will see the following page. You can either copy & past the output or directly **Download** the file.

.. image:: images/SrTiO3_fig2.png
    :width: 800px

In VASP calculations of interface models, we often want to fix some layers in the bulk. The web app provides a method to fix some layers in each grain. 
For example, if we want to fix 3 center layers in each grain, we can enter ``3`` for the **Fix center layers**.

.. image:: images/SrTiO3_fig3.png
    :width: 800px

Then click **Build**, you will see the following page. 

.. image:: images/SrTiO3_fig4.png
    :width: 800px

Please note that the default tolerance factor to determnine if sites are in the same layer is 0.25 Angstrom.