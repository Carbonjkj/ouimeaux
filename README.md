# ouimeaux

Open source control for Belkin WeMo devices

* Free software: BSD license
* Documentation: http://ouimeaux.rtfd.org.

## Features

* Supports WeMo Switch, Light Switch, Insight Switch and Motion
* Command-line tool to discover and control devices in your environment
* REST API to obtain information and perform actions on devices
* Simple responsive Web app provides device control on mobile
* Python API to interact with device at a low level

## About this fork

The original repository can be found here: https://github.com/iancmcc/ouimeaux

It doesn't appear to be maintained and it doesn't work with modern Python
packages.

It has been forked here so that I can include my modifications to
`requirements.txt` as well as document how to use it.

## Installation

```
$ sudo pip install virtualenv
$ mkdir ouimeaux-env
$ virtualenv ouimeaux-env
$ source ouimeaux-env/bin/activate
$ cd ouimeaux-env
$ pip install git+https://github.com/syphoxy/ouimeaux.git
$ pip install -e 'git+https://github.com/syphoxy/ouimeaux.git#egg=ouimeaux[server]'
```

At this point you should be able to use `wemo` and `wemo server` so long as
you've activated your environment with `source ouimeaux-env/bin/activate`.

**Note:** Ensure that the `pip` and `virtualenv` command you use belongs to a
Python 2 installation. On some systems, there are multiple versions of Python
installed. See below for an example from my Fedora system.

```
$ /bin/ls -1 "$(dirname $(which python))/virtualenv"{,-2} "$(dirname $(which python))/p"{ython,ip}[23]
/usr/bin/pip2
/usr/bin/pip3
/usr/bin/python2
/usr/bin/python3
/usr/bin/virtualenv
/usr/bin/virtualenv-2

$ pip --version
pip 9.0.1 from /usr/lib/python3.5/site-packages (python 3.5)

$ pip2 --version
pip 9.0.1 from /usr/lib/python2.7/site-packages (python 2.7)
```

## Contributing

The instructions for setting up a local environment are slightly different.

```
$ git clone https://github.com/syphoxy/ouimeaux.git

# if you have a feature branch already, do this now
$ cd ouimeaux
$ git checkout feature/YOUR-BRANCH-HERE
$ cd ..

# not entirely certain if this is necessary but
# don't forget to do this every time you switch branches
$ virtualenv ouimeaux
$ source ouimeaux/bin/activate

$ cd ouimeaux
$ pip install -r requirements.txt
$ pip install -e . '.[server]'
```

## Troubleshooting

Open an issue and I'll try to help.
