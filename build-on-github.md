# Build On Github Actions

Our project includes a small C++ app with a build script.
Normally the app will just print "hello world", but when executed with a "-version" flag it will print its current version number.
The version is determined at compile time using this line in the file version.h

```
#define MYAPP_VERSION 1
```

Every build we use a python script to increase the version number. The python script is called `inc_version.py`.

We use a Makefile to build the app, so from the command line we can write:

```
$ make
```

To build the app with the value currently written in version.h, or:

```
$ make version
```

To automatically run the python script and increase version number in version.h
(Of course we'll also need to run normal `make` afterwards to build the program).

## Moving To Github Actions
Your task is to move this project to Github Actions, so that each commit will automatically trigger a version bump and build.

