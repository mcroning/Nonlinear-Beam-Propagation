# Nonlinear Beam Propagation
non paraxial and paraxial beam propagation using FFT or FDBPM

Nonlinear split step optical beam propagation using photorefractive nonlinearities. Other nonlinearites could be subbed in. The current example is for photorefractive barium titanate. The code can process the mnist or audio mnist libraries to enable testing with optical deep learning image classification methods such as SOLO. (U. Tegin, M. Yildirim, I. Oguz et al., “Scalable optical learning operator,” Nature Computational Science, 1(8), 542-549 (2021)). Fourier transform and finite difference methods are available in the code.
This project is inpired by older research in photorefractive beam propagation by the FFT split step method: M. Cronin-Golomb, “Whole beam method for photorefractive nonlinear optics,” Optics Communications, 89(2-4), 276-282 (1992). The nonparaxial finite difference method is from "Split step non-paraxial finite difference method for 3D scalar wave propagation" D. Bhattacharya, A. Sharma, Opt Quant Electron (2007) 39:865–876 and "Three-dimensional finite difference split-step nonparaxial beam propagation method:new method for splitting of operators", D. Bhattacharya, A. Sharma, Appl. Opt. 48, 1878-1885 (2009)

There are three files: 
1) load_prdata.ipynb : creates dictionary of variables and large common arrays for parallel multicore processing
2) pr_audiodigit_ray.ipynb : notebook to load dictionary, input images (mnist ot mnist audio) and perform beam propagation using ray for parallelization, tested on Apple M1 Pro silicon 
3) variables.pdf : description of dictionary variables

Run load_prdata first to set up the problem and produce the parameter library file (prdata.mat) with step size, transverse grid spacing, coupling constant etc. prdata.mat can be loaded into Matlab for inspection.

Then run pr_audiodigit_ray to
1) load images from the public mnist digits or audio databases
2) perform photorefractive two beam coupling with specifed beam angles and waists, coupling constants and noise levels. Two calculation methods are available: FFT and Finite Difference. Optionally apply images to one or both beams

Output includes longitidinal cross sections and animations.  The output is back propagated by phase conjugation to allow direct comparison of input and output images
The accuracy of the code can be checked against the analytic propagation of gaussian beams 
