<img src="nsidc.jpg" alt="NSIDC logo" style="width=225px">
<img src="icebridge_logo.png" alt="IceBridge logo" style="width=225px">

# OVERVIEW

The ILATM1B MATLAB package provides a function to read binary
IceBridge ATM data files.

This MATLAB function calls the program qi2txt which reads binary data
files from the Operation IceBridge ATM instrument. The readILATM1B
function then returns a data array containing the floating-point ATM
data as well as an ASCII header line identifying each of the 12 fields
comprising each ATM data record. Operation IceBridge ATM data are
available as the [ILATM1B product](http://nsidc.org/data/ilatm1b.html)
at the National Snow and Ice Data Center (NSIDC).

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
the function `addpath` at the Matlab command line. E.g., if the
package was extracted to `/home/users/janedoe/ILATM1B-reader`, then at
the MATLAB command line we would run:

    >> addpath /home/users/janedoe/ILATM1B-reader

#### Verify Install

At the MATLAB command prompt:

    >> help ilatm1b

This will show the contents of the MATLAB package, and these commands
will show help on the two functions provided in the package:

    >> help ilatm1b.read
    >> help ilatm1b.test_read

If these commands are unable to find the ilatm1b package, check your
installation directory and the MATLAB `path` directory.

### Reading ILATM1B data

At the MATLAB command prompt:

    >> filename_url = 'ftp://n5eil01u.ecs.nsidc.org/SAN2/ICEBRIDGE/ILATM1B.001/2010.04.05/ILATM1B_20100405_141754.atm4cT3.qi';
    >> qi2txt_dir = '.';
    >> [data, header] = ilatm1b.read(filename_url, qi2txt_dir);

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

Copyright (c) 2018 National Snow and Ice Data Center (NSIDC)

DISCLAIMER

This software is provided as-is as a service to the user community in
the hope that it will be useful, but without any warranty of fitness
for any particular purpose or correctness.  Bug reports, comments, and
suggestions for improvement are welcome; please send to
nsidc@nsidc.org.

## Acknowledgements

* ILATM1B Airborne Topographic Mapper (ATM) Project
* NASA, Goddard Space Flight Center, Wallops Flight Facility
* Principal Investigator: [Bill Krabill](William.B.Krabill@nasa.gov)

This software was developed by the IceBridge Group under NASA-DAAC 
Contract.
