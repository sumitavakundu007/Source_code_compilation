# Compile GCC 7.5.0 (c++11 compiler) from source code

```bash
unset LIBRARY_PATH CPATH C_INCLUDE_PATH PKG_CONFIG_PATH CPLUS_INCLUDE_PATH INCLUDE
```
Set a directory as /path/to/prefix

Compile GMP
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/gmp-4.3.2.tar.bz2
tar -xvf gmp-4.3.2.tar
cd gmp-4.3.2
./configure --disable-shared --enable-static --prefix=/path/to/prefix
make && make check && make install
```

Compile MPFR
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/mpc-0.8.1.tar.gz
tar -xvf mpfr-2.4.2.tar
cd mpfr-2.4.2
./configure --disable-shared --enable-static --prefix=/tmp/gcc --with-gmp=/path/to/prefix
make && make check && make install
```
Compile MPC
```bash
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/mpc-0.8.1.tar.gz
tar zxvf mpc-0.8.1.tar.gz
cd mpc-0.8.1
./configure --disable-shared --enable-static --prefix=/tmp/gcc --with-gmp=/path/to/prefix --with-mpfr=/path/to/prefix
make && make check && make install
```

ISL
```bash
tar -xvf isl-0.18.0.tar.gz
cd isl-0.18.0
./configure --disable-shared --enable-static --prefix=/tmp/gcc --with-gmp=/path/to/prefix
make && make install
```

Compile GCC
```bash
cd gcc
mkdir build && cd build
../configure --prefix=/path/to/prefix --enable-std=c++11 --enable-shared --disable-bootstrap --disable-libstdcxx-pch --enable-languages=all --enable-threads=posix --with-gmp=/path/to/prefix --with-mpfr=/path/to/prefix --with-mpc=/path/to/prefix --with-libisl=/path/to/prefix --disable-multilib --disable-werror
make -j N
make install
```

## License
[MIT](https://choosealicense.com/licenses/mit/)