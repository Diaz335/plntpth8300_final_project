#installing fastStructure 
mkdir ~/proj
cd ~/proj
git clone https://github.com/rajanil/fastStructure
#retrieve latest code updates
cd ~/proj/fastStructure
git fetch
git merge origin/master

#build python extensions
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export CFLAGS="-I/usr/local/include"
export LDFLAGS="-L/usr/local/lib"

#set these environment variables.
source ~/.bashrc 

#build library extensions
cd ~/proj/fastStructure/vars
python setup.py build_ext --inplace

#to choose model complexity(model components that explain structure)
python chooseK.py --input=test/testoutput_simple

#inferring population structure--? will be given in step above
python structure.py -K ? --input=test/testdata --output=test/testoutput_simple