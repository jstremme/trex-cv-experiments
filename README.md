# trex-cv-experiments

[![python38](https://img.shields.io/badge/python-3.8-orange.svg)]()
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

Contains code and instructions for analyzing experiments with the [trex](https://github.com/mooch443/trex) computer vision tool

### About

...

### Build the Trex Environment

The instructions and code in this repository have been tested on MacOS Big Sur Version 11.5.1 with an Intel Core i7 processor and 32 GB memory.  To build the environment on this or a similar machine, follow the steps below.  For more information about using [Tensorflow](https://github.com/tensorflow/tensorflow) (which powers Trex) in a MacOS [conda environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#activating-an-environment), see [this post](https://github.com/apple/tensorflow_macos/issues/153).

1. Make sure you have git for MacOS installed (see installation instructions [here](https://github.com/git-guides/install-git)).  Simply type `git` into your terminal to test that the git CLI tool is installed.
2. In your terminal, run `git clone --depth 1 --branch v1.1.3 https://github.com/mooch443/trex` from the base directory of this repository.
3. In your terminal, `cd` to the `trex` subdirectory.
4. Install Anaconda for MacOS from [here](https://www.anaconda.com/products/individual).
5. Use the `conda` package manager that comes with Anaconda to build a Python 3.8 environment for trex by running: `conda env create --file=environment.yml --name tracking --channel trexing trex python=3.8.10` from the base directory of this repository in your terminal.  This will install Python package dependencies and might take a few minutes.
6. Run `conda activate trexing` to activate the environment.
7. Install a compatible Tensorflow version with : `pip install --upgrade --force --no-dependencies https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha3/tensorflow_macos-0.1a3-cp38-cp38-macosx_11_0_arm64.whl https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha3/tensorflow_addons_macos-0.1a3-cp38-cp38-macosx_11_0_arm64.whl
`.  Note that **if this step fails** with the error message `not a supported wheel on this platform`, you will need to run `export SYSTEM_VERSION_COMPAT=0`, then try again.  As described here, this issue is related to the Python bug [here](https://www.python.org/downloads/release/python-387/).  As such, until the Python bug is resolved, you will always need to run `export SYSTEM_VERSION_COMPAT=0` before loading/running Python in this environment.
7. Start using trex as described [here](https://trex.run/docs/run.html), by running the command: `trex`.
8. See the next section of this README for information on analyzing specific XXX experiments from XXX.

### Analyze experiments

### Contributing

To contribute features, bug fixes, tests, examples, or documentation to this codebase, please submit a pull request with a description of your proposed changes or additions.

Please include a brief description of your pull request when submitting code and ensure that your code follows the [Pep 8](https://www.python.org/dev/peps/pep-0008/) style guide.  To do this run `pip install black` and `black spacy-for-family-history` to reformat files within your copy of the project using the [black code formatter](https://github.com/psf/black).  The black code formatter is a PEP 8 compliant, opinionated formatter that reformats entire files in place.  You can also use the [autopep8 code formatter](https://packagecontrol.io/packages/AutoPEP8) within your IDE to ensure Pep 8 compliance.
