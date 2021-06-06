# makegen

makegen is a python script that helps you to generate makefiles. It takes as input a very simple description of your project written in YAML file.

Minimal configuration file:

```YAML

# application name
target-name: myapp

# folders with source code files
source-dirs:
    - src
    - library

# folders where to search header files
include-dirs:
    - library

```

You can choose the name of the input and output files, but by default are 'project.yaml' and 'makefile':

```
$ makegen --help
                 _
 _ __ ___   __ _| | _____  __ _  ___ _ __
| '_ ` _ \ / _` | |/ / _ \/ _` |/ _ \ '_ \
| | | | | | (_| |   <  __/ (_| |  __/ | | |
|_| |_| |_|\__,_|_|\_\___|\__, |\___|_| |_|
                          |___/

Generate a makefile to build software projects
    -h --help          Print this text
    -v --version       Print version number
    -i --input <file>  The project configuration file, project.yaml by default
    -o --output <file> The output makefile, makefile by default

Example:
    makegen --input config.yaml --output makefile

$
```

To install:

```
sudo cp makegen.py /usr/local/bin/makegen
sudo chmod +x /usr/local/bin/makegen
```

Completed example with all features defined:

```YAML

# compiler flags, (optional)
cflags: -O3 -std=gnu11 -Wall -pedantic

# linker flags, (optional)
ldflags: -lcurl

# application name, (optional, 'out' by default)
target-name: myapp

# folder where to save the application, (optional, 'dist' by default)
dist: dist

# folder where to build the application, (optional, 'build' by default)
build: build

# folder to install the application, (optional, '/usr/local/bin' by default)
install-dir: /usr/local/bin

# compiler, (optinonal, $CC by default)
compiler: g++

# indicate source file extension,'yes' for 'cpp' or 'no' for 'c', (optional, 'no' by default)
iscpp: yes

# source files folders, (mandatory)
source-dirs:
    - src
    - library

# folders where to search header files
include-dirs:
    - library
    - perry

```
