Masters Project: Machine Learning For Optimisation of Laser Physics Experiments


Investigations and tests into the use of the Gaussian Process provided by M-LOOP: M. R. Hush, https://m-loop.readthedocs.io/en/ latest/api/mloop.html (2016). The action of this algorithm in a given simulated experiment was compared with a standard Nelder-Mead algorithm. 

Over the course of a year, various types of simulated experiments were created and M-LOOP was interfaced with these. The final form of the experiment attempted to replicate a 'walking the beam' experiment. Due to the inability to go into a lab (as a result fo the Covid-19 pandemic 2020-2021), a simulation was made in which a beam is reflected by two mirrors onto a detector. Each mirror has two degrees of freedom, corresponding to pitch and yaw (tilting up/down and left/right). With two mirrors, this gave four degrees of freedom. By changing the mirror angles, the final position of the beam changes. The aim was to find the correct angles for the mirrors such that the beam would pass through a filter, and then hit the detector. 

This synthetic experiment was then interfaced with M-LOOP. M-LOOP was then used to control the optimal mirror angles in order to minimise a given cost, and thus align the beam in the most efficient way. A Gaussian process regression algorithm (trained by a differential evolution algorithm) was used and then compared with the simplex-based Nelder-Mead algorithm. 

Importantly in the experiment, one can set the size of the boundaries of mirror angles for the algorithms to test. A larger boundary is advantageous in a real life experimental setting, as it means that less time has to be spent with manual testing to find an initial approximate value for each parameter. It was concluded that the Gaussian process was more versatile than the Nelder-Mead algorithm in this way (with the Nelder-Mead falling into local minima in the cost landscape when the parameter boundaries were too large). However, if one starts with more suitable initial boundaries (such that the Nelder-Mead algorithm does not fall into local minima), then the Nelder-Mead is able to converge within fewer runs (and therefore faster) to the optimal parameter settings than the Gaussian process. Both algorithms outperformed the differential evolution algorithm, which was slow to converge, and hence, only used to train the Gaussian process algorithm. 

Future work relating to this report would involve combining the current form of the experiment, with code which allows for the plotting of individual photons (included above). In this way, the vector used as the 'beam' in the original experiment could be used to specify the centre (mean in x and y dimensions) of the distribution of photons which hit the detector. In such a way, one could then investigate the effect that Poisson (shot) noise has on the efficacy of the algorithms. 

