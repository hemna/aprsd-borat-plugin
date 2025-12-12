
APRSD Borat Plugin
==================


.. image:: https://img.shields.io/pypi/v/aprsd-borat-plugin.svg
   :target: https://pypi.org/project/aprsd-borat-plugin/
   :alt: PyPI


.. image:: https://img.shields.io/pypi/status/aprsd-borat-plugin.svg
   :target: https://pypi.org/project/aprsd-borat-plugin/
   :alt: Status


.. image:: https://img.shields.io/pypi/pyversions/aprsd-borat-plugin
   :target: https://pypi.org/project/aprsd-borat-plugin
   :alt: Python Version


.. image:: https://img.shields.io/pypi/l/aprsd-borat-plugin
   :target: https://opensource.org/licenses/MIT
   :alt: License



.. image:: https://img.shields.io/readthedocs/aprsd-borat-plugin/latest.svg?label=Read%20the%20Docs
   :target: https://aprsd-borat-plugin.readthedocs.io/
   :alt: Read the documentation at https://aprsd-borat-plugin.readthedocs.io/


.. image:: https://github.com/hemna/aprsd-borat-plugin/workflows/Tests/badge.svg
   :target: https://github.com/hemna/aprsd-borat-plugin/actions?workflow=Tests
   :alt: Tests


.. image:: https://codecov.io/gh/hemna/aprsd-borat-plugin/branch/main/graph/badge.svg
   :target: https://codecov.io/gh/hemna/aprsd-borat-plugin
   :alt: Codecov



.. image:: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white
   :target: https://github.com/pre-commit/pre-commit
   :alt: pre-commit


----

..

   [!WARNING]
   Legal operation of this software requires an amateur radio license and a valid call sign.

   [!NOTE]
   Star this repo to follow our progress! This code is under active development, and contributions are both welcomed and appreciated. See `CONTRIBUTING.md <https://github.com/hemna/aprsd-borat-plugin/blob/master/CONTRIBUTING.md>`_ for details.


Features
--------

The APRSD Borat Plugin provides a fun APRSD plugin that responds to messages with random Borat quotes. Key features include:


* **Random Quote Responses**\ : Responds to messages starting with "b" or "B" with random Borat quotes
* **APRS Message Formatting**\ : Automatically wraps quotes to fit within APRS message length limits (67 characters per line)
* **Easy Configuration**\ : Simple enable/disable configuration option
* **Large Quote Database**\ : Includes a collection of classic Borat quotes

Requirements
------------


* ``aprsd >= 4.2.4``
* A running APRSD instance

Installation
------------

You can install *APRSD Borat Plugin* via `pip <https://pip.pypa.io/>`_ from `PyPI <https://pypi.org/>`_\ :

.. code-block:: console

   $ pip install aprsd-borat-plugin

Or using ``uv``\ :

.. code-block:: console

   $ uv pip install aprsd-borat-plugin

Configuration
-------------

Before using the Borat plugin, you need to configure it in your APRSD configuration file.
Generate a sample configuration file if you haven't already:

.. code-block:: console

   $ aprsd sample-config

This will create a configuration file at ``~/.config/aprsd/aprsd.conf`` (or ``aprsd.yml``\ ).

Plugin Configuration
^^^^^^^^^^^^^^^^^^^^

Add the following section to your APRSD configuration file to enable the Borat plugin:

.. code-block:: yaml

   [aprsd_borat_plugin]
   # Enable the Borat plugin (default: False)
   enabled = True

Example Configuration
^^^^^^^^^^^^^^^^^^^^^

Here's a complete example configuration:

.. code-block:: yaml

   [aprsd_borat_plugin]
   enabled = True

Usage
-----

Once installed and configured, the Borat plugin will automatically be loaded when you start APRSD.

How It Works
^^^^^^^^^^^^

The plugin responds to APRS messages that start with "b" or "B" (case-insensitive). When triggered, it will:


#. Select a random quote from its database
#. Wrap the quote to fit APRS message length limits (67 characters per line)
#. Send the formatted quote back to the sender

Example Usage
^^^^^^^^^^^^^

If someone sends you an APRS message like:

.. code-block::

   b

or

.. code-block::

   B hello

The plugin will respond with a random Borat quote, such as:

.. code-block::

   Kazakhstan is number one exporter of potassium,
   Other Central Asian countries have inferior
   potassium.

Verifying It's Working
^^^^^^^^^^^^^^^^^^^^^^

After starting APRSD, check the logs for messages like:

.. code-block::

   INFO: Loading plugin: BoratPlugin
   INFO: BoratPlugin enabled

You can test the plugin by sending yourself an APRS message starting with "b" or "B" and you should receive a Borat quote in response.

For more details, see the `Command-line Reference <https://aprsd-borat-plugin.readthedocs.io/en/latest/usage.html>`_.

Contributing
------------

Contributions are very welcome. To learn more, see the `Contributor Guide <CONTRIBUTING.md>`_.

License
-------

Distributed under the terms of the `MIT license <https://opensource.org/licenses/MIT>`_\ ,
*APRSD Borat Plugin* is free and open source software.

Issues
------

If you encounter any problems,
please `file an issue <https://github.com/hemna/aprsd-borat-plugin/issues>`_ along with a detailed description.

Credits
-------

This project was generated from `@hemna <https://github.com/hemna>`_\ 's `APRSD Plugin Python Cookiecutter <https://github.com/hemna/cookiecutter-aprsd-plugin>`_ template.
