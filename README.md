# Features

## Server

* Install server version from downloads site: `xl-helper install server --version 4.5.0`
* Install latest successful SNAPSHOT from Jenkins: `xl-helper install server`
* Install from the local file: `xl-helper install server --dist /tmp/xl-deploy-4.5.0-server.zip`
* Install and copy all the stuff from old installation: `xl-helper install server --version 4.5.0 --upgrade-from-path ./xl-deploy-4.1.0-SNAPSHOT-server`
* Start the server after installation: `blablabla -start`


## Plugin

* Install plugin version and restart if was started `xl-helper install plugin wls --version 4.5.0`
* Update plugin version and restart if was started

## Cli

* Install CLI version from downloads site: `xl-helper install cli --version 4.5.0`

## Other
* Downloaded artifacts are cached (except snapshots)

# Usage

## Requirements
`pip install jenkinsapi`
`pip install nose`

## Configuration file
Needs to be placed at `~/.xl-helper`
See `conf/.xl-helper.example` as an example.

## Bash alias

It's much more convenient to use `xl-helper` with configured bash alias:

`alias xl-helper="~/xl/research-and-development/xl-helper/xl-help.py"`

# Development

## Desired features

* Unhardcode cache location (currently `/tmp`)
* In-place upgrade of the server
* Installation of plugins snapshots
* Install-as-update for the plugins: install if plugin is missing, upgrade/downgrade if already present
* Plugin upgrade should fail if the plugin is not installed/or newer version is installed
* Versioning and and distribution of the tool
* Handle more corner-cases and errors

## Unit tests

Adding feature = Writing test + writing code

Running tests: `nosetests -v`

Tests are also runnable from IntelliJ

## New version

* `python setup.py sdist` and test the distribution created at `dist` folder;
* Bump the version;
* Create a tag (see previous ones for the format);
* `python setup.py sdist upload`