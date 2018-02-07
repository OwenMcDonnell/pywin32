# pywin32

This is the readme for the Python for Win32 (pywin32) extensions, which provides access to many of the Windows APIs from Python.

See [CHANGES.txt](https://github.com/mhammond/pywin32/blob/master/CHANGES.txt) for recent notable changes.

Note that as of build 222, pywin32 has a new home at [github](https://github.com/mhammond/pywin32).
You can find build 221 and later on github and older versions can be found on
the old project home at [sourceforge](https://sourceforge.net/projects/pywin32/)

A special shout-out to @xoviat who provided enormous help with the github move!

## Binaries
By far the easiest way to use pywin32 is to grab binaries from the [most recent release](https://github.com/mhammond/pywin32/releases)

Feel free to [open issues](https://github.com/mhammond/pywin32/issues) or [pull-requests](https://github.com/mhammond/pywin32/pulls)

## Installing via PIP

Note that PIP support is experimental.

You can install pywin32 via pip:
> pip install pywin32

However, you almost certainly need to execute:
> python Scripts/pywin32_postinstall.py -install

after installation, or you will see various ImportErrors importing core
modules.

Note that if you want to use pywin32 for "system wide" features, such as COM
objects or Windows Services, then you must run the above command from an
elevated command prompt.

## Building from source
Building from source is extremely complicated due to the fact we support building
old versions of Python using old versions of Windows SDKs. If you just want to
build the most recent version, you can probably get away with installing th
same MSVC version used to build that version of Python, grabbing a recent
Windows SDK, setting the `MSSDK` environment variable to point at the root of
the SDK, and running `setup.py` (or `setup3.py` for Python 3.x versions)

`setup.py` is a standard distutils build script.  You probably want:

> python setup.py install

or

> python setup.py --help

You can run `setup.py` without any arguments to see
specific information about dependencies.  A vanilla MSVC installation should
be able to build most extensions and list any extensions that could not be
built due to missing libraries - if the build actually fails with your
configuration, please [open an issue](https://github.com/mhammond/pywin32/issues).
