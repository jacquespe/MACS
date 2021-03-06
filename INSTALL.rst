======================
INSTALL Guide For MACS
======================
Time-stamp: <2012-04-28 12:54:45 Tao Liu>

Please check the following instructions to complete your installation.

Prerequisites
=============

Python version must be equal to *2.7* to run MACS. I recommend
using the version *2.7.2*.

Numpy_ (>=1.3.0) are required to run MACS v2. 

.. _Numpy: http://www.scipy.org/Download

GCC is required to compile ``.c`` codes in MACS v2 package, and python
header files are needed. If you are using Mac OSX, I recommend you
install Xcode; if you are using Linux, you need to make sure
``python-dev`` is installed.

Cython_ (>=0.14.1) is required *only if* you want to regenerate ``.c``
files from ``.pyx`` files using ``setup_w_cython.py`` script.

.. _Cython: http://cython.org/

Install under Debian or Ubuntu Linux system
===========================================

The most convenient way to install MACS is through Debian APT system,
so that it can be perfectly integrated in the Python environment of
your operation system. You can easily manage the package, and the
uninstallation is much easier. Download the *deb* package from MACS
download page, and type this in the commend line::

 $ dpkg -i macs_2.0.10.deb

To uninstall, type::

 $ dpkg -r macs_2.0.10

This is tested only in Ubuntu >= 10.04 LTS.

Install from source
===================

MACS uses Python's distutils tools for source installations. To
install a source distribution of MACS, unpack the distribution tarball
and open up a command terminal. Go to the directory where you unpacked
MACS, and simply run the install script::

 $ python setup.py install

By default, the script will install python library and executable
codes globally, which means you need to be root or administrator of
the machine so as to complete the installation. Please contact the
administrator of that machine if you want their help. If you need to
provide a nonstandard install prefix, or any other nonstandard
options, you can provide many command line options to the install
script. Use the –help option to see a brief list of available options::

 $ python setup.py --help

For example, if I want to install everything under my own HOME
directory, use this command::

 $ python setup.py install --prefix /home/taoliu/

If you want to re-generate ``.c`` files from ``.pyx`` files, you need
to install Cython first, then use ``setup_w_cython.py`` script to
replace ``setup.py`` script in the previous commands, such as::

 $ python setup_w_cython.py install

or::

  $ python setup_w_cython.py install --prefix /home/taoliu/

Configure enviroment variables
==============================

After running the setup script, you might need to add the install
location to your ``PYTHONPATH`` and ``PATH`` environment variables. The
process for doing this varies on each platform, but the general
concept is the same across platforms.

PYTHONPATH
~~~~~~~~~~

To set up your ``PYTHONPATH`` environment variable, you'll need to add the
value ``PREFIX/lib/pythonX.Y/site-packages`` to your existing
``PYTHONPATH``. In this value, X.Y stands for the major–minor version of
Python you are using (such as 2.7 ; you can find this with
``sys.version[:3]`` from a Python command line). ``PREFIX`` is the install
prefix where you installed MACS. If you did not specify a prefix on
the command line, MACS will be installed using Python's sys.prefix
value.

On Linux, using bash, I include the new value in my ``PYTHONPATH`` by
adding this line to my ``~/.bashrc``::

 $ export PYTHONPATH=/home/taoliu/lib/python2.7/site-packages:$PYTHONPATH

Using Windows, you need to open up the system properties dialog, and
locate the tab labeled Environment. Add your value to the ``PYTHONPATH``
variable, or create a new ``PYTHONPATH`` variable if there isn't one
already.

PATH
~~~~

Just like your ``PYTHONPATH``, you'll also need to add a new value to your
PATH environment variable so that you can use the MACS command line
directly. Unlike the ``PYTHONPATH`` value, however, this time you'll need
to add ``PREFIX/bin`` to your PATH environment variable. The process for
updating this is the same as described above for the ``PYTHONPATH``
variable::

 $ export PATH=/home/taoliu/bin:$PATH

About PeakSplitter
==================

Please go to it's main site
<http://www.ebi.ac.uk/bertone/software.html> to download.

--
Tao Liu <taoliu@jimmy.harvard.edu>

