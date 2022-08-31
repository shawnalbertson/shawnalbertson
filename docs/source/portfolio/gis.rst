GIS Post-processing in Python
==============================

During a semester abroad to the University of Edinburgh, Scotland, I worked for a professor who was interested in using neural networks to determine temperature and salinity of the ocean based on Sentinel-2 multi spectral satellite images. My task was to develop a tool which would take a processed GIS file (NN output) and filter out clouds which proved to confound the data. The two images below shows the result before and after applying the cloud mask. The work was done in Python using GDAL to load and interact with GeoTIFF files in an object-oriented manner.

.. image:: /images/gis/salinity_noCM.png
    :width: 500
    :align: center

.. image:: /images/gis/salinity_withCM.png
    :width: 500
    :align: center

The work began weeks before the start of the pandemic and transitioned into a remote style work setup after I had to move back to the U.S. 
