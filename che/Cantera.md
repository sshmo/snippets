# Cantera

## Fork and clone cantera

```bsah
    git clone --recursive https://github.com/<fork_name>/cantera.git
    cd cantera
```

## create a conda envirnoment with installed reqs

``` bash
    conda create -n <env_name> python=3 scons cython boost numpy ruamel_yaml
    conda activate <env_name>
```

## change cantera configurations

``` bash
    cantera.conf
    python3_package = 'full'
    boost_inc_dir = '/<path_to_conda_install_folder>/envs/cantera/Library/include'
```

## build cantera and install it locally

``` bash
    scons build
    scons install prefix=$CONDA_PREFIX
```

## Install Code::Blocks

``` bash
    sudo add-apt-repository ppa:codeblocks-devs/release
    sudo apt-get update
    sudo apt-get install codeblocks codeblocks-contrib
```

## Code::Blocks compiler settings

``` bash
    linker: add pthread
    linker: add /<path_to_conda_install_folder>/envs/<env_name>/lib/libcantera.a
    search_directories/Compiler: add /<path_to_conda_install_folder>/envs/<env_name>/include
    search_directories/Linker: add /<path_to_conda_install_folder>/envs/<env_name>/cantera/build/lib
```
