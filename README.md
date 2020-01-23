# Drifter

> adventures in New Bohemia, the drifter is now housebound

*Jehst - The Return of the Drifter*


## What is it?

Drifter is a simple (very simple) replacement for [Vagrant](https://vagrantup.com) based on [Multipass](https://multipass.run).

> :warning: Drifter is pre-alpha quality

## Goals

- make out of the box experience easier (SSH keys, multiple VMs)
- no need to mess around with cloud-init
- simple guest port access via SSH tunnels
- shell script based provisioning


## Dependencies

- Multipass
- `jq`
- macOs (for now)

## Usage


- `./drifter dev ssh` Will start a "dev" vm, based on the 18.04 image, copy the multipass ssh key for your usage and ssh you to the VM. Also forwards the SSH agent
- `./drifter dev suspend` will suspend the vm
- `./drifter dev stop` will send you a present 🎁
- `./drifter dev tunnels` will use SSH to tunnel access to some ports
- `./drfiter dev provision` will run `./provision.sh` script to provision the machine, run as many times as you want
- `./drifter dev shell` will open a shell in the machine, but without any tunnels, SSH agent forwarding etc


# Roadmap

- [ ] create your own user and throw-away SSH key for auth, rather than using the one provided with Multipass
- [ ] configurable ports for tunneling
- [ ] better handling of command line options
- [ ] ability to specify machine names
- [ ] better UX overall
- [ ] custom provision script path
