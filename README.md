This is an example of high-precision calibration for an all-sky image, applied to an all-sky image 
with equal-area projection. Parameter adjustments are necessary for different cameras and projections. 
The example primarily utilizes HEALPix to segment and transform the all-sky image so that Astrometry.net 
can identify stars, and then uses GWCS to calibrate the image with registered stars. In addition to 
Astrometry.net and SExtractor, the Python packages used include numpy, astropy, healpy, scipy, gwcs, 
asdf, zoneinfo, datetime, os, and matplotlib.


The corresponding paper is:
Yin J., Yao Y., Qian X., Liu L., Chen X., Zhai L., 2025, MNRAS, 537, 617. doi:10.1093/mnras/staf056
