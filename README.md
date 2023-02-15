# RC-FAB-2D-Heterostructures-Docs
This repository contains the code documentation for the RC-FAB-2D-Heterostructures repository.

If you want to build the html documentation from the .rst files run the following code from within the repository folder.

```bash
pip3 install sphinx
pip3 install fugro
cd docs
make html
```

The documentation can now be found in the `docs -> build -> html` folder

To build the latex documentation use `make latex` instead of `make html`, a folder containing latex documents is now generated. It is recommended
to use overleaf for compiling.