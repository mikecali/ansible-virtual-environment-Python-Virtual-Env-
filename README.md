# Ansible and Python Virtual Environment 

## Download the packages that are needed to install Python version and the virtualenv onto the home directory.:
 - Python-2.7.9.tgz
 - virtualenv-15.0.2.tar.gz

## Create python 2.7.9 virtual environment

cd $HOME/

## Install dependencies

yum install -y zlib-dev openssl-devel sqlite-devel bzip2-devel zlib-devel

## Extract python-2.7.9 installation package

``
 tar -zxvf Python-2.7.9.tgz
 mkdir $HOME/paraenv
 cd $HOME/Python-2.7.9
 ./configure --prefix=$HOME/paraenv
 make
 make install
``

## Extract virtualenv and setup the python2.7 to be used in the virtualenv
``

 cd $HOME/
 tar xvf virtualenv-15.0.2.tar.gz
 cd virtualenv-15.0.2
 $HOME/paraenv/bin/python2.7 setup.py install
 cd $HOME/
 paraenv/bin/virtualenv ve -p paraenv/bin/python2.7
``

## Activate the virtual environment
source ve/bin/activate

#Check the Python version inside the virtual environment

``
[root@xxx]# source ve/bin/activate
(ve) [root@csuxprsgs107 sup-521200]# python -V
Python 2.7.9 
``

## Install the ansible package inside the python virtual environment


## Download ansible-2.2 and other dependencies packages and put it in a directory. for our test we we use the $HOME/ansible2.2 directory.

``
ansible-2.2.1.0.tar.gz
Jinja-1.2.tar.gz
paramiko-2.1.2-py2.py3-none-any.whl
httplib2-0.10.3.tar.gz
setuptools-34.3.2-py2.py3-none-any.whl
PyYAML-3.12.tar.gz
Jinja2-2.8.1-py2.py3-none-any.whl
pycrypto-2.6.1.tar.gz
pyasn1-0.2.3-py2.py3-none-any.whl
cryptography-1.8.1.tar.gz
six-1.10.0-py2.py3-none-any.whl
pyparsing-2.2.0-py2.py3-none-any.whl
pycparser-2.17.tar.gz
packaging-16.8-py2.py3-none-any.whl
MarkupSafe-1.0.tar.gz
ipaddress-1.0.18-py2-none-any.whl
idna-2.5-py2.py3-none-any.whl
enum34-1.1.6-py2-none-any.whl
cffi-1.10.0-cp27-cp27m-manylinux1_x86_64.whl
asn1crypto-0.22.0-py2.py3-none-any.whl
appdirs-1.4.3-py2.py3-none-any.whl
``

## Activate the virtual environment
source ve/bin/activate

cd $HOME/ansible2.2

pip install --no-index --find-links=$HOME/ansible2.2/ ansible-2.2.1.0.tar.gz --verbose

## Check the ansible version

``
(ve) [root@csuxprsgs107 sup-521200]# ansible --version
ansible 2.2.1.0
  config file = /etc/ansible/ansible.cfg
  configured module search path = Default w/o overrides
``
