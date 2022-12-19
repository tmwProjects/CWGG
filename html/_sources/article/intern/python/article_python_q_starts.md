# Quick starts

## Table of Contents

[Folder structure](#folder-structure)

[README.md](#readmemd)

[Install Pycharm IDEA](#install-pycharm-idea)

- [Linux](#for-linux)

- [Windows](#for-windows)

- [MacOS](#for-macos)

[Connect Pycharm with your Github Account](#connect-pycharm-with-your-github-account)

[Install and configure Git](#install-and-configure-git)

- [Linux](#git-for-linux)

- [Windows](#git-for-windows)

- [MacOS](#git-for-macos)

[Install Python 3.9](#install-python-39)

- [Linux](#python-for-linux)

- [Windows](#python-for-windows)

- [MacOS](#python-for-macos)

[Install pip and Python Modules](#install-pip-and-python-modules)

- [Linux](#pip-for-linux)

- [Windows](#pip-for-windows)

- [MacOS](#pip-for-macos)

[Fork this Repository](#fork-this-repository)

[Rules for workflow](#set-of-rules-for-the-workflow)

[Let's code!](#lets-code)

- [Links for programming with Python](#here-are-some-helpful-links-for-programming-with-python-in-relation-to-earth-science "Earth data science!")

- [Recommendations](#recommendations)
---

<a name="fold"></a>
### Folder structure

For successful integration and participation in this repository, detailed knowledge of our folder structure is necessary.


<a name="read"></a>
### README.md



<a name="pyc"></a>
### Install Pycharm IDEA

To minimise difficulties and keep everything consistent, we will work with Pycharm here.

<a name="pycl"></a>
#### For Linux

1) Download Pycharm Community Edition from [here](https://www.jetbrains.com/pycharm/download/#section=linux "Pycharm")

2) Then execute the following command in the terminal in the download directory:
<pre><code>sudo tar xfz pycharm-*.tar.gz -C /opt/</code></pre>

3) In the terminal, navigate to the target directory:
<pre><code>cd /opt/pycharm-*/bin</code></pre>

4) Execute the bash script:
<pre><code>./pycharm.sh</code></pre>

The Pycharm welcome window should then appear. 
A desktop entry can be created via the small gearwheel.


<a name="pycw"></a>
#### For Windows

1) Download Pycharm Community Edition from [here](https://www.jetbrains.com/pycharm/download/#section=windows "Pycharm")

2) Run the installer and follow the wizard steps.

<a name="pycm"></a>
#### For MacOS

1) Download Pycharm Community Edition from [here](https://www.jetbrains.com/pycharm/download/#section=mac "Pycharm")

2) Mount the image and drag the PyCharm application into the application folder.

3) Run the app from the Applications directory.

<a name="pycandgithub"></a>
### Connect Pycharm with your Github Account

- To integrate Github into PyCharm, go to **Settings** and type **Github** in the search bar. Under **Version control** 
you will now find the **Github** tab. Click on it and click on the small plus symbol.

- Select **Log in via Github...**

An authentication window will open in the web browser. Click on **authorise**.

- Enter your account details and accept.

- Github is then integrated into Pycharm.

<a name="gconf"></a>
### Install and configure Git

In our [GITHUB_CONFIG.md](https://github.com/tmwProjects/MSAT/blob/master/Set-Up/GITHUB_CONFIG.md "Configure Git and Github") 
file you will find a comprehensive explanation of how to configure and use Git, as well as Github. For a quick start to 
contributing to this repository, the following steps are necessary.

<a name="gfl"></a>
#### Git for Linux

Execute the following command in the terminal:
<pre><code>sudo apt-get install git</code></pre>

<a name="gfw"></a>
#### Git for Windows

1) Download Git for Windows from [here](https://git-scm.com/download/win "Download Git").

2) Run the installer and follow the wizard steps.

<a name="gfm"></a>
#### Git for MacOS

1) Download Git for Windows from [here](https://git-scm.com/download/mac "Download Git").

2) Run the installer and follow the wizard steps.

<a name="cgloyp"></a>
#### Configure git local on your PC

Execute the following command with your details in the terminal:

<pre><code>git config --global user.name "Pseudonym/Name"</code></pre>
<pre><code>git config --global user.mail "Mailadress"</code></pre>

Example:

<pre><code>$ git config --global user.name "Jane Bloggs"
$ git config --global user.mail "jane.bloggs@protonmail.com"</code></pre>

Furthermore, extremely complex configurations are possible.


<a name="python"></a>
### Install Python 3.9



<a name="pyl"></a>
#### Python for Linux

<pre><code>$ sudo apt update</code></pre>

<pre><code>$ sudo apt install python3.9</code></pre>

<pre><code>$ python3.9 --version</code></pre>

<a name="pym"></a>
#### Python for Windows

1) Download **Python3.9** installer from [here](https://www.python.org/ftp/python/3.9.8/python-3.9.8-amd64.exe "Download Python") and start the Installer.
2) Select the checkbox **Add Python 3.9 to PATH**. After that, click Customize Installation
3) Now, you will reach the section Optional Features. This by default checks the **pip** package installer, test suite, 
py launcher, etc.
4) Click **Next**.
5) The Advanced Options section would be visible now. Select **Install for all users**. On selecting it will set the 
following installation path on it own. You can change the installation path by clicking Browse. If you want to keep 
the default path, click **Install**.
6) After the Setup Progress click **close**.
7) To verify the installation, go to **START** >> type **CMD**, right-click **Open as Administrator**.
Execute in the terminal the following command:

<pre><code>python --version</code></pre>

<a name="pymos"></a>
#### Python for MacOS

1) Download **Python3.9** installer from [here](https://www.python.org/ftp/python/3.9.8/python-3.9.8-macos11.pkg "Download Python") and start the Installer.

**IMPORTANT**: If you need an Intel-only Install image, download the image from [here](https://www.python.org/ftp/python/3.9.8/python-3.9.8-macosx10.9.pkg "Download Python").

2) Follow the installation instructions.
3) To verify the installation execute in the terminal the following command:

<pre><code>python --version</code></pre>

<a name="mods"></a>
### Install pip and Python Modules

For the installation of Python modules a few small steps are necessary. First of all, make sure that the pip programme 
is installed. pip the package installer for Python. You can use pip to install packages from the Python Package Index 
and other indexes. The procedures for the most common operating systems are described below.

<a name="pyml"></a>
#### pip for Linux

First, execute the following commands in the terminal:

<pre><code>sudo apt update</code></pre>

<pre><code>sudo apt-get -y install python3-pip</code></pre>

Modules can then be installed with the following command:

<pre><code>pip3 install [PACKAGE] 

sudo pip3 install [PACKAGE]</code></pre>

For example:
<pre><code>pip3 install matchMS</code></pre>

Depending on the Linux distribution, the commands may differ slightly.

<a name="pymw"></a>
#### pip for Windows

**IMPORTANT**: Install pip via get-pip.py only with Python3 or later. This method doesn't work for earlier versions.

1) Download the get-pip File from [here](https://bootstrap.pypa.io/get-pip.py "Download pip").
2) Execute the following command in the terminal:

<pre><code>python get-pip.py</code></pre>

If the file isn’t found, double-check the path to the folder where you saved the file. You can view the contents of 
your current directory using the following command:

<pre><code>dir</code></pre>

3) Verify your installation:

<pre><code>pip help</code></pre>

4) To run PIP from any location, you need to add it to Windows environment variables to avoid getting the "not on PATH" 
error. To do so, follow the steps outlined below:

- Open the System and Security window by searching for it in the Control Plane.
- Navigate to System settings.
- Select Advanced system settings.
- Select New and add the directory where you installed PIP.
- Click OK to save the changes.

5) Upgrade pip with the the following command in the terminal:

<pre><code>python -m pip install --upgrade pip</code></pre>

<a name="pymm"></a>
#### pip for MacOS

**IMPORTANT**: Install pip via get-pip.py only with Python3 or later. This method doesn't work for earlier versions.

1) Download the get-pip File from [here](https://bootstrap.pypa.io/get-pip.py "Download pip").
2) Execute the following command in the terminal:

<pre><code>python get-pip.py</code></pre>

If the file isn’t found, double-check the path to the folder where you saved the file. You can view the contents of 
your current directory using the following command:

<pre><code>dir</code></pre>

3) Verify your installation:

<pre><code>pip help</code></pre>

4) Upgrade pip with the the following command in the terminal:

<pre><code>python -m pip install --upgrade pip</code></pre>

<a name="fork"></a>
### Fork this Repository

"A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without 
affecting the original project."

Source: [Github Docs](https://docs.github.com/en/get-started/quickstart/fork-a-repo)

The easiest way to fork a repository is to log in with your account on Github and visit the corresponding repository. 
On the start page, you will find a button in the top right-hand corner that is labelled **Fork**.

- **Click** on this button. A copy of the repository will then be cloned to your account.

- Then open the Pycharm welcome window.

- **Click** on **Projects**.

- Then **click** on **Get from VCS**. A window will open where you can select your personal Github account. Once you 
have done this, we will see all the projects or repositories. Select the appropriate one to clone it on your current PC.

<a name="rule"></a>
### Set of rules for the workflow

To get a structured view of whether you are programming cleanly, you can read through a few principles that can help 
you. You can find them in our [CODING_RULES.md](https://github.com/tmwProjects/MSAT/tree/master/Set-Up/CODING_RULES.md "Rules for clean code") file.

<a name="lcode"></a>
### Let's code!

In our repository you will find a small file called **main.py**. This is a small template with simple structures for a 
simplified overview for a quick start. You will notice that a module called **time** is already imported into this 
template. This, in conjunction with the small code that comes before and after your own code, measures the runtime 
of your code. 

The lower this is, the better.

<a name="helplink"></a>
#### Here are some helpful links for programming with Python in relation to Earth Science:

[Earth data science](https://www.earthdatascience.org/ "Earth data science"): "This site contains open, tutorials and course materials 
covering topics including data integration, GIS and data intensive science."

[Geo-Python 2019](https://geo-python.github.io/site/2019/index.html "Geo-Python"): "The Geo-Python course teaches you the basic 
concepts of programming using the Python programming language in a format that is easy to learn and understand (no 
previous programming experience required). Each lesson is a tutorial with specific topic(s) where the aim is to gain 
skills and understanding how to solve common data-related tasks using Python programming (see schedule & learning goals). 
Course is organized by the Department of Geosciences and Geography at the University of Helsinki."

[ImparoAnalytics](https://imparoanalytics.com/ "ImparoAnalytics"): "Earth Science is an interdisciplinary subject, using physics, 
chemistry, biology, geology and mathematics to understand how the solid earth, oceans and atmosphere work, how people 
impact the environment and how we can manage the earth’s natural resources in a sustainable manner. Earth Science 
datasets are increasing in size and complexity, and Earth Scientists need new approaches to data analysis and problem 
solving. Which is why Earth Data Science is a rapidly emerging field, as data science provides the toolbox to deal with 
data from a variety of sources and scales. From data acquisition, processing, visualizing, analysis and modeling, data 
science skills are increasingly core to the work of Earth Scientists." 

- The Repositorys with tutorials on Github can be found [here](https://github.com/A-Soden "").

[An Introduction to Earth and Environmental Data Science](https://earth-env-data-science.github.io/intro.html ""): 
"This book grew out of a course developed at Columbia University 
called Research Computing in Earth Science. It was written mostly by Ryan Abernathey, with significant contributions 
from Kerry Key and Tim Crone. By separating the book from the class, we hope to create an open-source community resource 
for Python education in the Earth and Environmental Sciences."

<a name="recom"></a>
#### Recommendations

A small recommendation here is [**Zeal**](https://zealdocs.org/ "ZEAL"). Zeal is a cross-platform offline documentation 
browser for developers. Zeal is available for Linux, Windows and MacOS. Zeal comes out of the box with a large set of 
docsets. These are not included in ZEAL, but can be downloaded with a few clicks.
