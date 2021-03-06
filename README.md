#  Empirical Wavelet Transform Python package

Original paper: 
Gilles, J., 2013. Empirical Wavelet Transform. IEEE Transactions on Signal Processing, 61(16), pp.3999–4010. 
Available at: http://ieeexplore.ieee.org/lpdocs/epic03/wrapper.htm?arnumber=6522142.  
Original Matlab toolbox: https://www.mathworks.com/matlabcentral/fileexchange/42141-empirical-wavelet-transforms

ewtpy performs the Empirical Wavelet Transform of a 1D signal over N scales. Main function is EWT1D:

ewt,  mfb ,boundaries = EWT1D(f, N = 5, log = 0,detect = "locmax", completion = 0, reg = 'average', lengthFilter = 10,sigmaFilter = 5)  
Other functions include:  
EWT_Boundaries_Detect  
EWT_Boundaries_Completion  
EWT_Meyer_FilterBank  
EWT_beta  
EWT_Meyer_Wavelet  
LocalMax  
LocalMaxMin  

Some functionalities from J.Gilles' MATLAB toolbox have not been implemented, such as EWT of 2D inputs, preprocessing, adaptive/ScaleSpace boundaries_detect.

The Example folder contains test signals and scripts

## Installation 

1) Dowload the project from https://github.com/vrcarva/ewtpy, then run "python setup.py install" from the project folder

OR

2) pip install ewtpy


## Citation and Contact
Preprint available at: https://doi.org/10.1101/691055

If you find this package useful, we kindly ask you to cite it in your work.   
Evaluating three different adaptive decomposition methods for EEG signal seizure detection and classification
Vinícius Rezende Carvalho, Márcio F.D. Moraes, Antônio Pádua Braga, Eduardo M.A.M. Mendes
bioRxiv 691055; doi: https://doi.org/10.1101/691055

The final paper will soon be submitted and linked here.  

If you developed a new funcionality or fixed anything in the code, just provide me the corresponding files and which credit should I include in this readme file. 

@author: Vinícius Rezende Carvalho
Programa de pós graduação em engenharia elétrica - PPGEE UFMG
Universidade Federal de Minas Gerais - Belo Horizonte, Brazil
Núcleo de Neurociências - NNC 

Any questions, comments, suggestions and/or corrections, please get in contact with vrcarva@ufmg.br

## Example script
```python
#%% Example script
import numpy as np
import matplotlib.pyplot as plt
import ewtpy

T = 1000
t = np.arange(1,T+1)/T
f = np.cos(2*np.pi*0.8*t) + 2*np.cos(2*np.pi*10*t)+0.8*np.cos(2*np.pi*100*t)
ewt,  mfb ,boundaries = ewtpy.EWT1D(f, N = 3)
plt.plot(f)
plt.plot(ewt)
```






