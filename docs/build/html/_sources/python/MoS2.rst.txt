==================
MoS2 
==================

Let's take MoS2 Σ5[001]/(130) tilt grain boundary as an example. The initial structure can be downloaded from this `Materials Project link
<https://next-gen.materialsproject.org/materials/mp-2815?formula=MoS2>`_::

    from aimsgb import GrainBoundary, Grain

    s_input = Grain.from_file("POSCAR_MoS2") 
    gb = GrainBoundary([0, 0, 1], 5, [1, 3, 0], s_input)
    structure = gb.build_gb()

.. image:: images/MoS2_fig1.png
    :width: 400px

You will see a warning saying "The lattice system of the grain is not orthogonal. aimsgb will find a supercell of the grain structure that is orthogonalized. This may take a while." 
It took me 3 min to generate the MoS2 grain boundary structure on my laptop. What takes it so long is the process of calculating the transformation matrix. In the future, I may store
the transformation matrices in a database so that it doesn't need to be calculated every time.

``s_input`` can also be created using ``from_mp_id`` method by giving an ``mp_id`` from `Materials Project <https://materialsproject.org/>`_. 
The ``mp_id`` of MoS2 is `mp-2815`::

    s_input = Grain.from_mp_id("mp-2815") 

Notice that some atoms at the grain boundary sit too close to each other. Let's add 1 Å distance between the grains::

    structure = gb.build_gb(add_if_dist=1)

.. image:: images/MoS2_fig2.png
    :width: 400px
