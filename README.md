# **Natural Language Processing In Python**

Be sure to have experience in python fundamental syntax. This guide assumes it's user is on Ubuntu or Debian Platform.

## Pre-requisites 
- Install and configure Git
- Signup for GitHub account
- Install and configure virtual environment and virtual wrapper (Try Anacoda)
- Docker containerization

## Tricks and Magic
- Operations with strings
- Pattern matching with regular expressions
- Web scrapping (requests, urllib, Beautiful Soup)
- Data Serialization (simplejson and pickle)
- Input/Output (file-systems and database systems)
- Multi-Threading
- Multi-Processing
- Asyncio
- Using Celery[Redis] for batch processing
- Getting started with Numpy, Pandas
- Visualization with Matplotlib
- Word cloud diagrams

## DevOps (Data Handling)
- Data preparation and acquisation
- Data assessment and cleaning
- Data aggregation
- Exploratory Data Analysis

## Neural Networks
- Example (statistical) model (Keras/Tensorflow/Scikit-learn)

## NLP
- Getting started with NLTK, Spacy, TextBlob, Polyglot, CoreNLP, Gensim


> # Python Environment Setup

### **NOTE**
>    `$` denotes termonal input  
>    `>>>`  denotes input within python environment  
>  `In [n]:` denotes input within ipython environment

Packages update and ugrade  

`$ sudo apt update && sudo apt upgrade -y`  

build dependancies  

`$ sudo apt install build-essential software-properties-common -y ` 
` sudo apt install libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget -y
`

If you are on Debian, then you need to install zlib.

`$ sudo apt install zlib1g-dev -y `

Download preferred python flavor source tarball.

`$ wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz `   
Alternatively   
`$ curl -O https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz `  

Unzip the tarball.

`$ tar -xzvf Python-3.7.4.tgz `

Configure the build the source.

`$ cd Python-3.7.4`  
`$ ./configure --enable-optimizations`  

Build the binaries and install

`$ make -j n`  #where n is the number of processor cores  
`$ sudo make altinstall `  #Do not use the standard make install as it will overwrite the default system python3 binary. 

On terminal type

`$ python3.7 `

## Customizations

> Alter python command for the signed-in user. Can be done for all users (It's not recommended changing global python command for there might be OS packages dependancy on python2.7)

`$ nano ~/.profile `  

Add the following two lines in your ~/.profile script:

` alias python=python3.7 `  
` alias pip=pip3 ` 

Close terminal and re-open it    
On the newly opened terminal type 

`$ python `


## Working with Virtual Environments
---

Using python built-in -m venv command

`$ python3 -m venv myvenv `

Activate the environment

`$ source myvenv/bin/activate `

Install package into the environment

`$ pip install simplejson ipython`

Run (python) code from the environment

`$ python `  
`>>> from simplejson import loads`   
`>>> print('hello world')`  

Output:
> hello world

Run above code from ipython environment

`$ ipython `  
`In [1]: from simplejson import loads`   
`In [2]: print('hello world')` 

Output:
> hello world
 
### Install virtualenv
`$ pip3 install virtualenv  `  

Now create a virtual environment

`$ virtualenv -p python3.7 venv `

Create virtual environment with system site packages

`$ virtualenv --system-site-packages -p python3.7 venv `

Activate and use the environment

`$ source venv/bin/activate `  

### Install and configure virtualwrapper

`$ pip3 install virtualenvwrapper `  
`$ mkdir ~/.virtualenvs `  
`$ nano ~/.profile`  

Add the following lines in your ~/.profile script:

` export WORKON_HOME="$HOME/.virtualenvs" ` 
` VIRTUALENVWRAPPER_PYTHON='/usr/bin/python3.7' `  #This needs to be placed before the virtualenvwrapper command  
` source /usr/local/bin/virtualenvwrapper.sh `  

Execute below command to complete setup

` source ~/.profile `  

Exit the terminal and open a new window   
In the newly opened terminal window, type these commands to create virtual environments within virtualwrapper

` mkvirtualenv testvenv `  
` mkvirtualenv anothervenv `   
` deactivate `   
` workon `   
` workon testvenv `
` rmvirtualenv anothervenv `

> Visit [commands reference](https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html) for more information


> ## Install Git

`$ sudo apt install git `

Configuring Git 

`$ git config --global user.name "Your Name" `  
`$ git config --global user.email "youremail@yourdomain.com"`  

Verify the changes

`$ git config --list `

> ## Finally install jupyter notebook

`$ mkvirtualenv nlpcrash `  
`$ pip install ipython ipykernel jupyter `  
