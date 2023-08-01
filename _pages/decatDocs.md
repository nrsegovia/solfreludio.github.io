---
layout: page
permalink: /decatdocs/
title: Docs
description: Stuff for DECAT data.
nav: false
---

### General Considerations



---
 
 
* Photometry has been processed using *photpipe*, which in turn uses **DOPHOT** to compute all the relevant quantities.
* Calibration catalogs were built using [DECaPS1](http://decaps.skymaps.info/oldwebsite/index.html) band-merged catalogs, where we also applied the offsets mentioned in the documentation. For reference:

>To shift the DECaPS magnitudes to the [Scolnic et al. (2015)](https://ui.adsabs.harvard.edu/abs/2015ApJ...815..117S/abstract) absolute calibration, offsets of 0.020, 0.033, 0.024, 0.028, and 0.011 mag must be added to the DECaPS grizY magnitudes, respectively.

This step was necessary as we were using archival data provided by Armin Rest as well, which also had the offsets incorporated.

* CCD numbering goes up to 61, as one CCD is [not working](https://noirlab.edu/science/programs/ctio/instruments/Dark-Energy-Camera/Status-DECam-CCDs).
* For each field (eta Car and DECaPS East), each CCD has a corresponding directory. Then, inside each directory, there are files with names realted to their corresponding band, date and exposure number. Example: For band _g_ of CCD 5 in the DECaPS East field, you would browse the `5/` directory within the respective `tar.gz` file (`decaps_east1-9.tar.gz`). Then, all _g_ band observations would follow the pattern `5/decaps_east.g.DATE.EXPNUM_1.sw.dcmp`. The same convention works for the `eta_car` field and the other bands.
* The `.dcmp` files are `FITS` files, so you can read them accordingly.
* Columns within the `.dcmp` files are defined as follows, according to the *photpipe* [documentation](https://photpipe-docs.readthedocs.io/en/latest/):

---

```
COLTBL1 = 'Xpos              ' / X position

COLTBL2 = 'Ypos              ' / Y position

COLTBL3 = 'M                 ' / PSF fitted instrumental magnitude (m=-2.5*log10(flux))

COLTBL4 = 'dM                ' / Error in M

COLTBL5 = 'flux              ' / flux in counts

COLTBL6 = 'dflux             ' / error in flux

COLTBL7 = 'type              ' / Type of object, as defined by dophot (1=stellar, 2=extended, 3=double star, 7=low S/N thus less free parameter fit, everything else is bad)

COLTBL8 = 'peakflux          ' / peakflux of fit

COLTBL9 = 'sigx              ' / sigx of fit, as defined by dophot

COLTBL10= 'sigxy             ' / sigxy of fit, as defined by dophot

COLTBL11= 'sigy              ' / sigy of fit, as defined by dophot

COLTBL12= 'sky               ' /

COLTBL13= 'chisqr            ' / chisqr of object

COLTBL14= 'class             ' / Classification of object, as defined by Sextra

COLTBL15= 'FWHM1             ' / FWHM along minor axis

COLTBL16= 'FWHM2             ' / FWHM along major axis

COLTBL17= 'FWHM              ' / FWHM

COLTBL18= 'angle             ' / Position angle

COLTBL19= 'extendedness      ' / Extendedness parameter (dophot)

COLTBL20= 'flag              ' / flags set by cleanim (hexadecimal), 0x1:at least 1 pixel within aperture of size defined by CMP_APERTURESIZE*FWHM, 0x8: central pixel of fit is masked

COLTBL21= 'mask              ' / masks within aperture: all masks from the mask file within the aperture are 'or'ed.

COLTBL22= 'Nmask             ' / # masked pixels within aperture of size defined by CMP_APERTURESIZE*FWHM

COLTBL23= 'RA                ' / RA of object in deg (this was added by Will and Brian, but is not used anymore and set to 0)

COLTBL24= 'Dec               ' / Dec of object in deg (this was added by Will and Brian, but is not used anymore and set to 0)
```
As you can probably notice, the coordinates are not included, but can be computed using the WCS information in the header and the X/Y pixel positions.

---

* If you are interested in the specific description of each *DOtype* (`COLTBL7 = 'type` in the previous table), you can check the following, which corresponds to Appendix C of the [DoPHOT Manual](https://github.com/M1TDoPHOT/DoPHOT_C/tree/master/manual4.0):

---

```

Type 1:  A 'perfect' star. Was used in computing weighted mean shape
         parameters for stars.

Type 2:  Object is not as peaked as a star, and has been interpreted
         to be a 'galaxy'. Shape parameters were calculated specifically
         for this object.

Type 3:  An object found to be not as peaked as a single star was
         interpreted to be two very close stars. This is one component
         of such a close pair. Final fit to this component used mean shape
         parameters for single star.

Type 4:  Failed to converge on a 4-parameter fit using mean single
         star shape. Photometry is extremely unreliable.

Type 5:  Not enough points with adequate S/N could be found around this
         object while attempting a 7-parameter fit to determine shape.
         Indicates a problem with the local environment, although a
         4-parameter fit with mean star shape succeeded. Photometry is
         suspect, and this may not be a bona-fide star.

Type 6:  Too few points with adequate S/N to do even a 4-parameter fit
         with mean star shapes. Object NOT subtracted from image.

Type 7:  Object was too faint to attempt a 7-parameter fit. No object
         classification could be done, so it might be a faint galaxy
         or two closely spaced stars. Photometry is OK (from successful
         4-parameter fit with mean shapes) provided the
         object is really a star.

Type 8:  These are obliterated regions due to data saturation or
         identification of cosmic rays.

Type 9:  If an attempt to determine the shape of an object fails to
         converge, it is classified as object type 9.
         Photometry is unreliable.
```

* When constructing light curves, you can get the necessary information from the header (i.e., `MJD` and exposure times).  

### File Access

___
* **Image access**: head to the [NOIRLab Data Archive search portal](https://astroarchive.noirlab.edu/portal/search/) and use `2021A-0921` as the Program Number. From there, on the categories available on the left-hand side you should select `Product Type -> image` and `Process Type -> instcal`. To separate between fields, go back to the portal and use either `(270.889, -29.530)` (DECaPS East), or `(161.262, -59.684)` (eta Car) as your `(RA, Dec)`.


### Known Issues


---
Besides the absence of one CCD, there are several problems that we have found while working with the data:

* Worse quality of the first night images of the `DECaPS East` field. This can be seen both in the final PSF photometry results as an increase in the number of `DOtype == 3` sources, as well as in the images themselves since the entire field looks blurry and some stars seem to be duplicated. Thus, caution is recommended when interpreting occasional spikes in brightness during the first night for some sources. A frame-by-frame analysis shows that special care is needed when dealing with the following frame numbers (`EXPNUM`): `1004881,1004882,1005155,1005163,1005239,1005248,1005267,1005268,1005269,1005286,1005287,1005298`.
* CCD 27 of the `DECaPS East` field shows a moving object within the FoV, so at times this affects the photometry of known objects. The full path of the object has not been determined yet, therefore it is possible that other CCDs are affected as well.
* There was a problem with the pointing for the `eta_car` field, so a few images have a different pointing and were compressed in a different file (containing `bad` in its filename for the bad pointing).
* The `DECaPS East` field is really crowded, so crossmatches between different images of the same band should be done with care. We have found that `0.5` arcseconds usually works well.
