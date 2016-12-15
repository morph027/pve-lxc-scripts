#!/bin/bash

if [[ $1 =~ ^[0-9]*$ ]]; then
  if [ -d /sys/fs/cgroup/cpu/lxc/$1 ]; then
    CONTAINER=$1
    shift
    COMMAND=$@
    echo -ne "\e[1;32mexecuting \"$COMMAND\" in container #${CONTAINER} ($(grep -m 1 hostname /etc/pve/lxc/${CONTAINER}.conf | awk '{print $NF}'))\e[0m\n"
    pct exec $CONTAINER /bin/sh -- -c "$COMMAND"
  else
    echo -ne "\e[1;31mcontainer $1 is not running\e[0m\n"
    exit 1
  fi
fi
