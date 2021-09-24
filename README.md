# trex-cv-experiments

[![python38](https://img.shields.io/badge/python-3-orange.svg)]()
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

Contains code and instructions for [Levin lab](https://ase.tufts.edu/biology/labs/levin/) motion analysis with the [trex](https://github.com/mooch443/trex) computer vision tool

### About

This repository contains proof of concept code and instructions for analyzing video footage from [Levin lab](https://ase.tufts.edu/biology/labs/levin/) using the [trex](https://github.com/mooch443/trex) computer vision tool.  Video data of deformed tadpole experiments was provided by Vaibhav Pai.  After receiving access to this data, follow the sections below to build the environment to install and run trex, then analyze the deformed tadpole videos with the trex tool.  Note that trex comes with [tgrabs](https://trex.run/docs/parameters_tgrabs.html), a tool for live-tracking and video conversion.  Following the instructions below to build the environment for and install trex, will also setup tgrabs.

### Build the Trex Environment

The instructions and code in this repository have been tested on MacOS Big Sur Version 11.5.1 with an Intel Core i7 processor and 32 GB memory.  To build the environment on this or a similar machine, follow the steps below.  For more information about using [Tensorflow](https://github.com/tensorflow/tensorflow) (which powers Trex) in a MacOS [conda environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#activating-an-environment), see [this post](https://github.com/apple/tensorflow_macos/issues/153).

1. Make sure you have git for MacOS installed (see installation instructions [here](https://github.com/git-guides/install-git)).  Type `git` into your terminal to test that the git CLI tool is installed.
2. In your terminal, run `git clone --depth 1 --branch v1.1.3 https://github.com/mooch443/trex` from the base directory of this repository.
3. Make sure you have Anaconda for MacOS installed (see installation instructions [here](https://www.anaconda.com/products/individual)).  Type `conda` into your terminal to test that conda is installed.
4. In your terminal, `cd` to the `trex` subdirectory.
5. Use `conda` to build a Python environment for trex by running: `conda create -n tracking -c trexing trex` from the base directory of this repository in your terminal.  This will install Python package dependencies and might take a few minutes.
6. Run `conda activate tracking` to activate the environment.
7. Start using trex as described [here](https://trex.run/docs/run.html), by running the command: `trex`.
8. See the next section of this README for information on analyzing specific video footage.

### Analyze Deformed Tadpole Experiments

For this proof of concept, I've been given access to video footage of tadpoles from Levin lab.  If interested in contributing, please contact joelstremmel22@gmail.com, and I will connect you with the researchers who might be able to provide access to their footage.  The steps to follow could be replaced with other footage to track and analyze other creatures.

##### Running Trex to Track Tadpoles

1. Once you have access to the footage, download and save all video clips to a directory of your choice.
2. In your directory of footage, identify a `.mp4` file that you would like to convert.
3. In the conda environment, run `tgrabs -i "/path/to/your/video.mp4" -o "desired-video-name"` to [create a `.pv` in a directory on your machine at ~/Videos](https://github.com/mooch443/trex#usage).
4. In the conda environment, run `trex -i "~/desired-video-name.pv" -track_max_individuals 37 -individual_prefix "tadpole" -auto_quit`.  If you happen to know the number of individuals in the experiment, specify this number exactly.

For more information on tracking creatures with trex, see the [trex docs](https://trex.run/docs/).

##### Analyzing Trex Outputs

The analysis to follow uses the video: `black pebble control 2 - muted.m4v` renamed as `black-pebble-control-2-muted.mp4`.

1. To view and analyze the outputs from Trex, install [Jupyter](https://jupyter.org/) by running `pip install notebook` from within your conda environment.
2. To open Jupyter, run `jupyter notebook` from within the base directory of this repository.
3. Open `analyze_tadpole_data.ipynb` to view and run existing code for this analysis.  See contributing instructions regarding adding code.

Next steps for tadpole analysis are documented in the notebook.  Functions and large code blocks in the notebook will eventually be moved to general Python modules in this repository.

### Contributing

To contribute features, bug fixes, tests, examples, or documentation to this codebase, submit a pull request with a description of your proposed changes or additions.

Please include a brief description of your pull request when submitting code and ensure that your code follows the [Pep 8](https://www.python.org/dev/peps/pep-0008/) style guide.  To do this run `pip install black` and `black trex-cv-experiments` to reformat files within your copy of the project using the [black code formatter](https://github.com/psf/black).  The black code formatter is a PEP 8 compliant, opinionated formatter that reformats entire files in place.
