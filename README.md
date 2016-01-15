# pve-lxc-scripts

Some useful scripts fpr Proxmox VE (PVE) LXC containers

## lxc-exec

Execute a command inside a running container.

**Example**

```
lxc-exec 1337 apt-get update
lxc-exec 1337 apt-get install vim -y
```

## lxc-exec-all

Execute a command inside all running containers using ```lxc-exec```.

**Example**

```
lxc-exec-all 1337 apt-get update
lxc-exec-all 1337 apt-get install vim -y
```

## lxc-update-all

Update software on all running containers using ```lxc-exec```.

### Supported systems

* apt-get
* yum
