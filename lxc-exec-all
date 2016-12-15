#!/bin/bash

CONTAINERS=( $(pct list | grep running | awk '{print $1}') )

for CONTAINER in ${CONTAINERS[@]}
do
  lxc-exec $CONTAINER "$@"
done
