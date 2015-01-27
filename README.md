# libpmd

## Synopsis:

Driver library for the PMD Technologies GmbH Argos3D P100 ToF camera.

**Author(s):** Martin Profittlich
<br/>
**Maintainer:** Ralf Kaestner <ralf.kaestner@gmail.com>
<br/>
**Licsense:** MIT License (MIT)

**Operating system(s):** Debian-based Linux
<br/>
**Package PPA:** ppa:ethz-asl/drivers

## Description

This project exists to facilitate package-based deployment of the driver.
The provided library and utility executables are published by the vendor
in binary format only. The may be installed and used as-is on supported
Ubuntu LTS distributions.

## Installation

## Building from source

We currently do not provide instructions for building this project from
source. Please refer to the below section to learn about package-based
installation.

## Installing from packages

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
