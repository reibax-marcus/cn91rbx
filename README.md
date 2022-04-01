# cn91rbx_firmware

cn91rbx firmware top project

Welcome to the RbxOS firmware top level project.

This project has been tested in Ubuntu 20.04. It might work in newer versions,
or even in other distros, but a few tweaks might be necessary.

If this is the first time that you work in this types of project this is what you 
should do:

```
./prepare_environment
/bin/bash
# You can optionally export the MACHINE variable here
source set_buildsystem_env /path/to/your/desired/workdir
```

The `prepare_environment` script will download an install all dependencies required 
to build in a Ubuntu 20.04 system and it will also download all git submodules for you.

The dependencies are partly based on yocto documentation:

https://docs.yoctoproject.org/3.4.3/brief-yoctoprojectqs/index.html#build-host-packages

Once you have done this for the first time you can skip the `prepare_environment` step.

In order to navigate this repository as you usually do
in any git project. Before building remember to always run:

git submodule update --init --recursive

The `set_buildsystem_env` script file will show instructions on next steps. You can also
check official Yocto documentation if you want to know more details. 

If you want to build an image for a machine different to the default one you can
run:

```
export MACHINE=cn9130-cf-base
```

If you want the full list of included machine definition files you can run:

```
rbxos_list_machines
```

Keep in mind that only a few of the listed machines have been tested on rbxos.

Documentation is still in progress. This code will assist you in generating the following components:

* A 8GB sdcard image with a bootloader, two boot partitions, two squashfs partitions and two ext4 partitions
* An upgrade file that will allow you to upgrade the system via an on-device web service

In order to achieve this you should prepare the build system and run:

```
bitbake rbxos-upgrade
```
