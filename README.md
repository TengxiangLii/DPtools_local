# DPtools_local

DPTOOLS: Processing and converting data related to the DFTB+ package

> The source code is from DFTB+ project(<https://github.com/dftbplus/dftbplus/tree/24.1>). This project is just isolates the DPtools toolkit so that you can install it anywhere.

## Description
This package contains a few scripts which should make the life of
DFTB+ users easier by providing functions to process and convert
various DFTB+ data formats. It currently contains the following
utilities:

* **dp_bands**  
  Creates plotable band structure data from band.out

* **dp_dos**  
  Creates plotable density of states or partial density of states data
  by convolving the data produced by DFTB+ with (usually) gaussian
  broadening functions.

* **gen2cif**  
  Converts a file in gen format to cif, which contains information
  about the periodic boundary conditions. Among others, Jmol is
  capable of visualising cif files.

* **gen2xyz**  
  Converts a file in gen format to xyz in order to visualise it with
  practically all available molecular visualisers.

* **xyz2gen**  
  Converts an xyz file to gen file.

* **straingen**  
  Applies uniaxial, isotropic or shear strains to geometries,
  with principle axes aligned with the cartesian directions.

* **repeatgen**  
  Can be used to build supercell structures for phonon bandstructures

Each script can be invoked with the option ``-h`` to obtain a short
summary about its usage and possible options.

## Installation

You need CMake (>=3.29) and Python (>=3.12) to build DPtools.  If your environment offers no CMake or only an older one, you can easily install the latest CMake via Python's ``pip`` command:
```
pip install --upgrade cmake
```
Install the dptools library in python:
```bash
cd path/to/your/source_code
```
Configure the project (in your build directory):
```bash
mkdir build && cd build
cmake ..
```
Compile the code:
```bash
cmake --install .
```
Go back to the source code:
```
pip install .
```
Add the installation directory (your actual installation path) to ``PATH``:
```bash
echo 'export PATH="/opt/dptools/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
Now you can use DPtools in your bash, such as:
```bash
dp_dos -b 0.01 band.out dos.dat
```