==================
Graphene 
==================

Let's take graphene Σ5[001]/(120) tilt grain boundary as an example. The initial structure can be found from `Materials Project
<https://next-gen.materialsproject.org/materials/mp-48?material_ids=mp-48>`_::

    from aimsgb import GrainBoundary, Grain

    s_input = Grain.from_file("POSCAR_C") 
    gb = GrainBoundary([0, 0, 1], 5, [1, 2, 0], s_input)
    structure = gb.build_gb()
.. image:: images/C_fig1.png
    :width: 400px
.. image:: images/C_fig2.png
    :width: 400px