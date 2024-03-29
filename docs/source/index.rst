.. Stacking setup documentation master file, created by
   sphinx-quickstart on Wed Oct 26 11:45:28 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Stacking setup's documentation!
==========================================

**Stacking setup** is a python library that is used to control custom stacking setups for stacking 2D materials. The library consists of 3 parts: The backend, frondend, and middleware. 
All of the hardware control takes place in the backend components, all interactions with the user (except for CLI) takes place in the frontend components, the middleware connects the frond and backend.

.. note::
    This project was created for research purposes and not commercial distribution, this means that the code is not as well tested
    as expected from a commercial product. The code is provided as is and no support is provided. Safe operation is the responsibility of the user.

Getting started
---------------
.. toctree::
   :maxdepth: 2

   getting_started/installation
   getting_started/configuration
   getting_started/programming_guidelines
   getting_started/troubleshooting

Library contents
----------------
.. toctree::
   :maxdepth: 2

   apidoc_generated/components.stacking_frondend
   apidoc_generated/components.stacking_middleware
   apidoc_generated/components.stacking_backend
   apidoc_generated/tests

