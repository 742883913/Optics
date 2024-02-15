<head>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
  <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
      }
    });
  </script>
</head>

# Fourier ptychographic microscopy image enhancement with bi-modal deep learning

## Situations now 

Now the silde scanners collect the information of light power and its phase to get the information like optical thickness.

Limitations: 
1. the nature of image which is traditionally recorded
2. the ultimate image quality that can be achieved by current scanners
    
    Now the scanners' object lenss are of high NA(0.9) and magnification, so its depth of field is limited. So the object in sight is not 100% in focus. So we use a technology to record the image from various planes of focus or we can use image processing technology to deal with the image.

## The FPM

**Outcomings:**
1. Can assess the phase information in a simple way

**Core of operating principle:**

1. numerical aperture synthesis

Its depth of field is directly related to the NA of objective lenss. But it has challenges because of focus variations across large FOV.


**The depth of field of FPM**

This is a coonventional microscope's DOF

$$DOF=\frac{\lambda\cdot n}{NA^2}+\frac{n\cdot\Delta x}{M\cdot NA}$$

n is the refractive index of the medium between the sample and the objective lens, ∆x the camera pixel pitch, M the objective lens magnification factor. It is evaluated to 3.35 μm at λ = 525 nm for our microscope configuration.

But it's not FPM's DOF. We can measure it through a method that  In a first step, the resolution chart is placed at z=0 and its smallest observable detail is identified. In a second step, the resolution chart is progressively moved along z until the previously identified smallest detail is no longer observable. The value zmax thus measured, provides an approximate value of DOF/2.

**The picture of FPM**

The optimal z-position of the objective depends on the modality (intensity and phase). It will cost a lot of time to construct the phase image because of its invisibility. 
