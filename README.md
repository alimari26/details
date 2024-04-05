
cSR Screening Automation Framework - with additional comments
===============================================================

This refers to the cSR_devel pack available at: https://github.com/aneveol/cSR_devel.git

Preliminaries
-------------

1. The code is run on a UNIX system (if you are on a Windows system, consider using a WSL, as the files are written for UNIX)
2. Python (>3.5.3) - the requirements.txt files contain package versions compatible with Python 3.5.3, please update depending on your version.
3. The files are nested as copies. There are multiple requirements.txt files at different levels. Start in `/cSR_devel/cSR`
4. Throughout the reference document (readme.md - of https://github.com/aneveol/cSR_devel.git) the path `/cSR_devel/cSR` is referred to as `~/cSR`

Checking & Installing Dependencies
-----------------------
Before starting, make sure the current working directory is the cSR root directory. (`/cSR_devel/cSR`)

### Python

```console
which python3
```
/usr/bin/python3
```console
python3 --version
```
Python 3.5.2

### Pip
Make sure pip is linked to the python version resulted above
```console
which pip3
```
/usr/bin/pip3

```console
pip3 --version
```
pip 19.3.1 (python 3.5.2)

### Virtual environment
Start by checking if you have a virtual environment installed
```console
virtualenv --version
```
If there is a version output, skip to: Set up.

#### Alternatively, to install virtual environments:

```console
pip install virtualenvwrapper
```
```console
export WORKON_HOME=~/Envs  # Choose a location for your virtual environments
export VIRTUALENVWRAPPER_PYTHON=/path/to/your/python
source /path/to/virtualenvwrapper.sh
```
```console
source ~/.bashrc
```
#### Set up your virtual environment called `SR_env`

```console
mkvirtualenv -p `which python3` SR_env
workon SR_env
````
You will know the virtual environment is active if you can see `(SR_env)` before your PATH.
To reload the environment after logging out, run:

```console
c workon SR_env
````

### Packages
There are multiple different requirements.txt files in the git. These contain different packages to be installed.
Initially, make sure you are in the `/cSR_devel/cSR` folder

```console
pip3 install -r requirements.txt
````

## Note on versions for more recent python version

If you have Python 3.10.12, I have added the version of the packages in the `/cSR_devel/cSR/requirements.txt`, assuming a pip 24.0

future==0.16.0
Keras==2.1.2
numpy==1.22.4
gensim==3.3.0
nltk==3.2.5
lxml==4.1.1
requests==2.18.4
scipy==1.12
ujson==1.35
Bio==1.5
PyYAML==5.2
scikit_learn==1.1

### Testing the installation

If all dependencies have been installed correctly, the following command should run without error:

```console
python -m csr.Data --help
````

Please check the `help` files for the additional modules as well: 

- `csr.Import`
- `csr.Export`
- `csr.Medline`
- `csr.Train`
- `csr.ML.Evaluation`
- `csr.Vocabulary`

## Note: to continue from this point, you will need access to the COMET json and xml files. 
