# Monte Carlo integration of the Mandelbrot
In this repository the area of the Mandelbrot set has been estimated using four different sampling techniques.

## Mandelbrot set plot
Firstly the mandelbrot set has been plotted for which the mandelbrot series went to 100 iterations and shows also zoomed parts of it in certain regions.

## Monte Carlo Sampling


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
The code supports parralism with CUDA. However, when CUDA is not available, delete "the import cupy as cp" line and change every "cp" to "np". However, removing this causes the runtime to be extended significantly. Recommended to reduce the iteration and sample sizes if not using CUDA. 

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
