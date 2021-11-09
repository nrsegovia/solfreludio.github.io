---
layout: page
title: Period Change Rates
description: Analysis of period change rates in Large Magellanic Cloud Classical Cepheids
img: assets/img/12.jpg
importance: 1
category: work
---

This project started back on 2019 as an assignment for the 'Variable Stars' subject dictated by Prof. Marcio Catelan. I participated actively into data acquisition and analysis, which led me to continue the project as part of both 'Experimental Astrophysics' subject and my undergraduate thesis.

A paper has been accepted for publication in MNRAS and the abstract reads as follows:

" The period-change rate (PCR) of pulsating variable stars is a useful probe of changes in their interior structure, and thus of their evolutionary stages. So far, the PCRs of Classical Cepheids in the Large Magellanic Cloud (LMC) have been explored in a limited sample of the total population of these variables. Here we use a template-based method to derive PCRs for these stars, by taking advantage of the long time baseline afforded by the Digital Access to a Sky Century @ Harvard (DASCH) light curves, combined with additional data from the Optical  Gravitational  Lensing  Experiment  (OGLE),  the  MAssive  Compact  Halo  Object  (MACHO)  project, Gaia’s Data Release 2, and in some cases the All-Sky Automated Survey (ASAS). From an initial sample of 2315 sources, our method provides an unprecedented sample of 1303 LMC Classical Cepheids with accurate PCRs, the largest for any single galaxy, including the Milky Way.  Our results include values that are largely compatible with theoretically expected PCRs, as computed by our team using the Modules for Experiments in Stellar Astrophysics (MESA) code, as well as with similar previous computations available in the literature. Additionally, five long-period (P >50 d) sources display a cyclic behavior in their O-C diagrams, which is clearly incompatible with evolutionary changes.  Finally, on the basis of their large positive PCR values, two first-crossing Cepheid candidates are identified."

The following pictures should be updated with O-C diagrams for Cepheids with computed period changes.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% responsive_image path: assets/img/1.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% responsive_image path: assets/img/3.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% responsive_image path: assets/img/5.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% responsive_image path: assets/img/5.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% responsive_image path: assets/img/6.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% responsive_image path: assets/img/11.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% responsive_image path: assets/img/6.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% responsive_image path: assets/img/11.jpg title: "example image" class: "img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
