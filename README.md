# OVERVIEW

The ILATM1B-reader MATLAB package provides a function to read binary
IceBridge ATM data files. The function returns a floating point array
and text header values from a given ATM granule file.

This Matlab function calls the C program qi2txt which reads
binary data files from the Operation IceBridge ATM
instrument. readILATM1B.m returns a data array containing the
floating-point ATM data as well as an ASCII header line identifying
each of the 12 fields comprising each ATM data record. Operation
IceBridge ATM data are available as the ILATM1B product at the
National Snow and Ice Data Center (NSIDC), at

http://nsidc.org/data/ilatm1b.html

Both the readILATM1B.m software and its required 

## Getting Started

### Prerequisites

* [MATLAB v9.0 or greater](https://www.mathworks.com/products/matlab.html)
* [The IceBridge ATM qfit reader](ftp://sidads.colorado.edu/pub/tools/icebridge/qfit/c/qi2txt_v0.5.zip)

### Installing

#### Option 1: From a release

#. Select a [release of the
ILATM1B-reader](https://github.com/kbeamnsidc/ILATM1B-reader/releases)
and download the desired release.

#. Unpack the tar file. At a command prompt:

        $ tar xvf matlab_ILATM1B_reader_VERSION.tar

#### Option 2: From GitHub

Clone this GitHub repository on your local machine:

    $ git clone https://github.com/kbeamnsidc/ILATM1B-reader.git

#### Configure MATLAB

Add the reader path: either edit the Matlab start-up script, or use
the function addpath at the Matlab command line.

#### Verify Install

At the MATLAB command prompt:

    >> help readILATM1B
    >> help test_readILATM1B

Both commands should show help documentation about the functions.

### Reading ILATM1B data

USING THE SOFTWARE
 
function [data, header] = readILATM1B(filename_url, qi2txt_dir)
 
  Reads the Qfit ILATM1B data into matlab; wrapper on the C version.
  ILATM1B Airborne Topographic Mapper (ATM) Project
  NASA, Goddard Space Flight Center, Wallops Flight Facility
  Principal Investigator: Bill Krabill (William.B.Krabill@nasa.gov)
 --------------------------------------------------------------------------
  USAGE:
  [data, header] = readILATM1B(filename_url, qi2txt_dir);
 
  RETURN VALUES: 
  data - ILATM1B data.
  NOTE: the C version qfit reader qi2txt called by this function returns data: 
   1    Relative Time (seconds from start of the file)
   2    Laser Spot Latitude (decimal degrees)
   3    Laser Spot Longitude (decimal degrees)
   4    Elevation (meters)
   5    Start Pulse signal Strength (relative integer) 
   6    Reflected Laser Signal Strength (relative integer)
   7    Scan Azimuth (degrees)
   8    Pitch (degrees)
   9    Roll (degrees)
  10    GPS PDOP (dilution of precision) 
  11    Laser received pulse width (digitizer samples)
  12    GPS Time (seconds)
 
  header - ILATM1B ASCII header line produced by qi2txt.
 
  ARGUMENTS:
  filename_url - ILATM1B Qfit input data file URL.
  qi2txt_dir - directory containing qi2txt C program executable.
 
  PATHS:
  code:
  http://nsidc.org/data/icebridge/tools.html
 
  code was tested on IceBridge FTP data file:
  ftp://n5eil01u.ecs.nsidc.org/SAN2/ICEBRIDGE/ILATM1B.001/2010.04.05/ILATM1B_20100405_141754.atm4cT3.qi
 --------------------------------------------------------------------------
  National Snow and Ice Data Center, Susan Rogers, March 16, 2011
  Copyright (c) 2011 Regents of the University of Colorado.

TODO:

test_readILATM1B.m
  Matlab test program that serves as an example of how to call
  readILATM1B.m.

## Contributing

To report a bug, or suggest an improvement or enhancement, please open
a [GitHub
Issue](https://github.com/kbeamnsidc/ILATM1B-reader/issues). [Pull
Requests](https://github.com/kbeamnsidc/ILATM1B-reader/pulls)
(preferably on an open issue) are also accepted on this repository.

## Versioning

This project follows the [Semantic Versioning](https://semver.org/)
rules.

## Authors

Susan Rogers, National Snow and Ice Data Center

## License

This software is licensed under the MIT License.

Copyright (c) 2018 National Snow and Ice Data Cente (NSIDC)

DISCLAIMER

This software is provided as-is as a service to the user community in
the hope that it will be useful, but without any warranty of fitness
for any particular purpose or correctness.  Bug reports, comments, and
suggestions for improvement are welcome; please send to
nsidc@nsidc.org.

## Acknowledgements

ILATM1B Airborne Topographic Mapper (ATM) Project
NASA, Goddard Space Flight Center, Wallops Flight Facility
Principal Investigator: [Bill Krabill](William.B.Krabill@nasa.gov)

This software was developed by the IceBridge Group under NASA-DAAC 
Contract.
