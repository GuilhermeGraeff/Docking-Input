# Links
https://gnina.github.io/libmolgrid/tutorials.html
https://github.com/gnina/libmolgrid/tree/master/test/data <- dataset 'structs' and small.types
https://www.pdbbind-plus.org.cn/download
https://gitlab.com/cheminfIBB/pafnucy
https://gitlab.com/cheminfIBB/tfbio
http://gnina.github.io/gnina/rsc_workshop2021/#/50


Daqui eu tirei os tutoriais:
Train basic cnn with tensorflow/keras -> https://gnina.github.io/libmolgrid/tutorials/train_basic_CNN_with_Tensorflow.html
Train basic cnn with pytorch          -> https://gnina.github.io/libmolgrid/tutorials/train_basic_CNN_with_PyTorch.html
Train simple cartesian reduction      -> https://gnina.github.io/libmolgrid/tutorials/train_simple_cartesian_reduction.html
Custom atom typer example             -> https://gnina.github.io/libmolgrid/tutorials/custom_atom_typer_example.html
Grid single molecule                  -> https://gnina.github.io/libmolgrid/tutorials/grid_single_molecule.html

# Primeira referencia para instalar o openbabel
Para instalar o openbabel, foram necessários seguir diferentes passoso nos seguintes links(mó difícil):
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

# Para utilizar o gninatyper (https://github.com/gnina/gnina README.md desse repo):
"gninatyper tool needs to be installed on your machine (it is installed alongside gnina)."

## Install OpenBabel3. Note there are errors in bond order determination in version 3.1.1 and older.
git clone https://github.com/openbabel/openbabel.git
cd openbabel
mkdir build
cd build
cmake -DWITH_MAEPARSER=OFF -DWITH_COORDGEN=OFF -DPYTHON_BINDINGS=ON -DRUN_SWIG=ON ..
make
make install

## Install gnina
git clone https://github.com/gnina/gnina.git
cd gnina
mkdir build
cd build
cmake ..
make
make install

# This is important (from https://github.com/gnina/scripts):

"The train/test files are of the form 1 set1/159/rec.gninatypes set1/159/docked_0.gninatypes where the first value is the label, the second the receptor, and the third the ligand. Additional whitespace delimited fields are ignored. gninatypes files are created using gninatyper. The receptor and label paths in these files can be absolute, or they can be relative to a path provided as the DATA_ROOT argument. To use this option, the root_folder parameter in each MolGridDataLayer of the model file should be the placeholder value "DATA_ROOT". This can also be hard-coded into the model."