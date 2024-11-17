# Monte Carlo integration of the Mandelbrot
In this repository the area of the Mandelbrot set has been estimated using Motne Carlo integration. First the Mandelbrot set is plotted and then the mandelbrot will be integrated using Monte Carlo.
## Mandelbrot set plot
Firstly the mandelbrot set has been plotted for which the mandelbrot series went to 100 iterations and shows also zoomed parts of it in certain regions. This is just for visualization of the Mandelbrot set and the plots are not used for the Monte Carlo sampling.

## Monte Carlo Sampling
The area of the mandelbrot set is estimated. To estimate the area more accurately and to not everestimate the area, the mandelbrot serie is now allowed to go up to 1000 iterations to check for divergence instead of 100. This thus increase computational time and can be reduced for less accurate estimations.

### Sampling techniques
The four techniques are:
  1. Uniform random sampling
  2. Latin Hypercube sampling
  3. Orthogonal sampling
  4. Sobol sampling.

### Sample sizes and iterations
These sampling techniques were used for different sample sizes. These sample sizes were repeated for a number iteration.
Orthogonal sampling requires that the sample sizes to be a square of a prime number and sobol sampling requires the the sample sizes to be a power of 2. Uniform random and latin hypercube sampling uses the orthogonal sampling sizes to make it more compareble to that. 

### Parallelism with CUDA note
The code supports parralism with CUDA. However, when CUDA is not available, delete "the import cupy as cp" line and change every "cp" to "np". However, using numpy over cupy will caus the runtime to be extended significantly. It is recommended to reduce the iteration, sample sizes and/or the max_length_set if not using CUDA. 

## Dependencies
The packages and their version used for this project are:
  * python      3.12
  * ipykernel   6.29.5
  * matplotlib  3.9.2
  * numpy       1.26.4
  * pandas      2.0.3
  * scipy       1.13.1
  * cuda        12.x
### optional dependency when having acces to CUDA
  * cupy        13.3.0
