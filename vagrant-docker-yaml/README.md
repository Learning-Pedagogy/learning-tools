# Running Multiple Docker Containers in Vagrant with YAML

These files were created to allow users to use Vagrant ([http://www.vagrantup.com](http://www.vagrantup.com)) to quickly and relatively easily launch multiple Docker ([http://www.docker.com](http://www.docker.com)) containers. The specifics of the Docker containers are specified in an external YAML file. The configuration was tested using Vagrant 1.7.2, VMware Fusion 6.0.5, and the Vagrant VMware plugin.

## Contents

* **README.md**: The file you're currently reading.

* **host/Vagrantfile**: This file is used by Vagrant to spin up a "host VM" for use with the Vagrant Docker provider. Edit this file to change the Vagrant box you'd like to use; by default, this Vagrantfile uses the "slowe/ubuntu-trusty-x64" box (built for the "vmware_desktop" provider).

* **Vagrantfile**: This file is used by Vagrant to spin up the Docker containers on the host VM created by `host/Vagrantfile`. Unless you change filenames, you should not need to edit this file. All container details are stored in a separate YAML file.

* **containers.yml**: This YAML file contains a list of the Docker containers and their properties for use by Vagrant. You will need to edit this file to specify container friendly name, image, and exposed ports.

## Instructions

1. If you wish to use a box _other_ than my "ubuntu-trusty-x64" base box (running Ubuntu 14.04), edit the `Vagrantfile` in the host subdirectory.

2. Edit the `containers.yml` file to specify the Docker containers that Vagrant should create on the host VM (specified by `host/Vagrantfile`). Each container should contain three properties: `name` (the friendly name to be assigned to the Docker container), `image` (the name of the Docker image to be used for this container), and `ports` (a list of ports to be exposed for the container).

3. From the directory where the main `Vagrantfile` is located, simply run `vagrant up` to spin up the specified host VM and specified Docker containers. Note that Internet access **will be** required to download Docker and the Docker images.

Enjoy!