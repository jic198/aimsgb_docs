===============
FCC Ni
===============

Let's take Ni Σ7[111]/(1 -3 2) tilt grain boundary as an example. The initial structure is an `FCC lattice structure
<shttps://next-gen.materialsproject.org/materials/mp-23?chemsys=Ni>`_::

    from aimsgb import GrainBoundary, Grain

    s_input = Grain.from_file("POSCAR_Ni") 
    gb = GrainBoundary([1, 1, 1], 7, [1, -3, 2], s_input)
    structure = Grain.stack_grains(gb.grain_a, gb.grain_b, direction=gb.direction)
    
.. image:: images/Ni_fig1.png
    :width: 400px

``s_input`` can also be created using ``from_mp_id`` method by giving an ``mp_id`` from `Materials Project <https://materialsproject.org/>`_. 
The ``mp_id`` of an FCC Ni is `mp-23`::

    s_input = Grain.from_mp_id("mp-23") 
