Overview
========

fMROI Graphical User Interface
------------------------------

The fMROI Graphical User Interface (GUI) is designed to provide users with a user-friendly and intuitive experience for creating Regions of Interest (ROIs) and visualizing neuroimages. The GUI consists of three main control sections:

1. **Listing table of loaded images:** In this section, users can view a table listing the loaded images in the order of overlay. It allows for easy selection of images, enabling or disabling their visualization, and provides the ability to view the value of the voxel pointed by the cursor.

2. **Control of image visualization aspect:** This section enables users to define various aspects of image visualization. Users have the flexibility to choose colormap, threshold, transparency, cursor position, and stacking order of images. These controls allow for customization and adjustment of the visual representation of the neuroimages.

3. **ROI generation and manipulation section:** This section is divided into three tabs: 

    - **ROI Table:** Provides a detailed overview and management of the created ROIs, allowing users to easily modify and organize them.
    - **Gen ROI:** Offers tools and functionalities for generating ROIs, simplifying the complex process with user-friendly options.
    - **Logic Op:** Enables users to perform logical operations on the ROIs, such as combining and selecting regions of interest. This feature enhances the versatility of the software for neuroimage analysis.

The fMROI GUI aims to streamline the workflow of ROI creation and manipulation, providing researchers with an efficient and comprehensive tool for their neuroimage analysis needs.


![fMROI Graphical User Interface](img/fmroi_oveview.png)


Loading Images
--------------

fMROI offers three methods for loading images into the software:

1. **Open NIfTI files:** Clicking on "File > Open" opens a window that allows you to select the images you want to load. The images must be three-dimensional NIfTI files (.nii or .nii.gz). If a 4-D NIfTI file is selected, fMROI will display a warning indicating that only the first 3-D volume from the 4-D array will be loaded. You can select multiple files to be opened at once using this method.

2. **Load templates:** By selecting "File > Load Templates," you can choose from a range of preinstalled templates. These templates include anatomical images, functional maps, and atlases.

3. **Load ROIs:** Clicking on "File > Load ROI" opens a window that allows you to select a ROI file. The ROI file should be a three-dimensional NIfTI file (.nii or .nii.gz). Upon loading the ROI file, fMROI generates a temporary image called "roi_underconstruction.nii," and the ROI is displayed in the "ROI Table" tab. If the loaded ROI image contains multiple ROIs (i.e., if the image is not binary), fMROI will convert the image values to positive integers. Each set of non-zero values will be considered as an independent ROI.

After loading an image using any of the three available options, an entry is generated in the fMROI table of loaded images. The image presentation in fMROI is similar to other neuroimage viewers such as FreeView and FSLeyes, where each loaded image is represented as a layer. Consequently, all the loaded images are stacked on top of each other, and to visualize an image that is below others, you can hide the images on top by unticking the checkbox in the first column next to the image name (1). Alternatively, you can adjust the transparency by decreasing the opacity in the control of image visualization aspect or apply thresholding to the top images using the Min and Max threshold controls. The images are stacked in the order they were loaded, with the last loaded image appearing on top. To change the order of the image stack, simply select the desired image (3 - the name of the selected image will be shown in bold) and use the "down" button (4) to move it down one level or the "up" button (5) to move it up one level. Additionally, the pixel values of each image are displayed in the second column (2), and you can remove a selected image by clicking the "Del" button (6).

![Table of loaded images](img/table_loadedimages.png)

*Please note that in the fMROI table of loaded images, the top image is represented by the last line, while the bottom image is represented by the first line.*

Image Visualization Aspect
--------------------------

**Controls**

![Controls of Image Visualization Aspect](img/image_controls.png)

The viewer contains 4 axes that display 3 planar slices (axial, coronal, and sagittal) and a volumetric render. Every image is associated with a colormap selected in the image colormap dropdown menu (`2`). fMROI comes with several Matlab default colormaps, but it is also possible to load a custom colormap or a Lookup table (LUT). The custom colormap must be an nx3 RGB array with values between 0 to 1 stored in a `.txt` or `.mat` file. To load a custom colormap file, just select "custom" from the colormap dropdown menu and it will pop up a window for selecting the `.txt` or `.mat` file. The color LUT must have the fields: 1. 'No' or 'Index'; 2. 'Label_Name'; 3. 'R'; 4. 'G'; 5. 'B', and must be stored in a `.tsv` (tab-separated value) or `.mat` (matlab table). The RGB values must be integers between 0 and 255. To load the color LUT, select LUT from the colormap dropdown menu and it will pop up a window to select the LUT file.

Example of Color LUT:

| Index | Label_Name | R   | G   | B   |
|-------|------------|-----|-----|-----|
| 0     | label_1    | 0   | 0   | 0   |
| 1     | label_2    | 255 | 255 | 255 |
| n     | label_n    | r_n | g_n | b_n |


By default, fMROI doesn’t display the volumetric render of the images. To create an image render, just tick the checkbox "3D" (`1`). After displaying the volumetric image, you can select the color of the volume from the render color dropdown menu (`3`). 

Once the images are displayed, you can change their visualization aspects through the slide bars.
Minimum and maximum threshold (`4`) will define the image values to be displayed. If "Min thrs" is lower than "Max thrs", fMROI displays only those voxels that have intensity higher than "Min thrs" AND lower than "Max thrs". Otherwise, if the "Min thrs" is higher than "Max thrs", it displays those voxels that have values higher than "Min thrs" OR lower than "Max thrs".
If you want to change the image contrast, i.e., specify a range of the colormap to be displayed, you must move the sliders Max and Min color (`5`). Finally, for changing the image opacity, you just need to move the sliders "Slice opac" to give transparency to planar images and the slider "Render opac" to give transparency to the render (`6`).

*Please note that only the selected image will be affected by the control changes.*


