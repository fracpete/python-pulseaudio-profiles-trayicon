# PyPi

Preparation:

* increment version in `setup.py`
* add new changelog section in `CHANGES.rst`
* commit/push all changes

Commands for releasing on pypi.org (requires twine >= 1.8.0):

```
find -name "*~" -delete
rm dist/*
./venv/bin/python setup.py clean
./venv/bin/python setup.py sdist
./venv/bin/twine upload dist/*
```


# Debian

Prerequisites:

```commandline
sudo apt-get install python3-all python3-stdeb dh-python
```

Generate Debian package with the following commands:

```commandline
rm -f *.tar.gz
rm -Rf deb_dist/*
python3 setup.py --command-packages=stdeb.command bdist_deb
```

# Github

Steps:

* start new release (version: `vX.Y.Z`)
* enter release notes, i.e., significant changes since last release
* upload `python-pulseaudio-profiles-trayicon-X.Y.Z.tar.gz` previously generated with `setyp.py`
* upload `deb_dist/python3-python-pulseaudio-profiles-trayicon_X.Y.Z-1_all.deb` previously generated with `stdeb`
* publish
