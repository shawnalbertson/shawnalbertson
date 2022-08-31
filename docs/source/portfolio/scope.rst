CT Scan Intercom
=======================================

I helped to improve the mechanical design of an intercom systems on CT scan machines for GE Healthcare. I took on two main tasks.

1. Designed and prototyped a waterproof intercom enclosure 
2. Evaluated the influence of mechanical vibration on electret microphones which are used on the CT gantry (the scanner itself)

The first task was to make design improvements for an intercom device which lives in the operator control room, sitting on a desk next to a computer. The device has been known to fail over time due to exposure to liquids, as from spills that might arise from an operator spilling a coffee or soda. As such, the device needed to be IPX4, while maintaining good audio quality, and without drastically altering the user interface.

The microphone, volume adjustment, and speakers all posed mechanical design challenges for integrating electronics while preventing fluid ingress. For each element, I designed an enclosure which could be 3D printed and assembled while working from home throughout this project (due to the pandemic). 

*Microphone*

After doing some research on how the problem of waterproofing microphones in personal devices such as phones was solved, I came across acoustic vent. This is an adhesive backed hydrophobic membrane which is designed to resist fluid ingress without affecting audio quality. The microphone was mounted directly behind the vent to keep it securely in place. 

.. image:: /images/scope/scim-mic.png
    :width: 500
    :align: center

|

*Volume control*

Potentiometers for volume control were integrated with an o-ring mounted directly against the front face of the intercom. A small recess in the intercom allowed the o-ring to sit and compress at 5% of the diameter. Since the part was getting 3D printed I was able to isolate the component and test multiple compression factors to balance feel and resistance of turning the knob with the ability to still resist fluid ingress. 

.. image:: /images/scope/scim-pot.png
    :width: 500
    :align: center

|

*Speaker*

Speaker integration posed a third design challenge. To solve this, I specified waterproof speakers with a plastic membrane and that was sealed to a foam ring on the perimeter. I mounted the foam ring to an elevated ridge on the intercom so that only the plastic membrane would be exposed to the exterior.

.. image:: /images/scope/scim-speaker.png
    :width: 500
    :align: center

|

The fully assembled intercom including components can be seen below. To test the device, I spilled a full cup of water on it with a piece of paper inside and was happy to see that no water permeated. I also recorded audio recorded through the microphone to make sure that the acoustic vent and aperture hadn't created any resonance that would negatively affect the audio quality.  

.. image:: /images/scope/scim-print.png
    :width: 500
    :align: center

|

My second task was to come up with a way to assess the effect of mechanical vibration on a microphone which is used in the CT gantry itself (the gantry is the large donut shaped device which actually spins the X-ray tube and detector). To do this, I developed a simple electrodynamic shaker to recreate vibrations seen on the gantry and evaluate the response of the signal recorded by the microphone. I did this working from home with minimal budget and access to only a 3D printer and simple electrical components. 

The testing setup included a control microphone and a vibrating microphone which were mounted side-by-side. A small solenoid vibration motor was used to create the vibrations desired for the study, which was chosen for its mechanical design which allowed us to easily constrain motion along a single axis. An Arduino Uno was used to generate pulse signals as well as record the digital signal from the accelerometer, a 14-bit MMA8451. Microphones were mounted in line with the accelerometers, and analog microhpone signals were measured using an Digilent Analog Discovery.

I designed the fixture in SOLIDWORKS so that it could be easily printed on a Prusa MK3S to accomodate the various electrical components described above. The stationary component of the motor was mounted directly to a base which could in turn be clamped / fastened to a solid surface. The dynamic component was secured to a slider which is constrained to move in a single direction. One microphone ("microphone 1") is mounted to this slider with four screws across a broad face, and the microphone is mounted perpendicular to the direction of vibration. A second microphone ("microphone 2") was included in the setup and is mounted to the base which is ideally stationary. An accelerometer is mounted along with each microphone, and both the accelerometer and microphone breakout boards are secured with a press fit in the 3D printed piece. The modular design of the accelerometer and microphone allows them to be placed on the setup in a repeatable and predictable way. 

.. image:: /images/scope/cad.png
    :width: 500
    :align: center

|

To recreate realistic vibrations, we tuned our system to mimic vibrations which were measured by GEHC on an actual CT scanner. RMS acceleration divided into third octave bins were used as a metric for comparing actual gantry vibrations with those made by our shaker. All data was analyzed in Python using `numpy`, `pandas`, and `matplotlib` libraries. I was able to show that at high frequencies, the vibrating microphone had noticeably higher energy peaks. This should justify an interest in decoupling electret microphones from mechanical vibration, especially using inexpensive methods such as foam, as a way to improve the audio quality of the intercom without overly technical or expensive approaches. 

.. image:: /images/scope/psd.png
    :width: 500
    :align: center

