+++
title = "Ubuntu Guest Agent2"
date = 2018-10-26T10:42:12-04:00
draft = true
tags = ["Ubuntu"]
categories = ["Ubuntu","Linux"]
toc = true
+++

## Introduction
Installing the Guest Agent in ubuntu virtual machine is fairly simple and will provide the oVirt-engine with additional information about the VM. The process has two main steps which is adding an install source and installing the ovirt-guest-agent package. Presently the ovirt-guest-agent package for Ubuntu is not in the official repos, but is available through evilissimo who currently maintains the package.

## Methods for Installation

### Using apt-get via terminal to install the oVirt Guest Tools
From a terminal session, type the following

Source list
ds for Installation

### Using YUM via terminal to install the oVirt Guest Tools
From a terminal session, type the following (for oVirt 4.2)

```
sudo yum install centos-release-ovirt42
sudo yum install ovirt-guest-agent-common
```

### Starting the service
From a terminal, enter the following commands to start the oVirt Guest Agent service

Start the service
`sudo systemctl enable --now ovirt-guest-agent.service`

The above command will enable the service to always start at booto, and start the service now so you do not need to reboot the VM.


## Troubleshooting
The web admin interface may take some time to start displaying the memory usage and other types of information. If you find that after some time this information has not been populated, restart the VM by performing a shut down or power off, power on, and verify that the service is started by running:

Service verification
`sudo systemctl status ovirt-guest-agent.service`

A reboot of the virtual machine did not seem to resolve the issue.



## Reference material for adoc files

include::https://asciidoctor.org/docs/asciidoc-syntax-quick-reference[]

include::https://powerman.name/doc/asciidoc[]

`sudo vi /etc/apt/sources.list.d/ovirt-guest-agent.list`

### Source list filler
Paste in the following source

`deb http://download.opensuse.org/repositories/home:evilissimo:ubuntu:/18.04/xUbuntu_18.04/ /`

Write/quit the file.

Finishing up on the terminal

````
wgt http://download.opensuse.org/repositories/home:/evilissimo:/ubuntu:/18.04/xUbuntu_18.04//Release.key
sudo apt-key add - < Release.key
sudo apt-get update
sudo apt-get install ovirt-guest-agent
````

The above command will install ovirt-guest-agent. Accept the prompt to install *ovirt-guest-agent* and any required dependencies.



## Reference material for adoc files

include::https://asciidoctor.org/docs/asciidoc-syntax-quick-reference[]

include::https://powerman.name/doc/asciidoc[]

