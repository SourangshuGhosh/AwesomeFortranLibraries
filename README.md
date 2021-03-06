# AwesomeFortranLibraries

This is a collection of Fortran routines I have written over the years for use in more complex codes. The different files are as independent as possible from each other, but in some cases dependencies are unavoidable.

A lot of routines are written so as to work with both single and double type precision. These are in the templates/ directory, and are coded using generic types. The files in templates are not valid Fortran, and will not compile. Running the parse.py script automatically generates the full source code from these templates, and places the results in src.

## Author:

Sourangshu Ghosh

## base_types.f90 (no dependencies)
  Defines numeric types
  
## lib_algebra.f90 (no dependencies)
### Defines the following routines:
    - cube root
    - several quadratic solvers
    - Simpson's rule integrator
    - Gaussian elimination linear equations solver

## lib_array.f90 (no dependencies)
### Defines the following routines:
    - linspace: create an array of values equally spaced in linear space
    - logspace: create an array of values equally spaced in log space
    - index_array_1d: find the order array elements should be in to be sorted
    - sort: sort one or two arrays
    - integral: trapezium integration
    - integral_linlog: trapezium integration with linear-log interpolation
    - integral_loglin: trapezium integration with log-linear interpolation
    - integral_loglog: trapezium integration with log-log interpolation
    - cumulative_integral: cumulative version of integral
    - cumulative_integral_linlog: cumulative version of integral_linlog
    - cumulative_integral_loglin: cumulative version of integral_loglin
    - cumulative_integral_loglog: cumulative version of integral_loglog
    - locate: search for a value in a sorted array
    - interp1d: 1-D linear interpolation
    - interp2d: 2-D linear interpolation
    - interp1d_linlog: 1-D linear interpolation in linear-log space
    - interp1d_loglin: 1-D linear interpolation in log-linear space
    - interp1d_loglog: 1-D linear interpolation in log-log space
    - histogram1d: convert an array of values to a histogram
    - histogram2d: convert two arrays of values to a 2-D histogram
    - ipos: bin value for equally spaced bins
    - xval: find center of bin for equally spaced bins
    
## lib_cfitsio.f90 (requires the cfitsio library to be installed)
  Defines wrapper routines for the cfitsio library
  
## lib_conf.f90 (no dependencies)
  Defines routines to make it easy to read Apache-style configuration files
  
## lib_constants.f90 (no dependencies)
  Defines some physical constants in SI and CGS units
  
## lib_hdf5.f90 (requires the HDF5 library to be installed)
  Defines wrapper routines for the HDF5 library
  
## lib_io.f90 (requires the posix_*.f90 modules - see below)
  Defines various I/O operations (file deletion with confirmation, etc.)

## lib_messages.f90
  Defines warning/error routines
  
## lib_random.f90
### Defines routines to sample random numbers:
    - uniform random numbers between 0 and 1
    - uniform random numbers between two bounds
    - random number from exp(-x) PDF
    - random number from a normal distribution
    - random position on a sphere
    - random Poisson variables
    - random frequency from a Planck function

## posix_default.f90 and posix_nag.f90
  Define various low-level routines, such as checking for file/directory
  existence, and a routine to sleep a program for an amount of time defined in
  microseconds. If using the NAG f95 compiler, use posix_nag.f90, otherwise
  use posix_default.f90
  
## type_angle3d.f90 (requires lib_random.f90)
  Defines a derived type for 3D angles, and associated routines
  
## type_pdf.f90 (requires lib_array.f90 and lib_random.f90)
  Defines derived types for discrete and continuous PDFs, and associated routines (including for sampling the PDFs).

## type_stokes.f90
  Defines a derived type for Stokes vectors, and associated routines
  
## type_vector3d.f90 (requires lib_random.f90 and type_angle3d.f90)
  Defines a derived type for 3D vectors, and associated routines


