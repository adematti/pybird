[![](https://img.shields.io/badge/arXiv-2003.07956%20-red.svg)](https://arxiv.org/abs/2003.07956)
[![](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/pierrexyz/pybird/blob/master/LICENSE)
[![](https://readthedocs.org/projects/pybird/badge/?version=latest)](https://pybird.readthedocs.io/en/latest/?badge=latest)

# PyBird: Python code for Biased tracers in redshift space
* Written by [Pierre Zhang](mailto:pierrexyz@protonmail.com) and [Guido D'Amico](mailto:damico.guido@gmail.com)
* License: MIT

## General info
PyBird is a fast code written in Python 3 computing EFT predictions for correlators of biased tracers in redshift space. 

Currently available: 
> one-loop predictions for two-point (2pt) functions: dark matter or biased tracers, real or redshift space, Fourier (power spectrum) or configuration space (correlation function).  

> includes additional modelling: geometrical (AP) distortion, survey mask, binning, exact-time dependence, and more. 

PyBird also provides likelihoods interfacing the EFT predictions with galaxy-clustering data. 

Currently available: 
> [BOSS DR12 LRG 2pt full-shape + rec. bao](https://github.com/pierrexyz/pybird/montepython/likelihoods/eftboss)

Soon available: 
> [eBOSS DR16 QSO 2pt full-shape]

## Dependencies
PyBird depends on the numerical libraries [NumPy](https://numpy.org/) and [SciPy](http://scipy.org/).  

The following packages are not strictly neccessary but recommended to run the cookbooks:
* PyBird has extra compatibility with **[CLASS](https://lesgourg.github.io/class_public/class.html)**.  
* PyBird likelihoods are integrated within **[MontePython 3](https://github.com/brinckmann/montepython_public)**. 
* PyBird likelihoods are showcased with **[iminuit](https://iminuit.readthedocs.io/)** and **[emcee](https://emcee.readthedocs.io/)**. 

## Installation
PyBird is pip-installable.
Just clone the repo, and install it as a Python package in development mode so your changes will be immediately available:
```
git clone https://github.com/pierrexyz/pybird.git
pip install --editable pybird --upgrade
```
That's it, now you can simply `import pybird` from wherever in your projects.

## Getting Started -- likelihood
If you are a **[MontePython 3](https://github.com/brinckmann/montepython_public)** user, likelihoods can be installed 'with less than a cup of coffee'.
* Download and install pybird as above
* Copy the likelihood folder [eftboss](montepython/likelihoods/eftboss) to your working MontePython repository: montepython_public/montepython/likelihoods/ 
* Copy the data folder [pybird/data/eftboss](https://github.com/pierrexyz/pybird/data/eftboss) to your working MontePython data folder: montepython_public/data/
* Try to run the likelihood of BOSS DR12 with the input param file [pybird/montepython/eftboss.param](https://github.com/pierrexyz/pybird/montepython/eftboss.param)

*** Note (23/03/08): the last MontePython version 3.5 seems to have some incompatibilities with the PyBird likelihood related to function `data.need_cosmo_arguments()`. To resolve it, see this [pull-request](https://github.com/brinckmann/montepython_public/pull/276). 

That's it, you are all set!

## Cookbooks
Alternatively, if you are curious, here are three cookbooks that should answer the following questions: 
* [Correlator](https://github.com/pierrexyz/pybird/notebooks/correlator_cookbook.ipynb): How to ask PyBird to compute EFT predictions? 
* [Likelihood](https://github.com/pierrexyz/pybird/notebooks/likelihood_cookbook.ipynb): How does the PyBird likelihood work? 
* [Data](https://github.com/pierrexyz/pybird/notebooks/data_cookbook.ipynb): What are the data read by PyBird likelihood?
* [cbird](https://github.com/pierrexyz/pybird/notebooks/cbird.nb): What is the algebra of the EFT predictions PyBird is based on?

## Documentation
Read the docs at [https://pybird.readthedocs.io](https://pybird.readthedocs.io).

## Citation
When using PyBird in a publication, please acknowledge the code by citing the following paper: 
> G. D’Amico, L. Senatore and P. Zhang, "Limits on wCDM from the EFTofLSS with the PyBird code", JCAP 01 (2021) 006, [2003.07956](https://arxiv.org/abs/2003.07956)

The BibTeX entry for it is:
```
@article{DAmico:2020kxu,
    author = "D'Amico, Guido and Senatore, Leonardo and Zhang, Pierre",
    title = "{Limits on $w$CDM from the EFTofLSS with the PyBird code}",
    eprint = "2003.07956",
    archivePrefix = "arXiv",
    primaryClass = "astro-ph.CO",
    doi = "10.1088/1475-7516/2021/01/006",
    journal = "JCAP",
    volume = "01",
    pages = "006",
    year = "2021"
}
```

Similarly, when using likelihoods, we would be grateful if you can cite the following papers. 

* When using the likelihood based on BOSS DR12 data, to acknowledge the data: 
> BOSS collaboration, S. Alam et al., "The clustering of galaxies in the completed SDSS-III Baryon Oscillation Spectroscopic Survey: cosmological analysis of the DR12 galaxy sample", Mon. Not. Roy. Astron. Soc. 470 (2017) 2617–2652, [1607.03155](https://arxiv.org/abs/1607.03155).


* When using the likelihood of BOSS DR12 LRG power spectrum, to acknowledge the power spectrum measurements: 
> G. D’Amico, Y. Donath, M. Lewandowski, L. Senatore and P. Zhang, "The BOSS bispectrum analysis at one loop from the Effective Field Theory of Large-Scale Structure", [2206.08327](https://arxiv.org/abs/2206.08327). 

* When using the likelihood of BOSS DR12 LRG correlation function, to acknowledge the correlation function measurements: 
> P. Zhang, G. D’Amico, L. Senatore, C. Zhao and Y. Cai, "BOSS Correlation Function analysis from the Effective Field Theory of Large-Scale Structure", JCAP 02 (2022) 036, [2110.07539](https://arxiv.org/abs/2110.07539). 

* When using the likelihood of BOSS DR12 LRG rec. bao, to acknowledge the post-reconstructed measurements: 
> H. Gil-Marín et al., "The clustering of galaxies in the SDSS-III Baryon Oscillation Spectroscopic Survey: BAO measurement from the LOS-dependent power spectrum of DR12 BOSS galaxies", Mon. Not. Roy. Astron. Soc. 460 (2016) 4210–4219, [1509.06373](https://arxiv.org/abs/1509.06373). 
