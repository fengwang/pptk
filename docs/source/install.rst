Installing pptk
===============

Install from PyPI
-----------------

One can either install pptk directly from PyPI

    >>> pip install pptk

or from the .whl file that results from 
:ref:`building pptk from source <build_from_source>`.

    >>> pip install <.whl file>

.. _build_from_source:

Building from source 
----------------------------------------

We provide CMake scripts for automating most of the build process, but ask the
user to manually prepare :ref:`dependencies <requirements>` and record their
paths in the following CMake cache variables.

* Numpy_INCLUDE_DIR
* PYTHON_INCLUDE_DIR
* PYTHON_LIBRARY
* Eigen_INCLUDE_DIR
* TBB_INCLUDE_DIR
* TBB_tbb_LIBRARY
* TBB_tbb_RUNTIME
* TBB_tbbmalloc_LIBRARY
* TBB_tbbmalloc_RUNTIME
* Qt5_DIR

To set these variables, either use one of CMake's GUIs (ccmake or cmake-gui),
or provide an initial CMakeCache.txt in the target build folder (for examples of
initial cache files, see the CMakeCache..txt files)

.. _requirements:

Requirements
~~~~~~~~~~~~

Listed are versions of libraries used to develop pptk, though earlier versions
of these libraries may also work.

* `QT <https://www.qt.io/>`_ 5.4
* `TBB <https://www.threadingbuildingblocks.org/>`_ 4.3
* `Eigen <http://eigen.tuxfamily.org>`_ 3.2.9
* `Python <https://www.python.org/>`_ 2.7+ or 3.6+
* `Numpy <http://www.numpy.org/>`_ 1.13

Windows
~~~~~~~

Create an empty build folder

    >>> mkdir <build_folder>

Create an initial CMakeCache.txt under <build_folder> and use it to provide
values for the CMake cache variables listed above. (e.g. see CMakeCache.win.txt)

Type the following...

    >>> cd <build_folder>
    >>> cmake -G "NMake Makefiles" <source_folder>
    >>> nmake
    >>> python setup.py bdist_wheel
    >>> pip install dist\<.whl file>

Linux
~~~~~

Similar to building on Windows.

Mac
~~~

Similar to building on Windows.