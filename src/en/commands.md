# Juju Command reference

You can get a list of the currently used commands by entering `juju help
commands` from the commandline. The currently understood commands are listed
here, with some examples.

* [General Commands](#general)
* [Environment-related Commands](#environments)
* [Machine-related Commands](#machines)
* [Charm-related Commands](#charms)
* [Service-related Commands](#services)
* [Unit-related Commands](#units)

##Index

<!-- XXX Sort down columns instead of across rows?
| | | | |
| --- | --- | --- | --- |
| [add-machine](#add-machine) | [add-relation](#add-relation) | [add-unit](#add-unit) | [api-endpoints](#api-endpoints) |
| [authorised-keys](#authorised-keys) | [bootstrap](#bootstrap) | [debug-hooks](#debug-hooks) | [debug-log](#debug-log) |
| [deploy](#deploy) | [destroy-environment](#destroy-environment) | [env](#env) | [expose](#expose) |
| [generate-config](#generate-config) | [get](#get) | [get-constraints](#get-constraints) | [get-env](#get-env) |
| [get-environment](#get-environment) | [help](#help) | [help-tool](#help-tool) | [publish](#publish) |
| [remove-machine](#remove-machine) | [remove-relation](#remove-relation) | [remove-service](#remove-service) | [remove-unit](#remove-unit) |
| [resolved](#resolved) | [retry-provisioning](#retry-provisioning) | [run](#run) | [scp](#scp) |
| [set](#set) | [set-constraints](#set-constraints) | [set-env](#set-env) | [set-environment](#set-environment) |
| [ssh](#ssh) | [stat](#stat) | [status](#status) | [switch](#switch) |
| [sync-tools](#sync-tools) | [terminate-machine](#terminate-machine) | [unexpose](#unexpose) | [unset](#unset) |
| [unset-env](#unset-env) | [unset-environment](#unset-environment) | [upgrade-charm](#upgrade-charm) | [upgrade-juju](#upgrade-juju) |
| [version](#version) | | | |

<!---------------------------------------------->
# General

### help
show help on a command or other topic

### version
print the current version

<!---------------------------------------------->
# Environments

<!--------------------->
## Environment Lifecycle

### bootstrap
start up an environment from scratch

### destroy-environment
terminate all machines and other associated resources for an environment

### sync-tools
copy tools from the official tool store into a local environment

### upgrade-juju
upgrade the tools in a juju environment

<!-- backup -->

<!-- restore -->

<!--------------------->
## Environment Configuration

### authorised-keys
manage authorised ssh keys

### generate-config
generate boilerplate configuration for juju environments

### get-constraints
view constraints on the environment or a service

### get-environment
(alias: get-env)

view environment values

### set-constraints
set constraints on the environment or a service

### set-environment
(alias: set-env)

replace environment values

### switch
(alias: env)

show or change the default juju environment name

### unset-environment
(alias: unset-env)

unset environment values

<!--------------------->
## Environment Info

### api-endpoints
print the API server addresses

### debug-log
display the consolidated log file

### stat
alias for status

### status
output status information about an environment

<!---------------------------------------------->
# Machines

### add-machine
start a new, empty machine and optionally a container, or add a container to a machine

### debug-hooks
launch a tmux session to debug a hook

### remove-machine
removes a machine

### retry-provisioning
retries provisioning for failed machines

### run
run the commands on the remote targets specified

### scp
launch a scp command to copy files to/from remote machine(s)

### ssh
launch an ssh shell on a given unit or machine

### terminate-machine
alias for destroy-machine

<!---------------------------------------------->
# Charms

### help-tool
show help on a juju charm tool

### publish
publish charm to the store

### upgrade-charm
upgrade a service's charm

<!---------------------------------------------->
# Services

### add-relation
add a relation between two services

### deploy
deploy a new service

### expose
expose a service

### get
get service configuration options

<H3>get-constraints</H3>
See [the entry under environment](#get-constraints)

### remove-relation
breaks a relation between two running services

### remove-service
terminates and removes a deployed service

### set
set service config options

<H3>set-constraints</H3>
See [the entry under environment](#set-constraints)

### unexpose
unexpose a service

### unset
set service config options back to their default

<!---------------------------------------------->
# Units

### add-unit
add one or more units of an already-deployed service

### remove-unit
removes a unit

### resolved
marks unit errors resolved


<!--
  - **add-machine:** start a new, empty machine and optionally a container, or add a container to a machine
  - **add-relation:** add a relation between two services
  - **add-unit:** add one or more units of an already-deployed service
  - **api-endpoints:** print the API server addresses
  - **authorised-keys:** manage authorised ssh keys
  - **bootstrap:** start up an environment from scratch
  - **debug-hooks:** launch a tmux session to debug a hook
  - **debug-log:** display the consolidated log file
  - **deploy:** deploy a new service
  - **destroy-environment:** terminate all machines and other associated resources for an environment
  - **env:** alias for switch
  - **expose:** expose a service
  - **generate-config:** generate boilerplate configuration for juju environments
  - **get:** get service configuration options
  - **get-constraints:** view constraints on the environment or a service
  - **get-env:** alias for get-environment
  - **get-environment:** view environment values
  - **help:** show help on a command or other topic
  - **help-tool:** show help on a juju charm tool
  - **publish:** publish charm to the store
  - **remove-machine:** removes a machine
  - **remove-relation:** breaks a relation between two running services
  - **remove-service:** terminates and removes a deployed service
  - **remove-unit:** removes a unit
  - **resolved:** marks unit errors resolved
  - **retry-provisioning:** retries provisioning for failed machines
  - **run:** run the commands on the remote targets specified
  - **scp:** launch a scp command to copy files to/from remote machine(s)
  - **set:** set service config options
  - **set-constraints:** set constraints on the environment or a service
  - **set-env:** alias for set-environment
  - **set-environment:** replace environment values
  - **ssh:** launch an ssh shell on a given unit or machine
  - **stat:** alias for status
  - **status:** output status information about an environment
  - **switch:** show or change the default juju environment name
  - **sync-tools:** copy tools from the official tool store into a local environment
  - **terminate-machine:** alias for destroy-machine
  - **unexpose:** unexpose a service
  - **unset:** set service config options back to their default
  - **unset-env:** alias for unset-environment
  - **unset-environment:** unset environment values
  - **upgrade-charm:** upgrade a service's charm
  - **upgrade-juju:** upgrade the tools in a juju environment
  - **version:** print the current version
-->
