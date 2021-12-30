# cmake-mpi-test
testing cmake setup for C++ MPI projects

An example file main.cpp is compiled through cmake to set-up MPI.

## Dependencies

Compiler (tested with GNU 9.3.0, Ubuntu 20.04) and MPI implementation needed. 

```
sudo apt install mpich
```

Check if `which mpic++` gives back a path. 

## Usage

Make a build folder, change to it and call cmake to above files.
```
mkdir build
cd build
cmake ..
```
Start compilation procedure, install into exe folder, change to it and 
run it through mpirun to get MPI. 
```
make
make install
cd ../exe
mpirun main
```
Output should be equal to:
```
Hello from rank 0
Hello from rank 1
```

# Credits
see this [Stackoverflow Question](https://stackoverflow.com/questions/23163075/how-to-compile-an-mpi-included-c-program-using-cmake)
for some discussion.
