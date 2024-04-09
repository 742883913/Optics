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

# Gaussian Optics

word|meaning
---|---
vertex|顶点
conjugate|共轭
power|光焦度
dioptre|屈光度
light throughput|光通量


**What is Gaussian Optics?**

- It's a small angle or paraxial approximation circumstance.

**What is power and dioptre?**

- Power is the focal length's reciprocal $1/f$
- Dioptre is the unit when power is measured in metres. It's like $m^{-1}$ .

**What is near point?**

- Near point is the closest distance for human eyes to focus image sharply. This distance always equal to 25cm.

## Ray through a single thin lens

<div align="center"><img src="./pic/g1.png" width="400"></div>

By the geometrical rule, we can see that

$$i-\phi =-\frac{y}{u},r-\phi =-\frac{y}{v},\phi=\frac{y}{R}$$

$$\frac{i}{r}=n\rightarrow -\frac n\nu+\frac1u=\frac1{R_1}(1-n)$$

<div align="center"><img src="./pic/g2.png" width="400"></div>

After that, when through the secong surface we get the last result

$$-\frac1u+\frac1{\nu^{\prime}}=\frac1f \\ \frac1f=(n-1)\left(\frac1{R_1}-\frac1{R_2}\right)$$

It's known as **Guassian formula**.

- For a single magnifying glass, the magnifying power equal to 

  $$M=\frac{V'}{f'}$$

## Concepts

**Angular magnification 角放大率**

- For paraxial rays, angular magnification equals to 

 $$\gamma =\frac{u'}{u}$$

 $u,u'$ is the angle between the ray and the axis on each side of the lens.

**vignetting 渐晕**

- As we can see from the picture, if we put our eye at $E_0$ ,we will miss the off-axis bundle 'bbb'. This is called **vignetting**. But if the angle of 'bbb' is much bigger, then the bundle will be stopped by $L_2$ . This will also cause vignetting.
- Conclusion: Vignetting is a phenomenon that the image center is brighter and the edge is darker. It's caused by
  1. the position we observe
  2. the size of lens

<div align="center"><img src="./pic/g3.png" width="400"></div>


