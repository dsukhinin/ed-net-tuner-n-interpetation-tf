# Envelope Detector net: hyperparams tuner and wights interpretation

This repository is Tensorflow reimplementation of small and interpretable deep neural network Envelope Detector-net(ED-net) that is used in brain decoding experiments, initially developed in [Petrosyan et al. 2021](#petrosyan2021) for motor BCI and studied in depth in [Petrosyan et al. 2022](#petrosyan2022).
Here wrapped inside Keras tuner to search for 4 main parameters and aaditionaly contains functions for weights interpretation. 



## Dependencies
```sh
pip install -r requirements.txt
```


## Usage 
Edit config.json. 
And follow hyper_ed_net_tuner.ipynb for use case.

Data files format:

- x_file -  (b,t,c)  b - n train samples, t - time step, с -n channels
- y_file - (b,a) where b - n train samples, a - class (int from 0 to n_classes-1)

Tuner main params: 
- n_trials - should be big enough to cover search space (for example, in case we want to tune 4 params with 4 possible values each, then  n_trials=4*4=16) 
- n_runs_per_trial - should be around 3-5
<br/>
Next select params to tune and set the boundaries by modifying:   _param_min | max | step 
 

## References
<a id="petrosyan2021">[1]
@article{petrosyan2021,
  title={Decoding and interpreting cortical signals with a compact convolutional neural network},
  author={Petrosyan, Artur and Sinkin, Mikhail and Lebedev, Mikhail and Ossadtchi, Alexei},
  journal={Journal of Neural Engineering},
  volume={18},
  number={2},
  pages={026019},
  year={2021},
  publisher={IOP Publishing}
}
 </a> 
 <br/>
<a id="petrosyan2022">[2]
@article{petrosyan2022,
doi = {10.1088/1741-2552/aca1e1},
url = {https://dx.doi.org/10.1088/1741-2552/aca1e1},
year = {2022},
month = {nov},
publisher = {IOP Publishing},
volume = {19},
number = {6},
pages = {066016},
author = {Artur Petrosyan and Alexey Voskoboinikov and Dmitrii Sukhinin and Anna Makarova and Anastasia Skalnaya and Nastasia Arkhipova and Mikhail Sinkin and Alexei Ossadtchi},
title = {Speech decoding from a small set of spatially segregated minimally invasive intracranial EEG electrodes with a compact and interpretable neural network},
journal = {Journal of Neural Engineering}
}
 </a> 
