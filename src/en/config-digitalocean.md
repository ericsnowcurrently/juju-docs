# Configuring for DigitalOcean

!!! **Note:** This particular provider is in "beta" as it is developed by a
community member [Kapil Thangavelu](http://github.com/kapilt/juju-digitalocean)
and makes use of [manual provisioning](config-manual.html). Manual provisioning
allows Juju users to implement any cloud provider's API calls and act similar to
a provider implemented in the Juju Core code base.


This process requires you to have a DigitalOcean account. If you
have not signed up for one yet, it can obtained at
[http://digitalocean.com](http://digitalocean.com).

## Prerequisites

You should start by installing Juju, as well as the juju-docean plugin from pip.
this may require you to install python-pip if you do not already have it
installed.

    add-apt-repository ppa:juju/stable
    apt-get update
    apt-get install juju python-pip
    pip install juju-docean


## Configuration

Then you are ready to generate a generic configuration file for Juju, using the
command:

    juju generate-config

This will generate a file, `environments.yaml`, which will live in your
`~/.juju/` directory (and will create the directory if it doesn't already
exist).

!!! **Note:** If you have an existing configuration, you can use
`juju generate-config --show` to output the new config file, then copy and paste
 relevant areas in a text editor etc.

You will need to add a section for Digital Ocean which will look like the
following:

    # https://jujucharms.com/docs/config-digitalocean.html
        digitalocean:
            type: manual
            bootstrap-host: null
            bootstrap-user: root


This is a simple configuration intended to run on Digital Ocean. When
bootstrapped, the tools will be served from the bootstrap-host on storage port
8040.

You will also need to obtain your accounts `ClientID` and `APIKey` from the
Apps & API page.

![Digital Ocean Apps and API page v2 Listing](./media/getting_started_do_api_v2.png)
![Digital Ocean Apps and API page v1 Listing](./media/getting_started_do_api_v1.png)


You will additionally need to set your API Key and ID in your shell's rc files,
for example append the following to `~/.bashrc`

    export DO_CLIENT_ID="XXX"
    export DO_API_KEY="XXX"


then source the file so it's loaded in your current environment.
`source ~/.bashrc`

## DigitalOcean Configuration

In order for Juju to access the nodes, you will have to have an ssh key
populated within the Digital Ocean Control panel.

![Digital Ocean SSH Key Listing](./media/getting_started_do_ssh_key.png)

## Bootstrapping


In order to make DigitalOcean the default provider in which all subsequent
commands issued will be performed against

    juju switch digitalocean

To bootstrap a Digital Ocean environment, you will need to route the command
through the docean plugin that we installed via `pip`.

    juju docean bootstrap

This command also respects [constraints](charms-constraints.html) so you can
size your bootstrap node accordingly should your deployment be of larger scale
than the default instance type can handle

    juju docean bootstrap --constraints="mem=2G, region=nyc2"

Which will create a droplet with 2Gb of ram in the nyc2 data center.

All machines created by this plugin will have the juju environment name as a
prefix for their droplet name if your looking at the DO control panel.


We can now use standard juju commands for deploying service workloads aka charms:

    juju deploy wordpress

Without specifying the machine to place the workload on, the machine will
automatically go to an unused machine within the environment.

## Constraints

Constraints are selection criteria used to determine what type of machine to
allocate for an environment. Those criteria can be related to size of the
machine, its location, or other provider specific criteria.

This plugin accepts the standard juju constraints

- cpu-cores
- memory
- root-disk

!!! **Note:** Additionally it supports the following provider specific
constraints. **region** and **transfer**

- region - to denote the digital ocean data center to utilize. All digitalocean
 data centers are supported and various short hand aliases are defined. ie.
 valid values include ams2, nyc1, nyc2, sfo1, sg1. The plugin defaults to nyc2.

- transfer - to denote the terabytes of transfer included in the instance monthly
cost (integer size in gigabytes).
