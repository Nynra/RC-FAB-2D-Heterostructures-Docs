.. _programming_guidelines:

Programming guidelines
======================

The library was developed with modularity and flexibility in mind. While this means
that adding functionality is relatively easy it does not mean that no programming
knowledge is required. It is highly recommended to at least have knowledge about the 
topics below to avoid unpredictable behavior of the system.

* Python:
    * Virtual python environment on the used operating system
    * `Threading <https://docs.python.org/3/library/threading.html>`_
    * `Multiprocessing <https://docs.python.org/3/library/multiprocessing.html>`_
    * `Class inheritance <https://www.w3schools.com/python/python_inheritance.asp>`_
    * `Exception handling <https://docs.python.org/3/tutorial/errors.html>`_
    * `Logging <https://docs.python.org/3/library/logging.html>`_
    * `Unit testing <https://docs.python.org/3/library/unittest.html>`_
    * `Mocking and monkey patching <https://docs.python.org/3/library/unittest.mock.html>`_

it is important to keep a consistent syntax and style over the complete program
for this reason we have decided to use the following guidelines

* Use camelCase with the first letter uppercase for classes
* Use snake_case for variables and functions
* Use numpy style docstrings
* Use type hints for functions that accept input

.. note::

    Type hinting and typeguarding are not nessessary for functionality but make 
    it easier to read and understand the code. It also makes debugging in 
    the remote configuration easier.

    For some more info on typeguarding and hinting see the following links:
    * `type hinting <https://docs.python.org/3/library/typing.html>`_
    * `typeguarding <https://pypi.org/project/typeguard/>`_

New module guidelines
---------------------

New functionality is implemented by classes that inherit from the respective
base class. This means:
* New hardware modules should inherit from :class:`stacking_setup.components.stacking_backend.components.base.Base`
* New middleware modules should inherit from stacking_setup.stacking_backend.middleware.base.BaseConnector

New command guidelines
----------------------

Because the system is controlled using the Marlin Gcode command set it is also
possible to add new commands to the system. To make this as easy as possible the 
following guidelines are used:

* New commands should be added to the :class:`stacking_setup.components.stacking_backend.stacking_setup.StackingSetupBackend` class. 
The function name should be the ID of the command, for example :func:`M114`.
* The command function should accept the attributes in dict format (see the  :class:`stacking_setup.components.stacking_backend.gcode_parser.GcodeParser`
class for more information)
* The command name, accepted attributes and attribute types should be added to the ACCEPTED_COMMANDS dict in the 
:class:`stacking_setup.components.stacking_backend.config.accepted_commands.py` file