===============================
Setting up a Jupyter Enviroment
===============================

pyntcloud wants to make point clouds fun again. In order to do so,
we need the right tools!

This page will guide you throw the process of setting up the right enviroment in order to make the most out of pyntcloud.

1. Grab and setup miniconda
----------------------------

Conda is a "OS-agnostic, system-level binary package manager and ecosystem".

https://conda.io/miniconda.html

**Grab conda 2.7 version**, it allows us to create python3 enviroments aswell, so
blindly trust me and grab the conda 2.7 version.

Answer **yes** when you get this prompt:

.. code-block:: bash

    Do you wish the installer to prepend the Miniconda2 install location
    to PATH in your /home/daviddelaiglesia/.bashrc ? [yes|no]
    [no] >>> yes

Once you have installed conda, add the `conda-forge <https://conda-forge.github.io/>`__ channel.

.. code-block:: bash

    conda config --add channels conda-forge

This will allow us to install packages from conda-forge, "A community led
collection of recipes, build infrastructure and distributions for the conda package manager".

2. Add Jupyter and nb_conda
---------------------------

Now that you have conda installed and the conda-forge channel is up, we are going
to add some cool packages.

First, we will install `Jupyter <http://jupyter.org/>`__ (and a bunch
of dependencies) in the **base** conda enviroment (make sure to use "source deactivate" if you are inside other enviroment).

.. code-block:: bash

    conda install jupyter -y

Try that everything is working by running:

.. code-block:: bash

    jupyter notebook

Shut it down with `Ctrl+C`.

Now, Jupyter is great, but it doesn't handle conda enviroments quite well by default.

So we will install a package that allows us to create, launch and manage notebooks
while working with different conda enviroments.

.. code-block:: bash

    conda install nb_conda -y

Now if you run:

.. code-block:: bash

    jupyter notebook

You should see a new Conda tab on the top.

This might look like a small modification, but it is game-changing. When you click
the New button, you can now select wich enviroment should
the new notebook. The package also add many other stuffs, take a lookt at its documentation:

3. Install pyntcloud
--------------------

Follow the steps at :ref:`basic-installation` -> Using conda.

You should now have an isolated enviroment with pyntcloud and all it's dependecies!.

To make use of it, run this from the **base** conda enviroment (make sure to use "source deactivate" if you are inside other enviroment):

.. code-block:: bash

    jupyter notebook

And create a new Notebook selecting env:pyntcloud as kernel.

4. Run the QuickStart
---------------------

Now that we have all setted up, let's run the QuickStart notebook, wich will give
us a quick overview of pyntcloud.