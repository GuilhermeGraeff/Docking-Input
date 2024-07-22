https://gnina.github.io/libmolgrid/tutorials.html

Daqui eu tirei os tutoriais:
Custom atom typer example -> https://gnina.github.io/libmolgrid/tutorials/custom_atom_typer_example.html
Grid single molecule -> https://gnina.github.io/libmolgrid/tutorials/grid_single_molecule.html
Train basic cnn with pytorch -> https://gnina.github.io/libmolgrid/tutorials/train_basic_CNN_with_PyTorch.html
Train basic cnn with tensorflow -> https://gnina.github.io/libmolgrid/tutorials/train_basic_CNN_with_Tensorflow.html
Train simple cartesian reduction -> https://gnina.github.io/libmolgrid/tutorials/train_simple_cartesian_reduction.html



Para instalar o open babel, foram necessários seguir diferentes passoso nos seguintes links(mó difícil):
https://openbabel.org/docs/UseTheLibrary/PythonInstall.html#linux-and-macosx
https://openbabel.org/docs/Installation/install.html#install-binaries
https://github.com/openbabel/openbabel/releases

1. Create a 'build' directory:

   mkdir build
   cd build

2. Configure the build system. You can specify additional build
options at this time (see below):

   cmake .. -DPYTHON_BINDINGS=ON <- usar esta flag! 

3. Compile:

   make -j2

4. Test (optional):

   make test

5. Install:

   sudo make install

export PYTHONPATH=/usr/local/lib:$PYTHONPATH


