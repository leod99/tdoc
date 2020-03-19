# Install pip offline

Download pip whl file from https://pypi.org/project/pip/#files  copy the file to host with WinSCP, then run

  sudo python pip-20.0.2-py2.py3-none-any.whl/pip install pip-20.0.2-py2.py3-none-any.whl


Optionally, if you use virtual environment for your project, run below CLI to create virtual environment, venv will create a virtual Python installation in the env folder,

refer to the link <https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/> for more detail

  python -m venv env


# Install Python packages offline

Steps to install python packages as below, take asn1 package for example.

  1.   Download  whl or tar.gz file for the package on pypi.org<https://pypi.org/project/asn1/#files>  https://pypi.org/project/asn1/#files for asn1
  2.   Copy the file to target host with WinSCP
  3.   Run pip install against the whl/tar.gz file as below,  activate virtual env with source env/bin/activate before pip install if venv is used for the project
  4.  If any dependency package(s) missing, repeat the steps from step 1 for the missing package(s) until the package is successfully installed

  pip install asn1crypto-1.0.0-py2.py3-none-any.whl


If any rpm is missing, for example postgresql-devel-9.2.24-1.el7_5.x86_64.rpm,  download it from rpmfind, copy to the host, then install with rpm -ivh,  add sudo in front if any permission issue.

rpm -ivh postgresql-devel-9.2.24-1.el7_5.x86_64.rpm

