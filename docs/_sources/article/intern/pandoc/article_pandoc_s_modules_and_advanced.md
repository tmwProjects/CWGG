# Modules for Python

The following modules are directly related to the processing of mass spectrometry data or geological datasets.
For the correct handling of the modules, the corresponding documentation must be researched.

## Mass spectrometry

- matchMS
- PyMassSpec
- spectrum_utils
- PythonMS
- pyhrms
- CoreMS
- PyQuant
- pymzml

The following packages are not available via pip.
They must be downloaded and implemented separately.

- aspg
- microMS

### Geological data sets

- pyrolite
- BurnMan

### Mathematics and Statistics

- numpy
- matplotlib
- scipy

### Data manipulation

- Panda

## Install Modules

For the installation of Python modules a few small steps are necessary. First of all, make sure that the pip programme 
is installed. pip is the package installer for Python. You can use pip to install packages from the Python Package Index 
and other indexes. The procedures for the most common operating systems are described below.

### Linux:

First, execute the following command in the terminal:

<pre><code>sudo apt-get -y install python3-pip</code></pre>

Modules can then be installed with the following command:

<pre><code>pip3 install [PACKAGE] 

sudo pip3 install [PACKAGE]</code></pre>

For example:
<pre><code>pip3 install matchMS</code></pre>

Depending on the Linux distribution, the commands may differ slightly.

### Windows:

<pre><code>pip install [PACKAGE]</code></pre>

### MacOS:

<pre><code>pip install [PACKAGE]</code></pre>
