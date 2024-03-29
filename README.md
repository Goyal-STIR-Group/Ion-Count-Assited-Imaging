# Ion-Count-Assited-Microscopy
Codebase for creating and analyzing ICAM images, as reported in the manuscript "Shot noise-mitigated secondary electron imaging with ion count-aided microscopy". A preprint versopm of the manuscript is available at https://arxiv.org/abs/2311.07003. 

Authors: Akshay Agarwal, Xinglin He

DOI for this repo: <a href="https://zenodo.org/doi/10.5281/zenodo.10535998"><img src="https://zenodo.org/badge/745682353.svg" alt="DOI"></a>

The codebase consists of 4 MATLAB scripts. These scripts were written and verified in MATLAB R2022a. 

The main script, image_code_main.m, reads each of the 4 datasets for one image sequentially and extracts complete image frames from them. The helper function extraction.m picks out the start of complete image frames in each dataset. image_code_main.m uses these frames to create both the conventional and ICAM images by implementing the estimators described in the manuscript. The helper function peakfinder5.m (modified from peakfinder.m available through the Matlab File Exchange) finds the peaks of pulses in the SE detector scan waveform, which facilitates the implementation of imaging estimators. image_code_main.m also analyzes the MSE, signal to noise ratio and Fourier-ring-correlation (FRC) resolution of each image. interX.m is a helper function (downloaded from the Matlab File Exchange) to find intersection point of 2 curves. It is used in the FRC resolution computation. Any number of frames (up to 16) can be used to create the final image. The analysis in figures 2, 3, and 4 of the manuscript was performed by using different numbers of image frames to vary the effective imaging dose, as detailed in image_code_main.m.
