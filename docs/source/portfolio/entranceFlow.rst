Entrance Flow Modeling
======================

I worked with two other students to model the entrance region of flow into a tube. We developed a numerical and a physical model of this process and compared the two to see how well our prediction worked. The numerical model was based on an existing paper which derived an analytical representation, which we then `implemented in MATLAB`_. We also created a physical demonstration by allowing smoke to pass through a set of flow stabilizers (straws) and then a transparent tube where we could watch and record the flow developing. By matching physical parameters from the physical and numerical model (density, velocity, Reynolds number), we found good agreement between the developing shapes of the two models.

.. _implemented in MATLAB: https://github.com/shawnalbertson/random/blob/main/entranceFlow.m

.. image:: /images/flow/smoke.png
    :width: 500
    :align: center

|