ROI Creation
============

Spheremask
----------

spheremask creates a spherical mask centered on curpos with the same dimension as srcvol with radius/volume equal to nvoxels. The mask is a binary array where the elements that belong to the sphere mask are set to 1 and all other voxels are set to 0.
 
- **Syntax:**

    > *mask = spheremask(srcvol, curpos, nvoxels, mode)*

 
- **Inputs:**

    > **srcvol:** 3D matrix, usually a data volume from a nifti file.<br>
    > **curpos:** Position where the sphere mask will be centered.<br>
    > **nvoxels:** Radius or Volume size in voxels.<br>
    > **mode:** String with the keywords 'radius' or 'volume' that defines if nvoxels is the number of voxels that compose the ROI (volume) or the radius size (radius).<br>

- **Output:**

    > **mask:** Binary 3D matrix with the same size as srcvol. 
 



Cubicmask
----------

Maxkmask
----------

Regiongrowingmask
-----------------

Img2mask
--------

Contiguousclustering
--------------------

Drawingmask
----------