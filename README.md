# Drifter

> Adventures in New Bohemia, the drifter is now housebound

*Jehst - The Return of the Drifter*


## What is it?

Drifter is a simple (very simple) replacement for [Vagrant](https://vagrantup.com) based on [Multipass](https://multipass.run).

> :warning: Drifter is pre-alpha quality

By default it will work with two vms `work` or `dev` (my choice :-)), either will be provisioned with 4 CPUs, 4 GB of RAM and 20GB disk running Ubuntu 18.04.

You can choose to use bundled `provision.sh` script, which installs Docker, Emacs etc or pass your own.

## Goals

- make out of the box experience easier (SSH keys, multiple VMs)
- no need to mess around with cloud-init
- simple guest port access via SSH tunnels
- shell script based provisioning


## Dependencies

- Multipass
- `jq`
- macOs (for now)

# Roadmap

- [ ] create your own user and throw-away SSH key for auth, rather than using the one provided with Multipass
- [ ] configurable ports for tunneling
- [x] better handling of command line options
- [ ] ability to specify machine names
- [x] better UX overall
- [x] custom provision script path


# Usage

```
  # Parses out all lines starting with to generate docs
  🧔🏻 Drifter, a small vagrant, powered by multipass
  All commands require the name of the VM to be passed e.g.
  # drifter -n dev -c ssh
  # drifter -n work -c tunnels
  Version=0.0.1
  or
  # drifter -c provision -n dev -p ./my/vm.sh
  Args:
  -n name of the vm (one of: dev, work)
  -c command
  -p if command is provision, path to the bash script to run in the machine
  Commands:
    suspend) Suspend the VM. Unsupported right now
    stop) Stop the VM
    provision) Provision the VM with given Bash script
    tunnels) Start a SSH session with multiple ports opened
    shell) Start a shell, no agent or tunnels opened
    ssh) Start a SSH session with SSH agent forwarded
    ip) Find the IP of the VM
```
