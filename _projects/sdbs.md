---
layout: page
title: PhD - Hot sdB stars
description: Formation channels
img: assets/img/sdbs.png
importance: 2
category: Work
---

Hot sub-dwarf stars of spectroscopic B class (sdB) are core helium burning stars located at the blue end of the horizontal branch in the Hertzsprung-Russell diagram (see e.g. <a href="https://ui.adsabs.harvard.edu/abs/2009ARA%26A..47..211H/abstract">Heber, 2009</a>). Amongst them, some present pulsations, which makes them important sources for asteroseismology. Similarly, it is theorized that sdBs may play a role in <a href="https://www.oxfordreference.com/display/10.1093/oi/authority.20110803095407472">AM CVn</a> systems (which are expected gravitational wave sources) as the donor could become an sdB during its evolution. Finally, they are proposed as progenitors of the rare and recently discovered blue large amplitude pulsator (BLAP, <a href="https://www.nature.com/articles/s41550-017-0166">Pietrukowicz et al., 2017</a>) class of variable stars. However, one of the most puzzling points of sdB stars is their origin. Scenarios proposed include both single and binary evolution, with the latter being widely accepted as the most likely formation path, considering observational constraints such as the period distribution of observed binaries where a member is an sdB star. This, in turn, makes them valuable for the study of interacting binary stars, as sdBs are thought to be formed thanks to <a href="https://www.oxfordreference.com/display/10.1093/oi/authority.20110803095627543">common envelope</a>, stable <a href="https://www.oxfordreference.com/display/10.1093/oi/authority.20110803100139245">mass transfer</a> or a combination of these episodes.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% responsive_image path: assets/img/sdbs.png title: "Evolution paths" class: "img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Taken from <a href="https://ui.adsabs.harvard.edu/abs/2008ASPC..392...15P/abstract">Podsiadlowski et al. 2008</a>. Three of the main formation scenarios are shown. Note that both the process and final results are different in each case.
</div>

My research involves analyzing the formation of sdBs by using a rapid binary population synthesis code, <a href="https://github.com/TeamCOMPAS/COMPAS">COMPAS</a> (of which <a href="https://solfreludio.github.io/projects/compas/">I'm also a developer of</a>). Changing the initial parameters of the simulated population allows me to evaluate the impact of these on the total number of sdB-like stars produced, as well as the relative numbers between different formation pathways. While these numbers are not an exact prediction of what we would expect in nature, they are understood as the likelihood of a certain number of evolution scenarios under a given initial configuration. 

One of the most recent developments in my research is the possibility to ignite helium before reaching the expected core mass at ignition during the canonical helium flash, which has been explored in previous works (see <a href="https://ui.adsabs.harvard.edu/abs/1996ApJ...466..359D/abstract">D'Cruz et al. 1996</a> and <a href="https://ui.adsabs.harvard.edu/abs/2002MNRAS.336..449H/abstract">Han et al. 2002</a>). I have revisited this problem with simulations in <a href="https://docs.mesastar.org/en/release-r22.11.1/">Modules for Experiments in Stellar Astrophysics (MESA)</a>. Different approaches give different numbers for the final amount of sdB candidates, although it is clear that some empirical results are only recovered if the ignition below canonical helium flash core mass is allowed. No other variation of the parameters (within the explored configurations) creates a similar effect (e.g. <a href="https://ui.adsabs.harvard.edu/abs/2012ApJ...746..186C/abstract">Clausen et al. 2012</a>).
