PyPi
====

Preparation:

* increment version in `setup.py`
* add new changelog section in `CHANGES.rst`
* align `DESCRIPTION.rst` with `README.md`  
* check whether `adc-venv` lists all the modules
* commit/push all changes

Quick test:

* create virtual environment for testing: `python3 -m venv venvtest`
* install into virtual environment: `./venvtest/bin/pip install .`
* test with help screen of conversion tool: `./venvtest/bin/adc-convert --help`
* remove test environment: `rm -Rf ./venvtest`

Commands for releasing on pypi.org (requires twine >= 1.8.0):

```
find -name "*~" -delete
rm dist/*
python3 setup.py clean
python3 setup.py sdist
twine upload dist/*
```


Github
======

Steps:

* start new release (version: `vX.Y.Z`)
* enter release notes, i.e., significant changes since last release
* upload `audio_dataset_converter_all-X.Y.Z.tar.gz` previously generated with `setup.py`
* publish


Docker
======

* create copy of [docker/latest](docker/latest) and rename it to just released version
* link to new version from [docker/README.md](docker/README.md)
* update version in `bash.bashrc`
* update versions of additional audio-dataset-converter libraries if necessary
* push out to in-house registry and docker hub
