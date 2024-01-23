---
title: Fundamentals of Antenna Arrays
tags:
  - circuit
project: substack
date_published: 2024-01-28
status: 🚧
final title: Fundamentals of Antenna Arrays
---
Antenna arrays have been the bedrock of radar for decades and have most recently been implemented in commercial communication systems for beamforming in 5G. This article deals with fundamentals of antenna arrays. It will form the basis of phased arrays and beamforming to be discussed in the future.

**You will learn:**

- How antenna arrays create narrow beams
- What is the impact of antenna type and array geometry
- How gain tapering improves array performance
- Detrimental effects of mutual coupling and how to address it

Let's dive in!

---

### Arraying Antennas to Create Narrow Beams

Let's say we have an isotropic antenna radiating a sine wave in space at a given wavelength. The red circles represent peaks of the sine waves, and blue circles represent troughs as shown in Fig 1. The spacing between a red and blue circle represents half a wavelength.

[

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F12cf56fc-f9d9-4fa6-a14f-6dba266a537f_1753x1032.png)



](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F12cf56fc-f9d9-4fa6-a14f-6dba266a537f_1753x1032.png)

Clearly, this radiation pattern is not as directional as we would like. To make the antenna beam point more in a certain direction, let’s place another similar isotropic antenna exactly half a wavelength away from the original one. Then observe how the radiation patterns from these two antennas interfere in space.

[

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc2b20393-cfe0-45f6-a660-6eaa418ddb34_1700x1382.png)



](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc2b20393-cfe0-45f6-a660-6eaa418ddb34_1700x1382.png)

You notice that radiation circles of the same color intersect along the vertical axis resulting in "constructive interference." This means the signals from each antennas add up to create a stronger signal. Along the horizontal axis, the red and blue circles intersect resulting in "destructive interference." The signals from each antenna cancel each other out, resulting in low radiation in that direction. By simply putting two identical antennas a fixed distance apart, you now have an antenna radiation pattern that is narrower than the original single antenna pattern.

Fig 3 shows the antenna gain diagram on the x-y plane looking along the z-axis. This is called the azimuth pattern of the antenna, and is a representation of how strong the antenna signal is as you go around it. The strongest radiation occurs along the Y axis when there is constructive interference, and destructive interference produces a radiation null along the X axis.

However, along the y-z plane the radiation pattern is still isotropic because no signal cancellations occur. It is easier to visualize the 3D radiation pattern for this antenna array as shown in Fig 3. It resembles a donut because the interference pattern from the linear array causes a null only along one direction. 

[

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4e903611-6de9-47a7-98a8-a8f1f9d7487e_1896x1146.png)



](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4e903611-6de9-47a7-98a8-a8f1f9d7487e_1896x1146.png)

Adding more antenna elements to the array will result in a narrower beam. Fig 4 shows the antenna patterns for 2, 4, 8, and 16 element linear arrays, with each antenna separated by half a wavelength. The main beam along the +/- 90 degree direction gets narrower as the number of elements increase, and the radiation along the 0/180 degree directions always produce a null due to wave cancellation.

For higher element arrays, “side lobes” or unwanted radiations occur in certain directions due to imperfect wave cancellation and they increase in number with the number of antennas in the array. Between every lobe, there is still a null and engineers have clever tricks to point it at an interference source to improve signal-to-noise ratio. We will discuss more about this in a future article on adaptive beamforming.

[

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F963a1009-ee3d-4cb7-a6bd-3ada106e52b8_2056x2336.png)



](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F963a1009-ee3d-4cb7-a6bd-3ada106e52b8_2056x2336.png)

### Two Dimensional Antenna Arrays

So far we have produced radiation patterns that are more directed in only one plane. The radiation pattern still emits in all directions in a perpendicular plane, as we saw in the donut 3D radiation pattern of a two element array in Fig 3.

To narrow the radiated antenna beam in both directions, we need a two dimensional antenna array and an NxN element rectangular array is a popular choice. The same principles we encountered in the constructive and destructive interference patterns, now occurs along two perpendicular planes, as will the nulls and grating lobes. Fig 5 shows the radiation pattern of a 2x2, 3x3 and 4x4 rectangular antenna array with isotopic antennas placed half wavelength apart in both directions.

[

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc629d024-6748-4bdf-aa26-2ef75907810e.heic)



](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc629d024-6748-4bdf-aa26-2ef75907810e.heic)

In practice, a 4x4 element array is a popular and even serves as a building block for higher element arrays, or arrays with multiple beams for multiple-input-multiple-output (MIMO) systems. The 4x4 array provides a good trade-off where the feed structures for the antenna array can be designed with minimal loss. Remember that the size of the array grows linearly in each direction as the array size increases. As a result, the transmission lines feeding these antennas are many wavelengths long already. Their losses are important to consider.

### Other Considerations

While working with antenna arrays, there are several other design considerations and practical implementation issues that need to be looked at.

#### Choice of Antenna Element

We have only dealt with isotropic antennas in our analysis so far. If a sharper beam is required, using an antenna element that produces a focussed radiation pattern immediately improves the directivity of the whole antenna array. The choice of the ideal element for the array depends on the application, and is guided by factors such as desired radiation pattern, polarization, and size.

Here are some popular antenna choices for arrays:

- **Dipole Antennas**: Widely used for their relatively small size compared to operating wavelength, simple structure and omnidirectional radiation pattern in the H-plane (donut shaped). They are well suited for high density arrays.
    
- **Patch Antennas**: Popular choice for phased array systems due to its planar geometry and ease of integration with active components for beam steering.
    
- **Slot Antennas**: Useful when antenna arrays need to be integrated into the surface of an object (conformal array) like an aircrafts exterior surface. Their radiation characteristics are similar to dipole antennas.
    
- **Horn Antennas**: Used when wide operating bandwidth is required, or while feeding an array of parabolic dishes. They are stable and often used to calibrate other antenna arrays.
    
- **Yagi-Uda Antennas**: Used when there is a need to have significant control over the radiation pattern and where high directivity is needed. They are physically large and not particularly useful in dense arrays.
    
- **Log-Period Antennas**: Used when broad frequency coverage is required, and often used in spectrum monitoring or electronic warfare.
    

#### Array Geometries

Antennas can be arranged in geometric patterns other than a linear or rectangular shape depending on the application and design requirements. The rectangular array is still a popular choice when implementing planar antenna array systems into communication systems, but other shapes can be considered as follows:

- **Circular Arrays**: When antennas are placed around a circle, they produce directional beams that can be steered in the azimuth plane. A useful application is in a ship’s navigational system where the antenna needs to scan around in the horizontal plane, and not necessarily up or down.
    
- **Cylindrical Array**: Think of this as a linear array of circular arrays. It provides 360 degree scan in the azimuth plane while also having elevation control (up/down). They are useful in electronic warfare, radar, or navigation.
    
- **Spherical Array**: Useful when beams need to be formed and steered in any directional in 3D space. Useful for satellite communications and advanced radar.
    
- **Conformal Array**: This is when antenna elements are placed along a curved surface to avoid disrupting aerodynamics or aesthetics of an aircraft or vehicle.
    

#### Gain Tapering

In our antenna array analysis, each antenna in the array was fed with equal amplitude and phase signals. We will discuss introducing phase shifts between antenna elements in a separate article on phased arrays. But carefully engineering the amplitude levels (but same phase) can help improve the array performance by reducing the side lobes in the radiation pattern. Here’s how.

Since the peripheral antenna elements in the array do not have a neighboring element to completely cancel out signals in certain directions, they are primary contributors to side lobes in a radiation pattern. **By reducing the signal level being fed to the peripheral antenna elements, the side lobe levels can be significantly reduced.** This is called Gain Tapering.

The trade-off with gain tapering is that the main lobe gets wider reducing the resolution of the antenna array. However, if the overall interference is greatly reduced at the cost of slightly lower main lobe gain, the overall signal-to-noise ratio of the antenna system is improved.

#### Mutual Coupling

We have always considered antenna elements to be independent of each other. But when they are in close proximity, the field radiated by one antenna induces currents in the neighboring antennas. This can have the following implications:

- **Impedance Changes**: The induced current on an antenna changes its input impedance and affects the power delivered to each antenna due to mismatch losses. 
    
- **Radiation Distortion**: When elements are not fed with uniform amplitude, the radiation pattern will get significantly distorted. The main lobe will point in the wrong direction and side lobe level will increase.
    
- **Polarization Changes**: If the elements in the array radiate with a particular [polarization](https://www.digikey.com/en/blog/antenna-polarization-what-it-is-and-why-it-matters), then mutual coupling can result in undesired radiation components, and eventually in polarization losses.
    

Ways to mitigate mutual coupling are usually quite challenging since we are constrained by the half-wavelength spacing requirement between antenna elements. Increasing the spacing would reduce mutual coupling but result in unwanted side lobes called grating lobes due to improper signal cancellations in space.

The use of decoupling networks between antennas is possible but increases the design complexity of the array. Isolation elements like absorbers can be placed between array elements, but this is not usually practical on a planar array.

Mutual coupling is ultimately needs to be incorporated into the analysis of the antenna array via computation techniques. Feed structures and array layouts need to be optimized to mitigate the effects of antenna mutual coupling.

### ⭐️ Key Takeaways

- Arraying antenna elements creates a more directed radiation pattern.
    
- Constructive and destructive interference enhance signals in some directions while cancelling it out in others.
    
- Higher the number of antennas in an array, the more directed the beam.
    
- Choice of array pattern (linear, rectangular, conformal, etc.) depends on the application.
    
- Using antennas with higher directivity increases overall array directivity. Actual choice (dipole, patch, slot, etc.) depends on the application.
    
- Gain tapering can be used to reduce side lobes and increase SNR.
    
- Mutual coupling is a necessary evil that needs to be considered in design.
    

### 📚 Resources

- Fantastic set of videos from Mathworks with beautiful animations on YouTube. Check out the [playlist](https://youtube.com/playlist?list=PLn8PRpmsu08q9U0y7_63Dfz5cawEnicxi&si=c_Dh9PPoI8xrqs3O).
    
- Don Parker and David Zimmermann, “[Phased Arrays — Part I: Theory and Architectures](https://ieeexplore.ieee.org/abstract/document/989953),” IEEE Trans. Microwave Theory and Techniques, Vol. 50, No. 3, Mar. 2002.
    
- Figures in this article have been generated using Matlab’s [Sensor Array Analyzer](https://www.mathworks.com/help/phased/ref/sensorarrayanalyzer-app.html) app. You can try it out with a 30 day trial version.