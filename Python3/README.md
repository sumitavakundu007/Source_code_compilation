# Compile Python-v3.6.X from source code

Download python-3.6.X.tar.xz from [official website](https://www.python.org/downloads/) and move that to the "source_root" directory, say 'softwares'

```bash
cd softwares
```
Untar it in the same directory

```bash
tar -xvf Python-3.6.X.tar.xz
```
Configure the build in a different directory or the same ditrectory, call it 'build-location'

```bash
cd /sofwares/Python-3.6.X
./configure --prefix=build-location --exec-prefix=build-location
```
Build the source with N processors

```bash
make -j N
```
Install

```bash
make install
```

you can set the PYTHONPATH in the .bashrc file, otherwise you have to specify the full directory of python binaries to execute python3.X i.e. build-location/bin/python3.X

pip (python2) or pip3 (python3) is automatically installed inside the bin directory. Install numpy, scipy in that directory

```bash
build-location/bin/python3.X/bin/pip3 install numpy
build-location/bin/python3.X/bin/pip3 install scipy
```
Check pip3 version

```bash
build-location/bin/python3.X/bin/pip3 --version
```
Check numpy and scipy version

```bash
build-location/bin/python3.X
>>> import numpy
>>> import scipy
>>> import(numpy.__version__)
>>> import(scipy.__version__)
```

## License
[MIT](https://choosealicense.com/licenses/mit/)