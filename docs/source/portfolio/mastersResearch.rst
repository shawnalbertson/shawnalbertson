Masters Research
================

**Phase resolved water wave predictions for the active control of floating bodies**

My masters thesis is aimed at answering two main questions:

1. How can we make phase resolved wave predictions on hardware that can be available in real time?
2. How can those wave predictions be used to stabilize a floating body?

While the wording of the title is general for the control of 'floating bodies', the work is funded by the Department of Energy with floating offshore wind turbines (FOWT) in mind. Because floating turbines are subject to oscillations that result from wave loading (among other things), the use of a wave forecast to stabilize a float has the opportunity to greatly increase the lifetime of a FOWT. 

The two questions each come with their own set of challenges. To answer the first, I have been able to use the URI Narragansett Bay Campus wave tank to create and measure series of irregular waves. I have focused on understanding and implementing deterministic linear wave models developed by Grilli et. al. :cite:p:`grilli11` which is centered around a spatio-temporal free surface decomposition into linear wave components. Using a deep water dispersion relation we can propogate the surface forward in time to come up with a phase resolved wave forecast. We use stationary capacitive wave gauges which penetrate the free surface to take wave measurements. Data is collected and buffered by a National Instruments DAQ and processed locally on the PC using our algorithm. All hardware control and data processing is done in MATLAB. To learn more about the process, visit our `documentation page`_.

.. _documentation page: https://py-wrp.readthedocs.io/en/latest/overview.html

To answer the second question I have been working with a barge model which had been modeled previously by our lab. I designed and built a physical moving ballast system which is mounted to the surface of the model barge and can take commands from the wave model. I am currently working on developing a feedforward controller for the linearized model to make use of the forecasted wave elevations.

My work will be presented at the NAWEA/ WindTECH conference at the University of Delaware in mid-september.


.. footbibliography::