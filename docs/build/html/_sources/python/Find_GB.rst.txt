=====================
Find Grain Boundaries
=====================

In this example, I will show you how to print out available Σ, rotation angles, grain boundary (GB) planes, and coincident site lattice (CSL) matrices from a 
given rotation axis. The purpose of this method is to provide you the grain boundary information. For example, if you are not sure what the GB plane is for a 
GB you want to generate, you can find this information in `GBInformation`. Let's say you want to create a Σ3[110] GB, but you are not sure what the available 
GB planes are. To find this information::

    from aimsgb import GBInformation

    print(GBInformation([1, 1, 0], 30).__str__())


    Grain boundary information for rotation axis: 110
    Show the sigma values up to 30 (Note: * means twist GB, Theta is the rotation angle)
    |  Sigma  |  Theta  | GB plane   | CSL matrix   |
    |---------+---------+------------+--------------|
    |    3    |  70.53  | (-1 1 1)   | -1  1  1     |
    |         |         | (1 -1 2)   | 1 -1  1      |
    |         |         | (1 1 0)*   | 1  2  0      |
    |    9    |  38.94  | (-1 1 -4)  | -1 -2  1     |
    |         |         | (-2 2 1)   | 1  2  1      |
    |         |         | (1 1 0)*   | -4  1  0     |
    |   11    |  50.48  | (-3 3 2)   | -3  1  1     |
    |         |         | (1 -1 3)   | 3 -1  1      |
    |         |         | (1 1 0)*   | 2  3  0      |
    |   17    |  86.63  | (3 -3 -4)  | 3 -2  1      |
    |         |         | (-2 2 -3)  | -3  2  1     |
    |         |         | (1 1 0)*   | -4 -3  0     |
    |   19    |  26.53  | (-3 3 1)   | -3  1  1     |
    |         |         | (1 -1 6)   | 3 -1  1      |
    |         |         | (1 1 0)*   | 1  6  0      |
    |   27    |  31.59  | (-5 5 2)   | -5  1  1     |
    |         |         | (1 -1 5)   | 5 -1  1      |
    |         |         | (1 1 0)*   | 2  5  0      |

Here, I print out the GB information with Σ up to 30. As you can see, the available GB planes for a Σ3[110] GB are `(-1 1 1), (1 -1 2), and (1 1 0)`. 
`(-1 1 1) and (1 -1 2)` are for tilt GB and `(1 1 0)` is for twist GB. 