# Blind challenge in LSS

Find the cosmology of blinded simulated LSS data!

## Preliminaries
Clone [PyBird](https://github.com/pierrexyz/pybird), switch to dev branch, and install it:
```
git clone https://github.com/pierrexyz/pybird.git
cd pybird
git checkout dev
pip install .
```

For the challenge, it is strongly recommended to install the following packages: 
* **[CLASS](https://lesgourg.github.io/class_public/class.html)**
* **[iminuit](https://iminuit.readthedocs.io/)** 
* **[emcee](https://emcee.readthedocs.io/)**
* (optional) **[MontePython 3](https://github.com/brinckmann/montepython_public)**

More information can be found in [PyBird README](https://github.com/pierrexyz/pybird/blob/master/README.md). 

## 23/12 USTC

Here are two fake data which are multipoles ($\ell=0,2,4$) of the power spectrum of galaxies in redshift space created using EFTofLSS predictions at one loop. 

ustc_1_2pt: the cosmology is: $\omega_b=0.02235, \omega_{\rm cdm}=0.120, h=0.675, \ln(10^{10}A_s=3.044, n_s=0.695$, and no massive neutrino. Find the truth of the EFT parameters $b_1, c_2, b_3, c_{ct}, c_{r,1}, c_{r,2}, c_{e,0}, cc_{e,2}$.

ustc_2_2pt: the cosmology is: $\omega_b=0.02235, n_s=0.695$, and no massive neutrino. Find the truth of $\Omega_m, h, \sigma_8$. 

For all data:
* $z=1, k_{nl}=k_{m}=0.5 \ h/Mpc, k_{r}=0.3 \ h/Mpc, \bar n=5e-3 \ (Mpc/h)^3$
* West-Coast parametrization (`'eft_basis': 'weastcoast'`): $c_{4} = (b_2 - b_4)/\sqrt{2} \equiv 0, c_{e,1} \equiv 0$
* No observational modeling (no AP effect, no survey mask) except linear binning (`'with_binning': True`): $\Delta k = 0.01 \ h/Mpc$)
* Covariance (provided) is about DESI volume $V \sim 3 \cdot 10^{10} \ [Mpc/h]^3$

A good place to start is [here](https://github.com/pierrexyz/pybird/blob/dev/notebooks/likelihood.ipynb). 

Good luck!

