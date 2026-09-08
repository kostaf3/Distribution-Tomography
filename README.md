# 3D Tomographic Reconstruction of Photoelectron Angular Distributions

This project was developed as part of my M.Sc. thesis in Physics at the University of Ioannina.

It implements a Mathematica-based computational workflow for simulating two-dimensional detector projections of a theoretical three-dimensional photoelectron angular distribution and reconstructing the original distribution using tomography.

The project was developed in the context of atomic photoionization experiments using Velocity Map Imaging (VMI), where a detector records 2D projections of the underlying 3D photoelectron momentum distribution.

## Project Overview

The project consists of two Mathematica applications:

1. **Photoelectron Simulation and Projection** — generates simulated 2D detector projections from a theoretical 3D photoelectron angular distribution at different rotation angles.

2. **Tomographic Reconstruction** — imports the generated projections and reconstructs the underlying 3D distribution using tomographic methods.

### Computational Workflow

Theoretical 3D distribution  
↓  
Simulation at different rotation angles  
↓  
2D detector projections  
↓  
Tomographic reconstruction  
↓  
Recovered 3D distribution  
↓  
Validation and comparison

## Simulation and Projection

The simulation is implemented in:

`notebooks/photoelectron_simulation_and_projection.nb`

The application takes an analytical expression describing the photoelectron angular distribution in spherical coordinates.

The user can configure the angular distribution, light-polarization parameters, number of projections, and other simulation parameters.

The distribution is rotated through a sequence of angles and numerical integration is used to calculate the corresponding 2D detector projections.

The generated projections are then exported as `.dat` files for use by the reconstruction application.

## Tomographic Reconstruction

The reconstruction is implemented in:

`notebooks/tomographic_reconstruction.nb`

The application imports a sequence of simulated detector projections and organizes the projection data for tomographic reconstruction.

Individual slices are reconstructed using Mathematica's inverse Radon transformation and are combined to recover the three-dimensional distribution.

The application also provides controls for data orientation and masking of the reconstructed distribution.

## Validation

The reconstruction method was evaluated using theoretical photoelectron angular distributions for which the original 3D distribution was known.

For linear light polarization, the tomographic reconstruction was compared with the inverse Abel transform.

The method was also tested for circular and elliptical polarization, where the symmetry requirements of the inverse Abel approach restrict its applicability.

To investigate robustness under non-ideal experimental conditions, noise was introduced into the simulated projections. The reconstruction was tested with noise levels up to 5% of the maximum signal.

## Example Results

### Theoretical 3D Distribution

![Theoretical 3D photoelectron distribution](examples/3d theoretical distribution linear.jpg)

### Simulated Detector Projection

![Simulated detector projection](examples/simulated_projection_linear.png)

### Reconstructed Slice

![Tomographically reconstructed slice](examples/reconstructed_slice_linear.png)

## Technologies and Methods

- Wolfram Mathematica
- Physics-based numerical simulation
- Numerical integration
- Tomographic reconstruction
- Inverse Radon transformation
- Inverse Abel transform
- Scientific data visualization
- Noise and robustness analysis

## Running the Project

### Requirements

- Wolfram Mathematica

### Generate the projections

1. Open `notebooks/photoelectron_simulation_and_projection.nb`.
2. Define the desired angular distribution.
3. Set the polarization and tomography parameters.
4. Run the simulation.
5. The calculated projections are displayed and exported as `.dat` files.

### Reconstruct the distribution

1. Open `notebooks/tomographic_reconstruction.nb`.
2. Import the generated `.dat` projection files.
3. Select the required reconstruction parameters.
4. Run the reconstruction.
5. The reconstructed distribution is displayed by the application.

## Author

**Konstantinos Filippou**  
M.Sc. Physics, University of Ioannina
