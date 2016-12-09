# Wagon Builders for Cloudify

Cloudify enables one to build and upload plugins to Cloudify which it then
manages and can be referenced from within blueprints.  The uploaded plugin
must match the platform that Cloudify is running on so either one must
build the wagon on the Cloudify host or ... you build it elsewhere.

Wagon Builders are intended to be a series of light-weight(ish) Docker containers
that enable one to build wagons on a multitude of platforms (starting with our
target OS: CentOS).

# Usage

Assuming you're calling from the current directory of your plugin:

    docker run -it --rm  --volume $(pwd):/wagon --workdir /wagon \
           antillion/wagon-builders:centos-7 wagon create -f -s .

# Makefile           

Pretty much identical.

    build_wagons:
      docker run -it --rm  --volume $$(pwd):/wagon --workdir /wagon antillion/wagon-builders:centos-7 wagon create -f -s .
