# 0x0A Configuration management

## Description

This project is an introduction to Configuration Management
This project contains very basic Puppet manifests.

## Files Info

### Create a file

Using Puppet, create a file in /tmp.

Requirements:

* File path is /tmp/school
* File permission is 0744
* File owner is www-data
* File group is www-data
* File contains I love Puppet

### install a package

Using Puppet, install flask from pip3.

Requirements:

* Install flask
* Version must be 2.1.0

### Execute a command

Using Puppet, create a manifest that kills a process named killmenow.

Requirements:

* Must use the exec Puppet resource
* Must use pkill
