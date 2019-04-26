+++
title = "Centos Guest Agent2"
date = 2019-04-25T17:58:31-04:00
draft = false
tags = ["Linux","RHV"]
categories = ["Linux","Centos","RHV"]
toc = true
+++

### Methods for Installation

Using YUM via terminal to install the oVirt Guest Tools
From a terminal session, type the following (for oVirt 4.2)

````
sudo yum install centos-release-ovirt42
sudo yum install ovirt-guest-agent-common
````

### Starting the service
From a terminal, enter the following commands to start the oVirt Guest Agent service

Start the service
`sudo systemctl enable --now ovirt-guest-agent.service`

The above command will enable the service to always start at booto, and start the service now so you do not need to reboot the VM.


### Troubleshooting
The web admin interface may take some time to start displaying the memory usage and other types of information. If you find that after some time this information has not been populated, restart the VM by performing a shut down or power off, power on, and verify that the service is started by running:

Service verification
`sudo systemctl status ovirt-guest-agent.service`

A reboot of the virtual machine did not seem to resolve the issue.



### Reference material for adoc files

include::https://asciidoctor.org/docs/asciidoc-syntax-quick-reference[]

include::https://powerman.name/doc/asciidoc[]

