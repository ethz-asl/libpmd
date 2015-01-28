# libpmd

## Synopsis:

Driver library for the PMD Technologies GmbH Argos3D P100 ToF camera.

**Author(s):** Martin Profittlich

**Maintainer:** Ralf Kaestner <ralf.kaestner@gmail.com>

**Licsense:** MIT License (MIT)

**Operating system(s):** Debian-based Linux

**Package PPA:** ppa:ethz-asl/drivers

## Description

This project exists to facilitate package-based deployment of the driver.
The provided library and utility executables are published by the vendor
in binary format only. The may be installed and used as-is on supported
Ubuntu LTS distributions.

## Installation

### Installing from packages (recommended for Ubuntu LTS users)

The maintainers of this project provide binary packages for the latest
Ubuntu LTS releases and commonly used system architectures. To install
these packages, you may follow these instructions:

* Add the project PPA to your APT sources by issuing 

  ```
  sudo add-apt-repository ppa:ethz-asl/drivers
  ```

  on the command line

* To re-synchronize your package index files, run

  ```
  sudo apt-get update
  ```

* Install all project packages (and their dependencies) through

  ```
  sudo apt-get install libpmd*
  ```

  or selected packages using your favorite package management tool

### Building from source

To build from source, this project requires the CMake build system with an
open-source macro extension called ReMake.

#### Preparing the build system

If you already have installed ReMake on your build system, you may
skip this step. Otherwise, before attempting to build this project the
traditional CMake way, you must install ReMake following
[these instructions](https://github.com/kralf/remake).

#### Installing build dependencies

The build dependencies of this project are available from the standard
package repositories of recent Ubuntu releases. To install them, simply
use the command

```
sudo apt-get install libusb-0.1-4 libqt4-opengl doxygen pkg-config
```

#### Building with CMake

Once ReMake is available on your build system, you may attempt to build this
project the CMake way. Assuming that you have cloned the project sources into
`PROJECT_DIR`, a typical out-of-source build might look like this:

* Create a build directory using 

  ```
  mkdir -p PROJECT_DIR/build
  ```

* Switch into the build directoy by 

  ```
  cd PROJECT_DIR/build
  ```

* In the build directory, run 

  ```
  cmake PROJECT_DIR
  ```

  to configure the build

* If you want to inspect or modify the build configuration, issue 

  ```
  ccmake PROJECT_DIR
  ```

* Build the project using 

  ```
  make
  ```

* If you intend to install the project, call 

  ```
  make packages_install
  ```

  (from packages on Debian-based Linux only) or 

  ```
  make install
  ```

## Feature requests and bug reports

Since the project authors do not publish the source code, feature requests and
bug reports may unfortunately not be considered by the maintainers.
