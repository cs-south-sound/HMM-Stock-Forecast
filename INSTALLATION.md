# INSTALLATION

## Prerequisites

`uname -ior`
    6.13.5-100.fc40.x86_64 unknown GNU/Linux

`sudo dnf upgrade --refresh`  - Get the latest versions of system packages

`sudo dnf install gcc-c++`    - [cpp_installation](https://developer.fedoraproject.org/tech/languages/c/cpp_installation.html)
    Total 693 kB/s |  59 MB     01:27

`sudo dnf install cmake`      - [cmake](https://developer.fedoraproject.org/tech/languages/c/cmake.html)
    Total 403 kB/s |  12 MB     00:31

- install pyenv prerequisites
  > Reference: https://realpython.com/intro-to-pyenv/
  > For managing Python versions
```bash
sudo dnf install gcc zlib-devel bzip2 bzip2-devel readline-devel sqlite \
sqlite-devel openssl-devel xz xz-devel libffi-devel
```
- install pyenv
  `curl https://pyenv.run | bash`

- get a list of available versions
  `pyenv install --list | less`
- install a version of python
  `pyenv install -v 3.13.2` 
- enable a version
  `pyenv global 3.13.2`

```bash
sudo find / -name Python.h
/home/mynamehere/.pyenv/versions/3.13.2/include/python3.13/Python.h
```
Add to the ~/.bash_profile
`export CPATH=/home/mynamehere/.pyenv/versions/3.13.2/include/python3.13/`
then to enable the path run
`source ~/.bash_profile`

`pip install --upgrade pip`

----
`g++ --version`
    g++ (GCC) 13.3.1 20240913 (Red Hat 13.3.1-3)

`cmake --version`
    cmake version 3.30.5

`python --version`  - installed above by pyenv
    Python 3.13.2
    
`pip --version`
    pip 25.0.1
    
`pyenv --version`
    pyenv 2.5.3
    
## Aquire the project code

```bash
git clone https://github.com/cs-south-sound/HMM-Stock-Forecast.git
cd HMM-Stock-Forecast
```


Create virtual environment
`python3 -m venv venv`

Enable virtual environment
`. venv/bin/activate`

Install dependencies defined in pyproject.toml
`pip install .`


## Test the installation
```bash
cd ~/HMM-Stock-Forecast/hmm_stock_forecast
python3 -m main.py -s 2019-01-01 -e 2022-01-01 -t SPY -w 100
```
