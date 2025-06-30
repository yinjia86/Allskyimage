This is an example of high-precision calibration for an all-sky image, applied to an all-sky image 
with equal-area projection. Parameter adjustments are necessary for different cameras and projections. 
The example primarily utilizes HEALPix to segment and transform the all-sky image so that Astrometry.net 
can identify stars, and then uses GWCS to calibrate the image with registered stars. In addition to 
Astrometry.net and SExtractor, the Python packages used include numpy, astropy, healpy, scipy, gwcs, 
asdf, zoneinfo, datetime, os, and matplotlib.

The corresponding paper is:
Yin J., Yao Y., Qian X., Liu L., Chen X., Zhai L., 2025, MNRAS, 537, 617. doi:10.1093/mnras/staf056


The program all_sky_calibration_v.ipynb is an improvement over the program allskyimage_uv2ad.ipynb, 
implementing the solution of the projection center and the determination of the projection method, 
and is capable of automatically solving all-sky images. The ZEA and ARC projections have been tested, 
while others have not been tested yet. The AllSky-340 image uses the ARC projection. Due to the low 
image resolution and a smaller number of stars, some positions could not be solved because the star 
image quality was insufficient.

The program all_sky_calibration_v_1.ipynb is an all-sky calibration that does not rely on geographic 
coordinates and observation time, thanks to the celestial coordinate fitting function of GWCS. If your 
geographic coordinates, observation time, and the actual projection of the image do not match, when you 
use all_sky_calibration_v.ipynb, some areas of the all-sky image may not be solvable. all_sky_calibration_v_1.ipynb 
avoids this issue by directly solving based on the equatorial coordinates, which can achieve better solving results. 
Subsequently, the calibration of the horizontal coordinates can be obtained based on the star catalog, 
geographic coordinates, and observation time.

The calibration time for all_sky_calibration_v_1.ipynb is relatively long. Once a calibration is completed, 
the calibration results can be reused, and here we provide all_sky_conversion.ipynb. The all_sky_conversion.ipynb 
compares the rotation angles of the central regions to obtain a rotation matrix, and then calculates the new image 
calibration. However, the calibration accuracy is significantly reduced.
