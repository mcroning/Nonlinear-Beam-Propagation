# Nonlinear Beam Propagation
non paraxial and paraxial beam propagation using FFT or FDBPM

Nonlinear split step optical beam propagation using photorefractive nonlinearities. Othe nonlinearites could be subbed in. The current example is for photorefractive barium titanate. The code can process the mnist or audio mnist libraries to enable testing with optical deep learning image classification methods such as SOLO. (U. Tegin, M. Yildirim, I. Oguz et al., “Scalable optical learning operator,” Nature Computational Science, 1(8), 542-549 (2021)).
This project is inpired by older research in photorefractive beam propagation: M. Cronin-Golomb, “Whole beam method for photorefractive nonlinear optics,” Optics Communications, 89(2-4), 276-282 (1992).

There are three files: 
1) load_prdata.ipynb  :creates dictionary of variables and large common arrays for parallel multicore processing
2) pr_audiodigit_ray_v2.ipynb : notebook to load dictionary, input images (mnist ot mnist audio) and perform beam propagation using ray for parallelization, tested on Apple M1 Pro silicon 
3) variables.docx : description of dictionary variables

Run load_prdata first to set up the problem
Then run pr_audiodigit_ray to
1) load images
2) perform photorefractive two beam coupling with specifed beam angles and waists, coupling constants and noise levels. Optionally apply images to one or both beams

Output includes cross longitidinal cross sections and animations.  The output is back propagated by phase conjugation to allow direct comparison of input and output images
The accuracy of the code can be checked against the analytic propagation of gaussian beams 
