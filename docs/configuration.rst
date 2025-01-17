.. _configuration:

Configuration
=============

Pre-installed packages
----------------------

xeus-python allows you to pre-install packages in the Python runtime. You can pre-install packages by passing the ``XeusPythonEnv.packages`` CLI option to ``jupyter lite build``.

.. note::
    This will automatically install any labextension that it founds, for example installing ipyleaflet will make ipyleaflet work without the need to manually install the jupyter-leaflet labextension.

For example, say you want to install ``NumPy``, ``Matplotlib`` and ``ipyleaflet``, it can be done with the following command:

.. code::

    jupyter lite build --XeusPythonEnv.packages=numpy,matplotlib,ipyleaflet

The same can be achieved through a ``jupyterlite_config.json`` file:

.. code::

    {
        "XeusPythonEnv": {
            "packages": ["numpy", "matplotlib", "ipyleaflet"]
        }
    }

Then those packages are usable directly:

.. replite::
   :kernel: xeus-python
   :height: 600px
   :prompt: Try it!

   %matplotlib inline

   import matplotlib.pyplot as plt
   import numpy as np

   fig = plt.figure()
   plt.plot(np.sin(np.linspace(0, 20, 100)))
   plt.show();
