# Compile OpenMPI from source code

Download the latest version of OpenMPI from its [official page](https://www.open-mpi.org/software/ompi)
Create a directory "softwares" and copy that .tar.gz file into that directory

```bash
mkdir softwares
cp /download_location/openmpi-3.1.3.tar.gz /installation_location/softwares
```
Untar it in the same directory

```bash
tar -xvf openmpi-*
```
Configure the build in a different directory or the same ditrectory

```bash
cd openmpi-*
./configure --prefix="/path/to/prefix/.openmpi"
```
Build the source with N processors

```bash
make -j N
```
Install

```bash
make install
```

Now all that is left to do is to include the path to your path environment
Add the lines to your .bashrc file

```bash
export PATH="$PATH:/path/to/prefix/.openmpi/bin"
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/path/to/prefix/.openmpi/lib/"
```

If your system doesn't have a default OpenMPI then type the following command to see the OpenMPI version

```bash
mpirun --version
```

If you don't add the path in your .bashrc file then type

```bash
/path/to/prefix/.openmpi/bin/mpirun --version
```