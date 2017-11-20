#### Install Python to a custom location in Linux. (Replace with your version of Python)  
wget https://www.python.org/ftp/python/3.6.3/Python-3.6.3.tgz  
tar -xvzf Python-3.6.3.tgz  
cd Python-3.6.3  
mkdir /opt/py363  
./configure --prefix=/opt/py363  
make  
make install  
  
#### Create a virtual environment pointing to above Python version.  
/opt/py363/bin/pip3.6 install virtualenv  
/opt/py363/bin/virtualenv -p /opt/py363/bin/python3 virtualenv01  
cd virtualenv01  
source bin/activate  
which python  
python -V  
pip -V  
