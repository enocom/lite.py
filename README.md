# lite

Creating and deleting bosh directors using
[bosh-deployment](https://github.com/cloudfoundry/bosh-deployment)
is convenient, but requires long commands with many arguments.

Using `lite` retains the convenience of `bosh-deployment` without the
long commands.

## Prerequisites

- Python 2.7 (this is installed by default on most machines)
- `git clone git@github.com:cloudfoundry/bosh-deployment ~/workspace/bosh-deployment`
- VirtualBox v5.1 or higher
- The new [bosh cli](https://github.com/cloudfoundry/bosh-cli)

## Installation

Move `lite` into your `PATH`.

## Usage

``` bash
# to create an env
lite create my-cool-env

# if you need to route *.bosh-lite.com ips to your env do
lite set-routes my-cool-env

# to remove routes for an env
lite unset-routes my-cool-env

# to delete an env
lite delete my-cool-env

# to establish an ssh tunnel to a VM
lite tunnel my-cool-env my-deployment my-instance-group 9999:localhost:3458

# to run a ssh command across an instance_group
lite ssh-command my-cool-env my-deployment my-instance-group 'my cool command'

# to fetch CPU and memory from each process in an instance_group
lite proc-status my-cool-env my-deployment my-instance-group

# to fetch the number of Go routines from each process in an instance_group
lite go-routines my-cool-env my-deployment my-instance-group
```
