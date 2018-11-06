#!/bin/bash

CONTAINERS=( $(pct list | grep running | awk '{print $1}') )

apt_update() {
lxc-exec $CONTAINER "apt-get update"
lxc-exec $CONTAINER "apt-get dist-upgrade -y"
lxc-exec $CONTAINER "apt-get clean"
lxc-exec $CONTAINER "apt-get autoremove -y"
}

yum_update() {
lxc-exec $CONTAINER "yum -y update"
}

apk_update() {
lxc-exec $CONTAINER "apk upgrade"
}

for CONTAINER in ${CONTAINERS[@]}
do
  lxc-exec $CONTAINER "which apt-get >/dev/null" && apt_update
  lxc-exec $CONTAINER "which yum >/dev/null" && yum_update
  lxc-exec $CONTAINER "which apk >/dev/null" && apk_update
done
