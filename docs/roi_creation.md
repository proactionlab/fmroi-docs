ROI Creation
============

Spheremask
----------

Spheremask creates a spherical mask centered on curpos with the same dimension as srcvol with radius/volume equal to nvoxels. The mask is a binary array where the elements that belong to the sphere mask are set to 1 and all other voxels are set to 0.
 
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

Cubicmask creates a cubic mask centered on curpos with the same dimension as srcvol with edge/volume equal to nvoxels. The mask is a binary array where the elements that belong to the cubic mask are set to 1 and all other voxels are set to 0.
 
- **Syntax:**
    > *mask = cubicmask(vol, curpos, nvoxel, mode)*
 
- **Inputs:**
    > **srcvol:** 3D matrix, usually a data volume from a nifti file.<br>
    > **curpos:** Position where the cubic mask will be centered.<br>
    > **nvoxels:** Edge or Volume size in voxels.<br>
    > **mode:** String with the keywords 'edge' or 'volume' that defines if nvoxels is the number of voxels that compose the ROI (volume) or the edge size (edge).<br>

- **Output:** 
    > **mask:** Binary 3D matrix with the same size as srcvol.<br>


Maxkmask
--------

Maxkmask searches for the kvox highest-intensity voxels of the srcvol contained in the region defined by premask. 

- **Syntax:**
    > *mask = maxkmask(srcvol, premask, kvox)*

- **Inputs:**
    > **srcvol:** 3D matrix, usually a data volume from a nifti file.<br>
    > **premask:** Binary 3D matrix with same size as srcvol. If premask is not a binary matrix, maxkmask will consider as ROI all non-zero elements.<br>
    > **kvox:** Integer that defines the number of non-zero elements in mask.<br>

- **Output:** 
    > **mask:** Binary 3D matrix with the same size as srcvol.<br>


Regiongrowingmask
-----------------

regiongrowingmask is a region growing algorithm that groups neighboring voxels from a seed iteratively according to a rule. The regiongrowingmask has three rules for growing (grwmode), ascending, descending and similarity to the seed, and three other rules for stopping growth, maximum number of voxels (nvox), region set by a mask (premask), and 
maximum difference in values between the seed and its neighbors (diffratio).

- **Syntax:**
    > *mask = regiongrowingmask(srcvol, seed, diffratio, tfMean, grwmeth, nvox, premask)*<br>

- **Inputs:**
    > **srcvol:** 3D matrix, usually a data volume from a nifti file.<br>
    > **seed:** 3D integer vector with the initial position for the growing algorithm.<br>
    > **diffratio:** Scalar that defines the maximum magnitude difference of the neighborhood with respect to the seed, i.e.:<br>
    \|neighbor_mag - seed_mag\| =< \|diffratio\|.<br>
    > **grwmode:** String - Defines de growing mode:
    >> *'ascending'* - searches for the neighbor with the maximum value every each iteration.<br>
    >> *'descending'* - searches for the neighbor with the minimum value every each iteration.<br>
    >> *'similarity'* - searches for the neighbor with the most similar value to the seed.<br>

    > **nvox:** Integer that defines the maximum number of voxels in ROI.<br>
    > **premask:** Binary 3D matrix with same size as srcvol that defines the region where the region growing will be applied. If premask is not a binary matrix, regiongrowingmask will binarize it considering TRUE all non-zero elements.<br>

- **Outputs:**
    > **mask:** Binary 3D matrix with the same size as srcvol.<br>


Img2mask
--------

Contiguousclustering
--------------------

Drawingmask
----------