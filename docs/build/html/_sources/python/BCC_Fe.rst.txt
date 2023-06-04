===============
BCC Fe
===============

Let's take Fe Σ5[001]/(120) tilt grain boundary as an example. The initial structure is a `BCC lattice structure
<https://next-gen.materialsproject.org/materials/mp-13?material_ids=mp-13>`_::

    from aimsgb import GrainBoundary, Grain

    s_input = Grain.from_file("POSCAR_Fe") 
    gb = GrainBoundary([0, 0, 1], 5, [1, 2, 0], s_input)
    structure = gb.build_gb()
    
.. image:: images/Fe_fig1.png
    :width: 400px

``s_input`` can also be created using ``from_mp_id`` method by giving an ``mp_id`` from `Materials Project <https://materialsproject.org/>`_. 
The ``mp_id`` of a BCC Fe is `mp-13`::

    s_input = Grain.from_mp_id("mp-13") 

To construct a bigger supercell for each grain, say 2 unit cells::

    gb = GrainBoundary([0, 0, 1], 5, [1, 2, 0], s_input, uc_a=2, uc_b=2)
    structure = gb.build_gb()

.. image:: images/Fe_fig2.png
    :width: 400px

To construct a Fe Σ5[001]/(001) twist grain boundary::

    gb = GrainBoundary([0, 0, 1], 5, [0, 0, 1], s_input)
    structure = gb.build_gb()

.. image:: images/Fe_fig3.png
    :width: 400px

It's possible to shift one of the grain along the grain boundary plane. For example, 
let's say we want to have one of the grain shifted for 0.2 Å along a-axis::

    gb = GrainBoundary([0, 0, 1], 5, [1, 2, 0], s_input)
    gb.grain_a.translate_sites(range(len(gb.grain_a)), [0.2, 0, 0])
    structure = gb.build_gb()

.. image:: images/Fe_fig4.png
    :width: 400px