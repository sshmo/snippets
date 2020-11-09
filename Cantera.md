git clone --recursive https://github.com/<fork_name>/cantera.git
cd cantera

conda create -n <env_name> python=3 scons cython boost numpy ruamel_yaml
conda activate <env_name>

cantera.conf
python3_package = 'full'
boost_inc_dir = '/<path_to_conda_install_folder>/envs/cantera/Library/include'

scons build
scons install prefix=$CONDA_PREFIX

Install Code::Blocks
sudo add-apt-repository ppa:codeblocks-devs/release
sudo apt-get update
sudo apt-get install codeblocks codeblocks-contrib