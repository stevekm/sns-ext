[![Build Status](https://travis-ci.org/NYU-Molecular-Pathology/snsxt.svg?branch=master)](https://travis-ci.org/NYU-Molecular-Pathology/snsxt)
# snsxt
Extension to the sns pipeline

# Overview

This program is meant to be an extension to the [sns](https://github.com/NYU-Molecular-Pathology/sns) WES pipeline for whole/target exome sequencing data analysis. 

`snsxt` is a BYOC framework (Bring Your Own Code) for running downstream analysis tasks on sns-wes pipeline output. 

Use this framework to run any extra analysis tasks you like after an `sns` pipeline analysis has finished.

# Usage

## Run

Functionality is currently built into the `run.py` script. Future work will include dedicated modules per analysis task. 

## Test

Unit tests for the various modules included in the program can be run with the `test.py` script. Individual modules can be tested with their corresponding `test_*.py` scripts.

# Components

`snsxt` uses the [`util`](https://github.com/NYU-Molecular-Pathology/util) submodule for expanded functionality and features, including the following:

## `config`

The `config` submodule is used to load various configuration files into global objects which will be accessed later throughout the main program. Configurations should be loaded and set in the `snsxt/config/__init__.py` submodule script. See existing code for examples.

## `classes`

The `classes` submodule contains Python object classes used to represent data from an sns wes analysis. 

## `find`

The `find` submodule is used throughout the program to find files that match given pattern criteria in the filesystem.

## `log`

The `log` submodule contains functions used to intialize, load, and manipulate logging throughout the program. The primary program logging configuration for the program come from the `logging.yml` file, and default log file output is in the `snsxt/logs` directory.

## `qsub`

The `qsub` module contains classes and functions used to submit and monitor jobs on the HPC cluster used at NYULMC, running Sun Grid Engine. 

# Credits

[`sh.py`](https://github.com/amoffat/sh) is used as an included dependency.

[sns](https://github.com/NYU-Molecular-Pathology/sns) pipeline output is required to run this. 
