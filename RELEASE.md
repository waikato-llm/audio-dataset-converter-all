PyPi
====

Preparation:

* increment version in `setup.py`
* add new changelog section in `CHANGES.rst`
* align `DESCRIPTION.rst` with `README.md`  
* commit/push all changes

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
* upload `audio-dataset-converter-all-X.Y.Z.tar.gz` previously generated with `setup.py`
* publish


Docker
======

* create copy of [docker/latest](docker/latest) and rename it to just released version
* link to new version from [docker/README.md](docker/README.md)
* update version in `bash.bashrc`
* update versions of additional audio-dataset-converter libraries if necessary
* push out to in-house registry and docker hub
